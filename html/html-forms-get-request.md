So a website I was working on showed a strange entry in our logs one day.
A form that POSTs data to a backend server was logged as a GET request with a query string.  
The query string contained all the form fields.  
We couldn't figure out how this could have happened...
```
Person A: maybe a user added the query string in an attempt at getting information from the server...
Person B: plausible, but odd in that they managed to obtain and meticulously copy all of the html form fields by name onto that query string...
Person C: well there's nothing in the code base that would cause such a request, how else could it have been added to the URL?
```
And this is where it stood for days, until a colleague came up with a brilliant observation and hypothesis which was this...

Observation
* Our HTML form POST event is handled through Javascript (AngularJS)
* Our form does not include a `method` attribute
* By default, HTML forms, on submit, will make a GET request to the current url (WITH THE FORM ELEMENTS TRANSCRIBED TO THE QUERY STRING)

Hypothesis
* User fills out form
* Something happens to their client that takes down JS/Angular while user is submitting form
* HTML is left to fend for itself, and makes the GET request with the form fields in the query string

You can see this for yourself by putting the following into a browser, filling out the form, and clicking submit...
```
<form>
  <input type="text" name="foo">
  <input type="text" name="bar">
  <input type="submit">
</form>
```
Look in the URL bar and you'll see the following query string `?foo=asdf&bar=qwer`
