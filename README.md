# Wikipedia-Instant-Search
#### An instant search application made using Wikipedia Opensearch API.

This **instant search** is built using `ajax` and `JQuery`. This application uses the Wikipedia Opensearch API. You can find it's documentation [here](https://www.mediawiki.org/wiki/API:Opensearch).

#### [View live demo](http://codecombat.000webhostapp.com/wikipedia/)

- I've also implemented `search box` where it provides suggestions in a dropdown while typing the keyword in the search box.

- Replace the `id` or `class name` of the search box and you can implement the same in your exisiting project.

```javascript

$(".searchbox").autocomplete({
    source: function(request, response) {
        $.ajax({
            url: "http://en.wikipedia.org/w/api.php",
            dataType: "jsonp",
            data: {
                'action': "opensearch",
                'format': "json",
                'search': request.term
            },
            success: function(data) {
                response(data[1]);
            }
        });
    }
});

```

### Useful links

- [JQuery Autocomplete UI](http://jqueryui.com/autocomplete/)
- [Wikipedia Opensearch API](https://www.mediawiki.org/wiki/API:Opensearch)