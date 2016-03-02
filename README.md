# Leaflet Tag Filter Button
Adds tag filter control for marker to LeafLet. 

Required [Leaflet.EasyButton](https://github.com/CliffCloud/Leaflet.EasyButton)

Check out the [demo](https://leaflet-tag-filter-button.herokuapp.com)

Usage
-----

Simple usage :

If you want to auto filter when filter popup is closed. Your markers must be contain tags option.
For example:

```

var map = L.map('map');

var fastMarker = L.marker([50.5, 30.5], { tags: ['fast'] }).addTo(map); 
var slowMarker = L.marker([50.5, 30.5], { tags: ['slow'] }).addTo(map);
var bothMarker = L.marker([50.5, 30.5], { tags: ['fast', 'slow'] }).addTo(map);

L.tagFilterButton({
	data: ['fast', 'slow']
}).addTo( map );

```


Set data from external url/ajax :


```

var map = L.map('map');
L.tagFilterButton({
	ajaxData: function(callback) {
		$.get('https://leaflet-tag-filter-button.herokuapp.com/data', function(data)) {
			callback(data);
		}
	}
}).addTo( map );


```

Selection complete callback

```

var map = L.map('map');
L.tagFilterButton({
	data: function(callback) {
		$.get('https://leaflet-tag-filter-button.herokuapp.com/data', function(data)) {
			callback(data);
		}
	},
	onSelectionComplete: function(tags) {
		console.log('selected tags are', tags);
	}
}).addTo( map );


```


Authors
-------

* Mehmet Aydemir