.. _pipelinestoc:

********************
Processing Pipelines
********************
--------
Overview
--------
The power of Graylog is the ability to ingest almost any type of log data, do almost
anything you want to it, and then store it in any way you want.

Graylog’s Processing Pipelines allow users to route, blacklist, modify
or enrich messages as they flow through Graylog. 

What that means is, if you want to parse, compare, change, convert, add to, delete from or drop a message, Pipelines are the tool to use.

Examples of possible transformations include:

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





Pipelines are the central concept tying together the processing steps applied to your messages.

Pipelines contain rules and can be connected to one or more streams, enabling fine-grained control over which processing steps are performed on a given type of message.

The language used for pipeline rules is very simple and can be extended by functions, which are fully pluggable. Processing rules are simply conditions followed by a list of actions, and do not have control flow by themselves.  To control the order in which processing rules are applied, pipelines utilize stages.

Each Stage contains one or more rules. Pipelines and rules are not configuration for pre-built code, as extractors and stream rules are, but are instead represented as code. They are similar to `Drools rules <https://www.drools.org/>`. This gives them great flexibility and extensibility, and enables a powerful ability to customize Graylog’s
message processing behavior.



**Pipeline structure**


Internally pipelines are represented as code. Let's have a look at a simple example and understand what each part does::

    pipeline "My new pipeline"
    stage 1 match all
      rule "has firewall fields";
      rule "from firewall subnet";
    stage 2 match either
      rule "geocode IPs";
      rule "anonymize source IPs";
    end

This code snippet declares a new pipeline named ``My new pipeline``, which has two stages.





The following pages introduce the concepts of stages, rules, stream connections, built-in functions, and examples of how to build processing pipelines. 

.. toctree::
   :titlesonly:

   pipelines/stages
   pipelines/stream_connections
   pipelines/rules
   pipelines/functions
   pipelines/usage
