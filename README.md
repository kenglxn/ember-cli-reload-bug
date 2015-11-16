# Ember-cli-reload-bug

This repo demonstrates how test reloading is failing using chrome with `ember test --server`.


## To reproduce bug do following:

1: Start ember test in server mode
```bash
npm install
bower install
ember test --server
```

2: while tests are running, load the faling test:
```bash
git checkout a8af8138095dee42367157154772ee7771543d60
# At this point the tests should be failing due to integrity check.
#
# Uncaught Error: Assertion Failed: The tests file was not loaded. Make sure your tests index.html includes "assets/tests.js"
```

3: Load up the passing test with integrity workaround in place
```bash
git checkout 1cb5c2ff0dd6625efa95f355608987acfa3391c8
```

4: Restart the ember test suite in server mode
```bash
ember test --server
```

5: Load up the failing test again
```bash
git checkout a8af8138095dee42367157154772ee7771543d60
#
# Et voila, the actual test failure:
#
# 1 error
#         expected true
```

### Error output in chrome:

[test-failure.log](test-failure.log)

### Relevant Screenshots:

![browser](https://raw.githubusercontent.com/kenglxn/ember-cli-reload-bug/master/browser.png "Browser screenshot")

![console](https://raw.githubusercontent.com/kenglxn/ember-cli-reload-bug/master/console.png "Console screenshot")
