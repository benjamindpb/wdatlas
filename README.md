# Wikidata Atlas 🗺
[Wikidata Atlas](https://wdatlas.dcc.uchile.cl/) is a platform that allows Wikidata entities that have geographic coordinate properties to be displayed on a world map, such as museums, stadiums, destroyed buildings or structures, nuclear weapons tests, among many others.

Below are links to repositories related to this project:

## Dump preprocessing
Before starting the development of the Wikidata Atlas project, a preliminary evaluation of the Wikidata data was carried out to see the feasibility of its use as a potential data source. For this, a pre-processing of its database ([truthy dump](https://www.mediawiki.org/wiki/Wikibase/Indexing/RDF_Dump_Format#Truthy_statements)) was carried out, focused on obtaining types of georeferential entities. Subsequently, an evaluation of the performance of the generation of a world map with georeferenced instances using different libraries was carried out. Finally, an analysis of the types found was carried out to see their distribution.

[https://github.com/benjamindpb/wikidata-preprocessing](https://github.com/benjamindpb/wikidata-preprocessing)

## System Architecture
The project architecture is the classic client-server model. For the backend, an API was developed using the Python Flask framework, on the other hand, the frontend was developed using the React.js Javascript framework.

### Flask API
The API that was created is fed from a JSON file generated after preprocessing and parsing the Wikidata dump (**not to be confused with the above preprocessing, however its implementation is very similar**). This will be vital for the implementation of the autocompletion of the system. Also, to obtain information on the instances of georeferenced types, the [Wikidata Query Service](https://query.wikidata.org/) endpoint was used to execute a SPARQL query that obtains all the instances of a given type with information such as his label, the description, coordinate location, referencial image and country.


[https://github.com/benjamindpb/flask-api](https://github.com/benjamindpb/flask-api)

### Web Interface
As previously mentioned, the React.js framework was used to develop the system interface. In addition, Bootstrap was used to improve the visual aspect of the different components of the system interface.
For the generation of the world map, the Leaflet library was used, specifically the npm package [react-leaflet](https://react-leaflet.js.org/) for the use of React components.

[https://github.com/benjamindpb/react-front-v2](https://github.com/benjamindpb/react-front-v2)


---
[![Alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Wikidata_Stamp_Rec_Dark.svg/200px-Wikidata_Stamp_Rec_Dark.svg.png "Powered by Wikidata")](https://www.wikidata.org/wiki/Wikidata:Main_Page)

