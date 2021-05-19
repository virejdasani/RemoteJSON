# RemoteJSON

## How it works
- Make a folder in this repo with app name
- Add JSON in the `APPNAME/index.html` file
- Add this to your javascript
```javascript
// For app update, if an update is available, the updateAvailable in the RemoteJSON repo will be updated to yes. That will result in the code below being executed
fetch('https://virejdasani.github.io/RemoteJSON/Geniemoji/index.html')
    .then((response) => {
        return response.json()
    })
    .then((data) => {
        // If update is available, and this version is not the latest one, the update div will no longer be empty. It will have the following HTML
        if (data.updateAvailable == "yes" && data.latestVersion !== "1.0.1") {
            document.getElementById("update").innerHTML = `
                <div id="update">
                    ${data.updateText}
                    Download update <!-- (${data.latestVersion}) --> <a href="${data.updateURL}" target="_blank">here</a>
                </div>
            `
        }
    })
    .catch((err) => {
        console.log(err)
    })
```

Sample JSON to add to `index.html`:
```json
{"updateAvailable":"no","latestVersion":"1.0.2","updateText":"An new version of Geniemoji is available!","updateURL":"https://github.com/virejdasani/Geniemoji/releases/tag/v1.0.2"}
```

### To open in external browser with electron
- `$ npm install open`
- Add to main.js:
```javascript
const open = require('open')

// CreateWindow function()

    // This opens all links with `target="_blank"` in external browser
    window.webContents.on('new-window', function (event, url) {
        event.preventDefault()
        open(url)
    })
```
