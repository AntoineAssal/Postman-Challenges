# Day 6 : Testing

## The BuildUp
Make a `GET` request called `jokes`

```HTTPS
https://api.chucknorris.io/jokes/random
```

Have 2 tests. One that fails and one that passes:

```js
pm.test("Status code is 200", function () {
 pm.response.to.have.status(200);
});

pm.test("Status code is 200", function () {
 pm.response.to.have.status(404);
});
```

<br>


## Solution 

```HTTPS
https://api.getpostman.com/collections/{{collection_uid}}
```
With updated `collection_uid` collection variable.
## Result

<img src="https://i.imgur.com/RbREZms.png">
<p align="center">
<img src="https://media1.giphy.com/media/NfzERYyiWcXU4/giphy.gif?cid=ecf05e47hkcrsrk4nchx80kdh6t555wpdy3wentp4rcg060x&rid=giphy.gif&ct=g" />
</p>