1. ```https
   postman-student-expert.glitch.me/training
   ```

this returns the instructions for next steps:
```json
"next": [
            {
                "step": "This folder has two requests in it—open the next one `1. Get matches`, look at the address, then come back to this one."
            },
            {
                "step": "Both requests use the same **base** URL `postman-student-expert.glitch.me`—instead of repeating this in every request, let's store it in a variable and reuse the value. Select the part of the address before `/training` and click **Set as variable** &gt; **Set as a new variable**. Enter `training_api` as the **Name** with `postman-student-expert.glitch.me` as the **Value**. Select **Collection** for the **Scope**, making sure the correct collection is selected. Click **Set variable**.",
                "pic": "https://assets.postman.com/postman-docs/postman-training-set-as-var.jpg"
            },
            {
                "step": "In the request builder, edit the address, replacing only `postman-student-expert.glitch.me` (the part before `/training`) with `{{training_api}}`—this is how we reference variables in requests. Click **Send** to make sure the request still behaves the same way and scroll back here.",
                "pic": "https://assets.postman.com/postman-docs/student-expert-url-var.jpg"
            },
            {
                "step": "Before you move on click **Save** to save your request edits. Now open the next request in the collection `Get matches` and do the same for the URL in there, replacing the base part of address with the variable reference—it should now be `{{training_api}}/matches`. Click **Send** on the `Get matches` request and remember to open the **Visualizer** on the response."
            }
        ]
```

2. ```https
   {{training_api}}/matches
   ```
This returns the data object:
```json
"data": {
        "matches": [
            {
                "id": "NL4Vc1Fuj",
                "creator": "postman",
                "matchType": "League Cup Semi Final",
                "opposition": "United",
                "date": "Wed Mar 24 2021 14: 00: 04 GMT+0000 (Coordinated Universal Time)",
                "points": -1
            },
            {
                "id": "rQjm103ofQ",
                "creator": "postman",
                "matchType": "League Cup Quarter Final",
                "opposition": "City",
                "date": "Thu Jan 30 2020 20: 50: 46 GMT+0000 (Coordinated Universal Time)",
                "points": 3
            },
            {
                "id": "odWOBZmn4r",
                "creator": "postman",
                "matchType": "Friendly",
                "opposition": "Athletic",
                "date": "Wed Jan 13 2021 23: 01: 26 GMT+0000 (Coordinated Universal Time)",
                "points": -1
            }
        ]
    },
```
Then the instructions for next steps:
```json
"next": [
    {
        "step": "This request retrieved all matches, but you can also filter the matches using parameters. Open **Params** and enter a new Query parameter, with `status` as the **Key** and `played` or `pending` as the **Value**. You will see the query parameter added to the end of the request address e.g. `/matches?status=pending`. Click **Send** again.",
        "pic": "https://assets.postman.com/postman-docs/student-expert-add-query.jpg"
    }
]
```
3. ```https
   {{training_api}}/matches?status=pending
   ```
This returns the filtered data object:

```json
 "matches": [
          {
              "id": "NL4Vc1Fuj",
              "creator": "postman",
              "matchType": "League Cup Semi Final",
              "opposition": "United",
              "date": "Wed Mar 24 2021 14: 00: 04 GMT+0000 (Coordinated Universal Time)",
              "points": -1
          },
          {
              "id": "odWOBZmn4r",
              "creator": "postman",
              "matchType": "Friendly",
              "opposition": "Athletic",
              "date": "Wed Jan 13 2021 23: 01: 26 GMT+0000 (Coordinated Universal Time)",
              "points": -1
          }
      ]
```
Then the instructions for next steps:
```json
 "next": [
            {
                "step": "So far we've retrieved data from the API, but let's also add some new data. Add another request to the collection. In **Collections** click the *...* on the **1. Begin training - Requests** folder and click **Add Request**–it will open in the request builder. Name the request '2. Add match'.",
                "pic": "https://assets.postman.com/postman-docs/student-expert-add-request.jpg"
            },
            {
                "step": "The new request will appear in the collection folder on the left. In the request builder, enter the URL, `{{training_api}}/match` and select `POST` from the method drop-down list. Click **Send**.",
                "pic": "https://assets.postman.com/postman-docs/student-expert-post-url.jpg"
            }
        ]
```
4. Set up the API key as email client then resent the `POST` request.

Returns a mismatch error since data is empty.\
Add this to body and resend.
```json
{
    "against" : "Academical",
    "match" : "Cup Final",
    "when" : "{{$randomDateFuture}}"
}
```
Now running
```https
{{training_api}}/matches?status=pending
```
Returns the updated filtered data object:
```json
"matches": [
            {
                "id": "NL4Vc1Fuj",
                "creator": "postman",
                "matchType": "League Cup Semi Final",
                "opposition": "United",
                "date": "Wed Mar 24 2021 14: 00: 04 GMT+0000 (Coordinated Universal Time)",
                "points": -1
            },
            {
                "id": "odWOBZmn4r",
                "creator": "postman",
                "matchType": "Friendly",
                "opposition": "Athletic",
                "date": "Wed Jan 13 2021 23: 01: 26 GMT+0000 (Coordinated Universal Time)",
                "points": -1
            },
            {
                "id": "pbOqhm-oY",
                "creator": "antoine's email'",
                "matchType": "Cup Final",
                "opposition": "Academical",
                "date": "Sat Jan 15 2022 15:24:32 GMT-0500 (Eastern Standard Time)",
                "points": -1
            }
        ]
```
The instructions for next steps:
```json
"next": [
            {
                "step": "**Save** your current request, then create another new request still inside the **1. Begin training - Requests** folder. Give it the name `3. Update score` and save it. In the request builder select `PUT` method, and enter the URL `{{training_api}}/match`. Click **Send**."
            }
        ]
```
