node-object-stream
==================

This is a simple stream implementing node's Transform interface. It parses an input stream and emits `'object'` events with parsed JSON objects when it reaches a full JSON object, and errors out when it encounters invalid JSON. To be put on npm in a bit.

# To use:

```
var NodeObjectStream = require('node-object-stream');
var objectStream = getReadableStreamSomehow().pipe(new NodeObjectStream);

// gives you a tidy little javascript object
objectStream.on('object', function(obj){
  doSomethingWithObject(obj);
});

// fires when stream has no more data
objectStream.on('end', function(){
  doSomethingWhenStreamIsDone();
});
```

As it inherits from the Transform stream interface, this stream can use both the standard readable and writable interfaces detailed in the [node documentation](https://nodejs.org/api/stream.html).

# License

This is GPL, duh.

Thanks for stopping by!
