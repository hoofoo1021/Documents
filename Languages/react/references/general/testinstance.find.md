# testInstance.find()

#### `testInstance.find()` <a href="#testinstancefind" id="testinstancefind"></a>

```
testInstance.find(test)
```

Find a single descendant test instance for which `test(testInstance)` returns `true`. If `test(testInstance)` does not return `true` for exactly one test instance, it will throw an error.
