Neo Doc
========

This repository contains a Neo4j graph database of <a href='http://docgraph.org'>DocGraph</a>.


Database
========

* Organizations -[:PARENT_OF] - Providers -[:SPECIALTY]- Specialties
* Providers -[:LOCATED_IN]-Locations

Nodes:
--------

* Organizations - Fields: name
* Specialties - Fields: name, code
* Providers - Fields: name, npi, type, address_first_line, address_second_line, address_city_name, address_state_name, address_postal_code, address_country_code, telephone_number, fax_number
* Locations - address_city_name, address_state_name, address_country_code

Edges:
--------

* PARENT_OF - Between Providers and Organizations
* SPECIALTY - Between Providers and Specialties
* LOCATED_IN - Between Providers and Locations
* REFERRED - Between Providers, Fields: times


Indexes:
--------

* Organization - Fields: name
* Specialty - Fields: name, code
* Provider - Fields: name, address_postal_code, telephone_number, npi
* Location - Fields: address_city_name, address_state_name, address_country_code


Instructions
========

It is available on Dropbox at [neo_doc_v1.tar.gz](https://dl.dropboxusercontent.com/u/57740873/neo_doc_v1.tar.gz).

It contains a graph.db directory that goes in neo4j/data/.


The file neo_doc.commands contains a "how to" for building this data yourself.


Clone the Neo4j Batch Import Utility

    git clone git://github.com/jexp/batch-import.git

Download and install Neo4j or use the neography

    bundle install
    rake neo4j:install

Follow the "Import to Neo" section in the neo_doc.commands file.


Licenses
========

Licensed under the Attribution-ShareAlike 3.0 Unported (CC BY-SA 3.0) unless otherwise noted.








