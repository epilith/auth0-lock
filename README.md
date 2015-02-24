# auth0-lock
Polymer element for login using auth0.

```html
<auth0-lock autoLogin="true" 
            domain="AUTH0_DOMAIN"
            clientId="AUTH0_CLIENTID"
            profile="{{profile}}"></auth0-lock>

<script>
    var firebaseRequest = {
        api: "api", // This defaults to the first active addon if any or you can specify this
        scope: "openid profile"         // default: openid
    };

    document.querySelector('auth0-lock').addEventListener('loggedIn', function (profile) {
        console.log(profile);
        
        // try to get delegated access to Firebase
        document.querySelector('auth0-lock').delegate(firebaseRequest, function (result) {
            console.log(result)
        });
    });
</script>
```
