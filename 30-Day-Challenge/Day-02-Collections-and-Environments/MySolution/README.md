# Day 2 : Collections and Environments 

## The BuildUp
 While having `{{baseURL}}` set up in `Env` like so :
 <img src="https://i.imgur.com/1TB7KXJ.png">   

1. Post with raw text:
    ```https
    {{baseURL}}/post
    ```
2. Get with params:
   ```https
   {{baseURL}}/get?foo=bar
   ```
## Solution 

```https
GET https://api.getpostman.com/collections/{{collection_uid}}
```
With my env looking like :
<img src="https://i.imgur.com/YbrGFjR.png">

## Result
<img src="https://i.imgur.com/u5TXhuS.png">

## Solution 2 

My solution 1 didn't respect the capitalization and number of variables for 1. and 2.\
So the one that worked is:
1. POST with raw text:
    ```https
    {{baseURL}}/post
    ```
2. GET with params:
   ```https
   {{baseURL}}/get?foo=bar&name=ferret
   ```
## Result

<img src="https://i.imgur.com/xTUKIm5.png">
<p align="center">
<img src="https://media1.giphy.com/media/Rznz8HjrKQAOQ/giphy.gif?cid=ecf05e47eb8e64j0aasd8oot8tck9rg49vhqqzxee75hwzq1&rid=giphy.gif&ct=g" />
</p>