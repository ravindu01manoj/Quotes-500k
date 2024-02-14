# Quotes-500K

### Get Random Quote
```ts
const axios = require("axios");

function random(from, min = 0) {
    return Math.floor(Math.random() * from) + min
}

async function randomQuote() {
    const pageId = random(10)
    const fileId = pageId * 50 + random(50, 1)
    const file = (fileId < 10 ? "00" : fileId < 100 ? "0" : "") + fileId

    var url = "https://raw.githubusercontent.com/ravindu01manoj/Quotes-500k/master/page" + pageId + "/quotes-" + file + "-manoj.json"

    const res = await axios.get(url)
    const quotes = res.data.data

    console.log(quotes[random(quotes.length)])

}

randomQuote()

```



