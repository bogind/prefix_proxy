## QGIS Prefix Proxy URL

Used for adding a **prefix** proxy to specific URLs, i.e. their addresses are built in the following way:

`[https://proxy.server.url/proxy]?[https://the.service.you/need/probably/arcgis/rest/services]?[url_params=their values]`


This is needed because QGIS allows setting a global proxy, but not a prefix proxy, and not for specific URLs. For Layers that
need other URL parameters (like OGC WMS/WFS/etc. or ArcGIS REST), the question mark (?) in the middle of the URL causes QGIS to
drop the necessary second question mark and construct the other URL parameters poorly.

Without the second question mark, adding these types of layers is impossible,
It's also really annoying trying to get their data,
The script adds a simple prefix proxy to all requests which start in the handler's URL.

