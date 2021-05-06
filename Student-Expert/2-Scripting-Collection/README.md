1. ```https
   {{mock_url}}/players
   ```

this returns the instructions for next steps:
```json
"steps": [
            {
                "note": "In the **Tests** tab for the request, add the following test function.",
                "js_code": [
                    "pm.test('Status code is 200', function () {",
                    "    pm.response.to.have.status(200); ",
                    "});"
                ]
            },
            {
                "note": "The `pm.test` function will use the first text string parameter to output the test result in Postman. This test checks whether the response status code is `200`. You can access test code snippets on the right of the test editing area. **Save** your request and click **Send** then check the **Test Results** in the response area. (_Click **Body** > **Visualize** to get back to these instructions._)",
                "pic": "https://assets.postman.com/postman-docs/student-expert-test-added.jpg"
            }
        ],
        "next": [
            {
                "step": "Try making your test fail by changing the status code check to `400`, **Send** again to see how a failed test appears.",
                "pic": "https://assets.postman.com/postman-docs/student-expert-test-failed.jpg"
            },
            {
                "step": "Once you have your test failing, open the next request in the folder `Get specific player` and click **Send**."
            }
        ]
```

2. ```https
   {{mock_url}}/players
   ```
Returns an error since no player is specified. So change it to :
```https
{{mock_url}}/player?id={{player_id}}
```
Use this script to assign a value to the player:
```js
pm.test('Status code is 200', function () {
    pm.response.to.have.status(200); 
});
var player_list=pm.response.json().data.players;
pm.environment.set('player_id', player_list[Math.floor(Math.random() * player_list.length)].id);
```
Now it returns proper data :
```json
 "data": {
        "name": "Aurore",
        "played": 684
    },
```
And the instructions for next step:
```json 
"next": [
            {
                "step": "Before you continue with scripting, add a description to this request—the description will appear within the collection documentation, which you would use if you were e.g. publishing an API for public use. In the Postman app, at the top of this request tab, to the left of the request name, expand and and click to edit. Add a short description of the request (you can use markdown) and click **Save**. If you're using the web version, use the little documentation icon to the right of the request.",
                "pic": "https://assets.postman.com/postman-docs/student-expert-add-description-web.jpg"
            },
            {
                "step": "From the app, open the collection on the left using the arrow &#9658; button and click **View in web** to see your description in the collection docs (in the browser). On the web you will see your docs appear inline. You can add descriptions to each request, to the collection as a whole, and to various other components."
            },
            {
                "step": "Open the next request `Get stats` and click **Send**."
            }
        ]
```
3. ```https
   {{mock_url}}/stats
   ```
Returns stats data:

```json
 "data": {
        "won": 9,
        "lost": 3,
        "drew": 4
    },
```
4. We need a testing script to verify that all fields are included in the object returned.
```js
pm.test('Status code is 200', function () {
    pm.response.to.have.status(200); 
});
pm.test('Stats include all fields', function () {
    var jsonData = pm.response.json().data;
    pm.expect(jsonData).to.have.all.keys('won', 'lost', 'drew');
});
```
And the instructions for next step:
```json
"next": [
            {
                "step": "You should see your test results output including passed and failed status. _Note that you can also use the **Console** at the bottom left to drill down into requests and responses._",
                "pic": "https://assets.postman.com/postman-docs/student-expert-runner-output-web.jpg"
            },
            {
                "step": "Finally, you're going to use additional scripting to change the request execution order. In the **Tests** tab for the `Get specific player` request, add the following code. The `played` number is a random int between 0-1000, so the code sets Postman up to re-run the collection from the `Get all players` request however many times it takes to find a `played` value greater than 750. Check out where the `played` field appears in the response by opening **Body** > **Pretty** in the request. **Save** the request.",
                "js_code": [
                    "if(pm.response.json().data.played<750) postman.setNextRequest('Get all players');"
                ]
            },
            {
                "step": "With all of your requests saved, open the collection runner again, and click the run you ran earlier from the **Recent Runs** list. Click **Retry** to run your collection again—it might run a different number of times whenever you run it depending on how long it takes to hit that >750 played value. Try clicking **Retry** a few times to see how it behaves differently each time (note that you only ran one iteration but built a loop workflow using `setNextRequest`—you can explicitly set the number of iterations when you set the run up instead of leaving it to chance like you did here).",
                "pic": "https://assets.postman.com/postman-docs/student-expert-runner-result-web.jpg"
            },
            {
                "step": "You've worked through the Postman Student Expert training collection! 🤓😎🥳 To complete your training, open the final folder in the collection **3. Check Progress** &gt; open the **Skill check** request, and hit **Send**. Complete the steps listed in the **Visualize** view until you get a success response."
            }
        ]
```
