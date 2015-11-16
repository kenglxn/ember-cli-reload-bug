# Ember-cli-reload-bug

This repo demonstrates how test reloading is failing using chrome with `ember test --server`.


## To reproduce bug do following:

1. Start ember test in server mode

    npm install
    bower install
    ember test --server

2. while tests are running, load the faling test:

    git checkout a8af8138095dee42367157154772ee7771543d60
    # At this point the tests should be failing due to integrity check.

3. Load up the passing test with integrity workaround in place

    git checkout 1cb5c2ff0dd6625efa95f355608987acfa3391c8

4. Restart the ember test suite in server mode

    ember test --server

5. Load up the failing test again

    git checkout a8af8138095dee42367157154772ee7771543d60
