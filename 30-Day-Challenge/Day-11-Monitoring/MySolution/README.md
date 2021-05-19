# Day 11 : Monitoring

## The BuildUp

1. Add a `GET` request called `should I water the plants?`
Created new `Get` request called `should I water the plants` in the folder.

```HTTPS
https://water-ttl.herokuapp.com/hygrometer
```

Now we want to test the response:

```js
pm.test("Status code is 200", function () {
 pm.response.to.have.status(200);
});
```

<br>

2. Now we want another request to water the plants called  `water the plants`.

Created new `POST` request called `water the plants` in the folder.
```HTTPS
https://water-ttl.herokuapp.com/water
```
With a `form-data` value of `duration:10`. Meaning water it for 10 seconds.

<br>


3. Now we want water the plants only when the soil is too dry (less than 0.60). 
   - The returned `json` is in percentages so I'm assuming this is outdated and meant 60%. 
   - If the soil is not too dry the collection should stop running.
   - 
<img src="https://i.imgur.com/Qrxz8yf.png">
   
So our condition is based on this value - Created new `Script` in **Tests**:
```js
pm.test("Status code is 200", function () {
 pm.response.to.have.status(200);
});

waterLevel = parseFloat(JSON.parse(responseBody).level);

if (waterLevel < 60.00){
postman.setNextRequest("water the plants");
}
else postman.setNextRequest(null);
```

4. Schedule a Monitor that waters the plants following these conditions every day during the week (Monday to Friday).
   
<p align="center">
<img src="https://i.imgur.com/n4t5JFK.png" width="300">
</p>



## Solution

```HTTPS
https://api.getpostman.com/collections/{{collection_uid}}
```
With updated `collection_uid` collection variable.
## Result

<img src="https://i.imgur.com/jOnUElQ.png">
<p align="center">
<img src="https://media3.giphy.com/media/10GN73YGycPXQk/giphy.gif?cid=ecf05e47yycow4lq21phg6iiousa8hen4wnx1b8i7qthywr8&rid=giphy.gif&ct=g" />
</p>
