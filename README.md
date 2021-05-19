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

Sample JSON:
```json
{"updateAvailable":"yes","updateVersion":"1.0.1","updateText":"An update is available","updateURL":"https://github.com/virejdasani/Geniemoji/releases/tag/v1.0.0"}
```
