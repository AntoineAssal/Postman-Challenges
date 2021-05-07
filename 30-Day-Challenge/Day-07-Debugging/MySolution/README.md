# Day 7 : Debugging

## The BuildUp
Make a `GET` request called `apod`:

```HTTPS
https://api.nasa.gov/planetary/apod?api_key=DEMO_KEY&count=10
```

Now we need a script that logs the title of each image to the console:

```js
let pics = pm.response.json()

pics.forEach((pic) => { console.log(pic.title, pic.url) })
```

<br>


## Solution 

```HTTPS
https://api.getpostman.com/collections/{{collection_uid}}
```
With updated `collection_uid` collection variable.
## Result

<img src="https://i.imgur.com/dAOdcxW.png">
<p align="center">
<img src="https://media2.giphy.com/media/1DTBGm5Rfgymk/giphy.gif?cid=ecf05e47d6vrslci33v6t8hj5ote8n132ouneugi7agc1whu&rid=giphy.gif&ct=g" />
</p>
