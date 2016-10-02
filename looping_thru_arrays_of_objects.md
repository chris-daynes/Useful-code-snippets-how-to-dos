#How to loop through arrays within Objects with jQuery.


```
$(document).ready(function(){

  $.getJSON('main.json', function(info) {

    var output = '';
    for (var i = 0; i < info.links.length; i++) {
      for(var key in info.links[i]) {
        if(info.links[i].hasOwnProperty(key)) {
        output += '<li>' + '<a href ="' + info.links[i][key] + '">' + key +'</a></li>';
      }//check hasOwnProperty
    }//loop for each key in object
  }//loop for each array element

    var update = document.getElementById("links");
    update.innerHTML = output;
  });
});
```

The json file being accessed is the "main.json" file.

```
{
  "full_name": "Chris Daynes",
  "title": "Computer Programmer",
  "links": [
    { "blog": "http://iviewsource.com" },
    { "facebook": "http://facebook.com" },
    { "youtube": "http://www.youtube.com" },
    { "podcast": "http://feeds.feedburner.com"},
    { "twitter": "http://twitter.com"}
  ]
}

```
