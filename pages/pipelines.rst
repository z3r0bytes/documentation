.. _pipelinestoc:

********************
Processing Pipelines
********************

The power of Graylog is the ability to ingest almost any type of log data, do almost
anything you want to it, and then store it in any way you want.

Graylog’s Processing Pipelines allow users to route, blacklist, modify
or enrich messages as they flow through Graylog. 

What that means is, if you want to parse, compare, change, convert, add to, delete from or drop a message, Pipelines are the tool used to do it.

Examples of possible transformations include, but are not limited to:

* Threat Intelligence Lookups
* Event Parsing
* Stream routing (Add to or remove from streams)
* Timestamp modifcation
* Value, type and format conversions
* DNS lookups
* Drop message
* WHOIS lookups
* Geo-location lookups
* Abbreviation
* Change string cases (uppercase, lowercase, capitalization, etc.)
* Concatenation
* Splitting
* Rename field
* Create field
* Remove field
* Clone message
* 

Pipelines contain one or more stage(s). Each Stage contains one or more rules. Pipelines and
rules are not configuration for pre-built code, as extractors and stream rules are, but are
instead represented as code. They are similar to `Drools <https://www.drools.org/>' rules. This gives them great
flexibility and extensibility, and enables a powerful ability to customize Graylog’s
message processing behavior.


The language used for pipeline rules is very simple and can be extended by functions,
which are fully pluggable.

The following pages introduce the concepts of pipelines, rules, stream connections, and the built-in functions.

.. toctree::
   :titlesonly:

   pipelines/pipelines
   pipelines/rules
   pipelines/stream_connections
   pipelines/functions
   pipelines/usage
