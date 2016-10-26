#World Maps Add-on for Splunk Enterprise

This is Work in Progress. 

The add-on urrently supports looking up counties in the following countries:
* Denmark
* Norway

How to use this:
<pre>
| makeresults | eval latitude="59.773147" | eval longitude="10.800195" |lookup geo_no_counties latitude longitude | stats count by featureId | geom geo_no_counties
</pre>

<pre>
index=* sourcetype=csv_opendata | eval latitude=lat | eval longitude=lon | lookup geo_dk_counties latitude longitude | stats count by featureId | geom geo_dk_counties
</pre>

Attributions:
* Denmark: http://www.microformats.dk/2009/10/04/danmarks-administrative-geografiske-inddeling-dagi-kml-version/
* Norway: http://www.norgeo.no/Generer_KML.html
