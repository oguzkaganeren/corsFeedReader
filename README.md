# corsFeedReader 

Feed reader using fetch API, Only works on same domain, unless you set [cors](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) server side for external domains, only supports RSS format, ATOM and JSON will come in the future if i need them.

## Setting Cors
[Nginx](https://enable-cors.org/server_nginx.html)

[Apache](https://enable-cors.org/server_apache.html)

## Usage
```
const myFeed = new CorsFeedReader(".appendTo-selector", {
        fetchAPI: 'https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch'
        }, {
        feedUrl: "https://forum.manjaro.org/c/announcements/stable-updates.rss",
        dev: true,
        items: 5,
        template: `
            <div class="feed-item {{ category }}">
              <a href="{{ link }}">
                  <h2>{{ title }}</h2>
                </a>
              <summary class="description">
                {{ pubDate }} <br>
                {{ description }}
              </summary>
            `,
        beforeTemplate: function(content) {
            // do something with content              
        },
        afterTemplate: function(content) {
            // do something with content
        }
    });
```
