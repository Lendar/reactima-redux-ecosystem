## Best Node.js quotes and code extractions
* 0 What is an error-first callback?
```javascript
fs.readFile(filePath, function(err, data) {  
  if (err) {
    //handle the error
  }
  // use the data object
});
```
Check basic knowledge on how async operations work
* 1 How can you avoid callback hells?
  * modularization: break callbacks into independent functions
  * use Promises
  * use yield with Generators and/or Promises
* 2 How can you listen on port 80 with Node?  
  Run the application on any port above 1024, then put a reverse proxy like nginx in front of it.
* 3 What's the event loop?  
  * Under the hood Node.js uses many threads through libuv. Every I/O requires a callback - once they are done they are pushed onto the event loop for execution.
  * :clapper: [Philip Roberts: What the heck is the event loop anyway?](https://www.youtube.com/watch?v=8aGhZQkoFbQ)