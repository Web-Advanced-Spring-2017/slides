class: center, middle

# Asynchronous Programming

---
## Concepts
**Alternatives to Callbacks**

- Modularise your code
- Use promises
- Use event-driven programming
- Use Async.js
- Use generators.

---
## Steps
- Step 1 : Async vs Sync Code
- Step 2 : Callback Hell
- Step 3 : Promises
- Step 4 : Multiple Promises
- Step 5 : Promise Lib
- Step 6 : Create your own promise
- Step 7 : Promise While Loop
---
class: center, middle
![img](http://i.imgur.com/bmkgMHb.gif)

---
class: center, middle

### How callbacks work?
```js
//The anonymous function is not being executed there in the parameter. ​
​//The item is a callback function
$("#btn_1").click(function() {
  alert("Btn 1 Clicked");
});
```
**Callback Functions Are Closures**

When we pass a callback function as an argument to another function, the callback is executed at some point inside the containing function’s body just as if the callback were defined in the containing function. 
---
class: middle
### Example
```js
function do_a(){
  console.log( '`do_a`: this comes out first');
}
 
function do_b(){
  console.log( '`do_b`: this comes out later' );
}
 
do_a();
do_b();
```
Source: [dreamersLab](http://dreamerslab.com/blog/en/javascript-callbacks/)
---
class:middle

```js
`do_a`: this comes out first
`do_b`: this comes out later
```

---
class:middle

```js
function do_a(){
  // simulate a time consuming function
  setTimeout( function(){
    console.log( '`do_a`: this takes longer than `do_b`' );
  }, 1000 );
}
 
function do_b(){
  console.log( '`do_b`: this is supposed to come out after `do_a` but it comes out before `do_a`' );
}
 
do_a();
do_b();
```
---
class:middle

```js
`do_b`: this is supposed to come out after `do_a` but it comes out before `do_a`
`do_a`: this takes longer than `do_b`
```
---
class:middle

```js
function do_a( callback ){
  setTimeout( function(){
    // simulate a time consuming function
    console.log( '`do_a`: this takes longer than `do_b`' );
 
    // if callback exist execute it
    callback && callback();
  }, 3000 );
}
 
function do_b(){
  console.log( '`do_b`: now we can make sure `do_b` comes out after `do_a`' );
}
 
do_a( function(){
  do_b();
});
```
---
class:middle

```js
`do_a`: this takes longer than `do_b`
`do_b`: now we can make sure `do_b` comes out after `do_a`
```
---
class:middle
### [Example code](http://javascriptissexy.com/understand-javascript-callback-functions-and-use-them/) using MongoDB in Nodejs 
```js
var p_client = new Db('integration_tests_20', new Server("127.0.0.1", 27017, {}), {'pk':CustomPKFactory});
p_client.open(function(err, p_client) {
    p_client.dropDatabase(function(err, done) {
        p_client.createCollection('test_custom_key', function(err, collection) {
            collection.insert({'a':1}, function(err, docs) {
                collection.find({'_id':new ObjectID("aaaaaaaaaaaa")}, function(err, cursor) {
                    cursor.toArray(function(err, items) {
                        test.assertEquals(1, items.length);
​
                        // Let's close the db​
                        p_client.close();
                    });
                });
            });
        });
    });
});
```
---
class: middle, center
## Promises
![Promise](https://media.giphy.com/media/Il1dji926Y7qo/giphy.gif)

The Promise object is used for asynchronous computations.

A Promise represents a value which may be available now, or in the future, or never.

[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

---
class: middle

### A Promise is in one of these states:

- **pending**: initial state, not fulfilled or rejected.
- **fulfilled**: meaning that the operation completed successfully.
- **rejected**: meaning that the operation failed.

![img](https://mdn.mozillademos.org/files/8633/promises.png)

#### [Overview - MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)

---
class: middle, center

```js
fs.readFile('directory/file-to-read', function(err, file) {
  if (error) {
    //handle error
  } else {
    //do something with the file
    fs.mkdir('directory/new-directory', function(err, file) {
      if (error) {
        //handle error
      } else {
        //new directory has been made
        fs.writeFile('directory/new-directory/message.txt', function(err, file) {
          if (error) {
            // handle error
          } else {
            // File successfully created
          }
        })
      }
    })
  }
})

```
---
class: middle, center

```js
processJson()

function processJson() {
	var jsonContent = null // Private Scope
	fs.readFileAsync("data/sample.json", "utf8")
		
		.then((fileData) => {
			fileData = JSON.parse(fileData)
			return fileData
		})
		
		.then((jsonData) => {
			console.log("Data type is: ", typeof(jsonData))
			jsonContent = jsonData // Store it globally for now, before we check for directory
			return null
		})
		
		.then(() => {
			return mkdirp.mkdirpAsync('new-data')
		})
		
		.then(() => {
			result = JSON.stringify(jsonContent)
			fs.writeFileAsync('new-data/message.txt', result)
			console.log("Wrote to file")
		})
		
		.catch((e) => {
			console.log("Error", e)
		})
}

```

---
class: middle, center

#### Mongoose Promises
![img](http://erikaybar.name/content/images/2015/10/ListMaster.png)
---
class: center, middle

## Let's code

---
class: center, middle

When a JavaScript date has gone bad, “Don’t call me, I’ll callback you. I promise!”