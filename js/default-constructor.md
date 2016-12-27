In ES6 class syntax a default constructor is provided for derived classes, if no constructor is defined.

The default constructor calls the super class constructor with the same arguments the derived class constructor was sent.

    constructor(...args) {
        super(...args);
    }

NOTE: When the constructor is defined explicitly, there is no default call to `super`

