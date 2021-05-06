# Progress Check

Complete each of the following request configurations and keep hitting Send to see the list update. When you're done you'll get a 200 OK status code!
### 1. Change the request method. ✅


### 2. Add `email` as a query param, with your student training email address as the value.✅

### 3. Add JSON body data including a field `name` with the value as your name.✅
```json
{
    "name":"Antoine"
}
```
### 4. Add API Key auth with the Key name `auth_key` and how much you learned from the student expert template (e.g. `loads`, `nothing`, etc) as the value (add to the request header).✅

### 5. Add a new variable to the collection, naming it `myCourse` and enter the reason you're learning about APIs as the Current value. (Leave the other var in place.)✅

### 6. Add a test script that gets the value of the `rand` property in the response JSON and sets it as the value of a variable (at collection or environment scope) named `responseData`. ✅
```js
var rand_var = pm.response.json().rand;
pm.environment.set('responseData', rand_var);
```






Returns 
```json
"done": true,
    "skills": [
        {
            "name": "Changed method",
            "hint": "Change the request method to `POST`, `PUT`, or `DELETE`.",
            "value": true
        },
        {
            "name": "Sent query parameter",
            "hint": "Add `email` as a query param, with your student training email address as the value.",
            "value": true
        },
        {
            "name": "Added body data",
            "hint": "Add JSON body data including a field `name` with the value as your name.",
            "value": true
        },
        {
            "name": "Authorized",
            "hint": "Add API Key auth with the Key name `auth_key` and how much you learned from the student expert template (e.g. `loads`, `nothing`, etc) as the value (add to the request header).",
            "value": true
        },
        {
            "name": "Set a variable",
            "hint": "Add a new variable to the collection, naming it `myCourse` and enter the reason you're learning about APIs as the Current value. (Leave the other var in place.)",
            "value": true
        },
        {
            "name": "Added a script",
            "hint": "Add a test script that gets the value of the `rand` property in the response JSON and sets it as the value of a variable (at collection or environment scope) named `responseData`. Hint: You'll need to Send the request twice after adding your code because it won't save the value until after the response is received the first time.",
            "value": true
        }
    ],
```
