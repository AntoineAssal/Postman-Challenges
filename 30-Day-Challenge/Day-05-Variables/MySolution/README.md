# Day 5 : Variables

## The BuildUp
In the `GET` request called `collection variable`

Change:
```HTTPS
https://api.coindesk.com/v1/bpi/currentprice/btc.json
```
To :
```HTTPS
{{coindeskBaseUrl}}/v1/bpi/currentprice/btc.json
```
By having it set up as a `collection variable` like so:

<img src="https://i.imgur.com/h7daYGV.png">

<br>

Then duplicate the request and renew the new one to `global variable`.

Now we change it to:
```HTTPS
{{coindeskBaseUrl}}/v1/bpi/currentprice/{{currency}}.json
```
By having set up a global variable `currency` like so:

<img src="https://i.imgur.com/nHohhpU.png">



## Solution 

```HTTPS
https://api.getpostman.com/collections/{{collection_uid}}
```
With updated `collection_uid` collection variable.
## Result

<img src="https://i.imgur.com/G88XGrP.png">
<p align="center">
<img src="https://media4.giphy.com/media/USyPsstb0PS9Am0l6q/giphy.gif?cid=ecf05e47pnhqz2j2kbkem4z2g0fnhfdqnhsq4q8rfzsm6g8r&rid=giphy.gif&ct=g" />
</p>