swagger2pdf
==============

Generate a PDF document from a Swagger spec using [Swagger2Markup](https://github.com/Swagger2Markup/swagger2markup) and [Asciidoctor](http://asciidoctor.org/).

Usage
------

Put a `swagger.yaml` file in the current directory and run following commands:

```
docker run --rm -v $(pwd):/in -v $(pwd)/out:/out tozny/swagger2pdf 
```