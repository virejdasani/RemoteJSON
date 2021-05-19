# RemoteJSON

## How it works
- Make a folder with app name
- Add JSON in the `appname/index.html` file
- Add this to your javascript
```javascript
// For app update
fetch('https://virejdasani.github.io/RemoteJSON/APPNAME/index.html')
    .then((response) => {
        return response.json()
    })
    .then((data) => {
        if (data.updateAvailable == "yes") {
            alert("yes")
        }
    })
    .catch((err) => {
        console.log(err)
    })
```
