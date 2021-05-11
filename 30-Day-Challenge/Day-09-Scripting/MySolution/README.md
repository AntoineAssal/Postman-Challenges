# Day 9 : Scripting

## The BuildUp
1. Add a request to get a random user and `echo` it out.

Created new `GET` request called `get random user` in the folder.
```HTTPS
https://randomuser.me/api
```
<br>

2. Now we want to echo to postman.
Created new `POST` request called `echo the user` in the folder.
```HTTPS
https://postman-echo.com/post
```
Added the `json` to the request's body:
```json
{
"name": "Dawn Ellis",
"email": "dawn.ellis@example.com",
"id": "334eecea-607d-4111-90ee-e57bea971654"
}
```
<br>
3. Chain the requests
In the first request I added this script:

```js
postman.setNextRequest("echo the request");
pm.collectionVariables.set()
```
Then in the second one, so it stops running:

```js
postman.setNextRequest();
```

## Solution 

```HTTPS
https://api.getpostman.com/collections/{{collection_uid}}
```
With updated `collection_uid` collection variable.
## Result

<img src="https://i.imgur.com/SDS4wSE.png">
<p align="center">
<img src="https://media4.giphy.com/media/nNxT5qXR02FOM/giphy.gif?cid=ecf05e47jhenuwvoh3qjxuvzc8u90y0muhbxd0133ni34b2r&rid=giphy.gif&ct=g" />
</p>