# Day 3 : Add Request Details

## The BuildUp

1. raw JSON body
    ```https
    {{baseURL}}/post
    ```
2. Add this to body field:
```json
    {
        "data": "doodles"
    }   
```

## Solution 
 
```HTTPS
https://api.getpostman.com/collections/{{collection_uid}}
```
- With the `collection_uid` variable being set to the value of Day-03 Collection and not Day-02.

- Because of that I changed it to a `collection variable` instead of `environment variable` since it will change for every day.


## Result

<img src="https://i.imgur.com/Vr2Zs4p.png">
<p align="center">
<img src="https://media3.giphy.com/media/THIvbrqPhSsTHxpuua/giphy.gif?cid=ecf05e47eb8e64j0aasd8oot8tck9rg49vhqqzxee75hwzq1&rid=giphy.gif&ct=g" />
</p>