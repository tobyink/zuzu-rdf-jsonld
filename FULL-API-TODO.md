# JSON-LD Full API TODO

This distribution initially targets JSON-LD 1.1 RDF parsing and
serialization: ToRDF and FromRDF. The following remain future work:

- Public compact, expand, and flatten API functions.
- Remote document loading over HTTP(S), including link headers, redirects,
  content-type handling, and remote context caching.
- HTML script extraction for JSON-LD documents embedded in HTML.
- JSON-LD framing.
- Full scoped context, protected term, and processing-mode diagnostics.
- Complete JSON-LD 1.0 compatibility mode.
- JSON Canonicalization Scheme support for JSON literal processing.
- Compressed CBOR-LD profile support.
