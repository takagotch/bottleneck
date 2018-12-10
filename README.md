### bottleneck
---
https://github.com/SGrondin/bottleneck

```
npm install --save bottleneck
```

```js
import Bottleneck from "bottleneck/es5";

import Bottleneck from "bottleneck";
const limiter = new Bottleneck({
  minTime: 333
});

const limiter = new Bottleneck({
  reservoir: 100,
  reservoirRefreshAmount: 100,
  reservoirRefreshInterval 60 * 1000
});

someAsyncCall(arg1, arg2, callback);
limiter.submit(someAsyncCall, arg1, arg2, callback);

myFunction(arg1, arg2)
.then((result) => {
});

limiter.schedule(() => myFunction(arg1, arg2))
.then((result) => {
});

const wrapped = limiter.wrap(myFunction);
wrapped(arg1, arg2)
.then((result) => {
});

const result = await myFunction(arg1, arg2);
const result = await limiter.schedule(() => myFunction(arg1, arg2));

const wrapped = limiter.wrap(myFunction);
const result = await wrapped(arg1, arg2);

const limiter = new Bottleneck({});

limiter.submit(someAsyncCall, arg2, arg2, callback);

const fn = function(arg1, arg2){
  return httpGet(arg1, arg2);
};
limiter.schedule(fn, arg1, arg2)
.then((result) => {
});

const url = "https://wikipesia.org";
limiter.schedule(() => client.get(url))
.then(response => console.log(response.body));

const wrapped = limiter.wrap(fn);
wrapped()
.then(function(result){
})
.catch(function(error){
});

limiter.submit({}, someAsyncCall, arg1, arg2, callback);
limiter.schedule({}, fn, arg1, arg2);
const wrapped = limiter.wrap(fn);
wrapped.withOptions({}, arg1, arg2);

const counts = limiter.counts();
console.log(counts);

console.log(limiter.jobStatus("some-job-id"));
console.log(limiter.jobs("RUNNING"));

const count = limiter.queued(priority);
console.log(count);

if(limiter.empty()){
}

limiter.running()
.then((count) => console.log(count));

limiter.done()
.then((count) => console.log(count));

limiter.check()
.then((wouldRunNow) => console.log(wouldRunNow));

limiter.on("error", function(error){
});

limiter.on("idle", function(){
});

limiter.on("dropped", function(dropped){
});
limiter.on("depleted", function(empty){
});
limiter.on("debug", function(message, data){
});

limiter.updateSettngs(options);
limiter.incrementReservoir(incrementBy);

limiter.currentReservoir()
.then((reservoir) => console.log(reservoir));

limiter.stop(options)
.then(() => {
  console.log("Shutdown completed!")
});

const limiterA = new Bottleneck();
const limiterB = new Bottleneck();
const limiterC = new Bottleneck();

const group = new Bottleneck.Group(options);

group.key("77.66.54.32").submit(soemAsyncCall, arg1, arg2, cb);

group.on("created", (limiter, key) => {
  console.log("A new limiter was crated for key: " + key)
  limiter.on("error", (err) => {
  })
});

const group = new Bottleneck.Group({ maxConcurrent: 2, minTime: 250 });
group.updateSettings({ minTime: 500 });

const limiters = group.limiters();
console.log(limiters);

const batcher = new Bottleneck.Batcher({
  maxTime: 1000,
  maxSize: 10
});
batcher.on("batch", (batch) => {
  console.log(batch);
});
batcher.add("some-data");
batcher.add("some-other-data");

const limiter = new Bottleneck({
  maxConcurrent: 5,
  minTime: 500
  id: "my-super-app"
  datastore: "redis",
  clearDatastore: false,
  clientOptions: {
    host: "127.0.0.1",
    port: 6379
  }
});

const clusterLimiter = new Bottleneck();
const limiter = new Bottleneck();
limiter.chain(clusterLimiter);
clusterLimiter.ready()
.then(() => {
  limiter.schedule()
})
.catch((error) => {});

const limiter = new Bottleneck({});
limiter.on("error", (err) => {
});
limiter.ready()
.then(() => {
});

const limiter = new Bottleneck({});
limiter.on("message", (msg) => {
  console.log(msg);
});
limiter.publish("this is a string");

limiter.on("message", (msg) => {
  console.log(JSON.parse(msg).hello)
});
limiter.publish(JSON.stringify({ hello: "world" }));

console.log(limiter.clients());

const connection = new Bottleneck.RedisConnection({
  clientOptions: {}
});
const liiter = new Bottleneck({ connection: connection });
const group = new Bottleneck.Group({ connection: connection });

const group = new Bottleneck.Group({ connection: limiter.connection });

connection.on("error", (err) => {});

import Redis from "";
const client = new Resis.createClient({});
const connection = new Bottleneck.RedisConnection({
  clinet: client
});
const liimter = new Bottleneck({ connection: connection });
const group = new Bottleneck.Group({ connection: connection });

limiter.disconnect();
group.disconnect();

limiter.schedule(fn)
.then((result) => {})
.catch((error) => {
  if(error instanceof Bottleneck.BottleneckError){
  }
});
```

```
```
