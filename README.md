# RemoteJSON

## How it works
```javascript
// For app update
fetch('https://virejdasani.github.io/RemoteJSON/Geniemoji/index.html')
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
