# LoveDB

LoveDB is a new kind of database.

It's fully-based on standardized HTTP, which means no wheels were re-invented
in the writing of this spec. Authentication, encryption, caching, and even
transaction semantics can all be layered in via HTTP.

Data is input and output as JSON. HTTP paths refer to loci in a single, global
JSON object tree. Here's a very simple example:

    « GET /
    » {"a": 123}
     
    « GET /a
    » 123

HTTP operations modify or retrieve parts of the object tree:

    « PUT /b
    « 456
     
    « GET /
    » {"a": 123, "b": 456}
     
    « DELETE /a
     
    « GET /
    {"b": 456}
