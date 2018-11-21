# Wikipedia Instant Search

[![Generic badge](https://img.shields.io/badge/Wikipedia-Opensearch-dodgerblue.svg?style=for-the-badge)](https://github.com/vinitshahdeo/coaching-website) 
[![Generic badge](https://img.shields.io/badge/Instant-Search-teal.svg?style=for-the-badge)](https://getbootstrap.com/) [![Generic badge](https://img.shields.io/badge/Auto-Complete-darkslatgray.svg?style=for-the-badge)](https://facebook.com/vinit.shahdeo/) 

#### An instant search application made using [Wikipedia Opensearch API](https://www.mediawiki.org/wiki/API:Opensearch).

This **instant search** is built using **Ajax** and **JQuery**. This application uses the Wikipedia Opensearch API. You can find it's documentation [here](https://www.mediawiki.org/wiki/API:Opensearch).

#### [Click to view live demo](http://codecombat.000webhostapp.com/wikipedia/)

- I've also implemented `search box` where it provides suggestions in a dropdown while typing the keyword in the search box.

- Replace the **`id`** or **`class name`** of the search box and you can implement the same in your exisiting project.


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

<hr>

Thank You!