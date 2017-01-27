When configuring eslint rules, you can use the explicit, or implicit values:

```
"rules": {
  "rule_1": 0,
  "rule_2": 1,
  "rule_3": 2
}
```

is equivalent to 

```
"rules": {
  "rule_1": "off",
  "rule_2": "warn",
  "rule_3": "error"
}
```

