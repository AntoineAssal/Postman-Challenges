# Day 8 : Running Collections

## The BuildUp
1. Add a request to get a random user and one test to determine if its successful.

Created new `GET` request called `get random user` in the folder.
```HTTPS
https://randomuser.me/api
```

Now we want to test the response:

```js
pm.test("Status code is 200", function () {
 pm.response.to.have.status(200);
});
```

<br>
2. Now we want another request to get only one female user and test if its successful.

Created new `GET` request called `get female user` in the folder.
```HTTPS
https://randomuser.me/api?gender=female
```
Now we want to test the response:

```js
pm.test("Status code is 200", function () {
 pm.response.to.have.status(200);
});
```
<br>
3. Now we want to get one user who is a female and french.

Created new `GET` request called `get french user` in the folder.

```HTTPS
https://randomuser.me/api?gender=female&nat=FR
```
Now we want to test the response:

```js
pm.test("Status code is 200", function () {
 pm.response.to.have.status(200);
});
```

## Solution 

```HTTPS
https://api.getpostman.com/collections/{{collection_uid}}
```
With updated `collection_uid` collection variable.
## Result

<img src="https://i.imgur.com/TaqjnTr.png">
<p align="center">
<img src="https://media3.giphy.com/media/Vi6fwn76gPynTeoL6W/giphy.gif?cid=ecf05e47o0lq8mn5h13ju9aawk2ecwz16wwtcbryru7aa2g9&rid=giphy.gif&ct=g" />
</p>