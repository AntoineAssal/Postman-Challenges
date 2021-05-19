# Day 12 : Postman API

## The BuildUp

- Need to add three `GET` requests:

1. Get a single collection.
2. Get a single environment.
3. Get a single workspace.

<br>


1. `get single collection`
```HTTPS
https://api.getpostman.com/collections/{{collection_uid}}
```

2. `get single environment`
```HTTPS
https://api.getpostman.com/environments/{{environment_uid}}
```

3. `get single workspace`
```HTTPS
https://api.getpostman.com/workspaces/{{workspace_id}}
```

- Now we want to have a collection level authorization helper to add an API key so it returns a success code and the collection.


- Finally we want a new environment to store these variables like so :
<img src="https://i.imgur.com/bvca8BP.png">
