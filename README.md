# rdf-jsonld

JSON-LD, YAML-LD, and CBOR-LD parser and serializer classes for the
ZuzuScript `rdf` distribution.

This trial distribution provides:

- `JsonLdParser`, `YamlLdParser`, `CborLdParser`, and
  `CompressedCborLdParser`.
- `JsonLdSerializer`, `YamlLdSerializer`, `CborLdSerializer`, and
  `CompressedCborLdSerializer`.
- Shared JSON-LD 1.1 ToRDF and FromRDF helpers.
- Author-gated tests using the official W3C JSON-LD API test suite.

The YAML-LD and CBOR-LD classes use the same JSON-LD data model as
JSON-LD itself, with `std/data/yaml` and `std/data/cbor` handling the
surface syntax. The compressed CBOR-LD classes use the CBOR-LD tag
profile and registry entry 1 by default.

## Example

```zzs
from rdf/parser/jsonld import JsonLdParser;
from rdf/serializer/jsonld import JsonLdSerializer;

let quads := ( new JsonLdParser() ).parse_string("""
{
  "@context": {"ex": "http://example.com/"},
  "@id": "ex:s",
  "ex:p": "value"
}
""", base: "http://example.com/doc");

say( ( new JsonLdSerializer( pretty: true ) ).serialize(quads) );
```

Parsers compose the `RdfParser` trait from `rdf/parser` and support
`parse_string`, `parse_file`, `parse_lines`, and `parse_chunks`. They
accept the same `base` and `into` options as the main RDF parsers.

Serializers compose the `RdfSerializer` trait from `rdf/serializer` and
support `serialize` and `serialize_each`.

## Notes

See `FULL-API-TODO.md` for JSON-LD API features outside this first RDF
parser/serializer release.
