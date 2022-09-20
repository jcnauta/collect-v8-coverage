# collect-v8-coverage

Use this module to start and stop the V8 inspector manually and collect precise (block-level) coverage with call counts.

```js
const {CoverageInstrumenter} = require('collect-v8-coverage');

const instrumenter = new CoverageInstrumenter();
await instrumenter.startInstrumenting();

// require some modules, run some code

await instrumenter.getCoverage();  // get coverage since startInstrumenting-call

// do more stuff

await instrumenter.getCoverage();  // get coverage since last getCoverage-call

const coverage = await instrumenter.stopInstrumenting();

```
