# Requests

## Variables
Instead of using the same `base url` every time I can put that in a variable.

## Auth Key
- When using `POST` on the `API`, an `Auth Key` is required to authorize my request.
- The `key` is inherited from the parent collection but I can edit it and store it in a variable too so it's not easily accessible.

### Steps
1. Open the `Authorization` tab for the request.
   
2. Select `Inherit auth from parent` from the `Type` drop-down list.
   
3. Click `…` and choose `Edit`.
   
4. Open the `Authorization` tab. Postman will add the `API key` details to the header for every request using the name `match_key` and the `value` specified by the referenced `email_key` variable.
   
5. Add a variable to the collection. Use the name `email_key` and enter email address in both value fields.
 

# Data

## POST

1. In `Body`, select `raw` and `JSON` instead of `Text` in the drop-down list.

2. ```json
   {
	"match": "Cup Final",
	"when": "{{$randomDateFuture}}",
	"against": "Academical"
    }
    ```
3. Send the `POST` request.    
   
## PUT

1. Change method to `PUT`
   
2. Specify the endpoint `{{training_api}}/match`.

3. Specify the match to update.

4. Add `match_id` with the specified `id` value to filter by, do that in the `key` column in `Params` tab.

5. ```json
   {
       "points" : 5
   }
6. Sned the `PUT` request to update the value of specified match.
   
## DELETE
1. Change method to `DELETE`
   
2. Specify the endpoint `{{training_api}}/match/:match_id`.

3. Add `match_id` with the specified `id` value used with the `POST` request.

4. Send the `DELETE` request to remove the record of that match.