# DEDL-O – Data Ecosystem Description Language Ontology

DEDL-O is an OWL ontology for describing the technical architecture of data ecosystems, their processes and the connection between both. Its integration layer states which process step calls which API endpoint and how data is mapped between them, which neither architecture nor process vocabularies can express on their own.

DEDL-O is the ontology of DEDL, the Data Ecosystem Description Language, whose information model was published at [WorldCIST 2026](https://link.springer.com/chapter/10.1007/978-3-032-32026-1_7).

| | |
|---|---|
| Namespace | `https://w3id.org/dedl#` (prefix `dedl`) |
| Current version | 1.0.0, <https://w3id.org/dedl/1.0.0> |
| Previous version | 0.1, <https://w3id.org/dedl/0.1> (not compatible with 1.0.0) |
| Documentation | <https://w3id.org/dedl> |
| JSON-LD context | <https://w3id.org/dedl/context.jsonld> |
| License | [CC BY 4.0](LICENSE) |

## Structure

DEDL-O describes a data ecosystem in three layers of one graph:

- **Architecture layer:** the technical elements of an ecosystem (`dedl:TechnicalDataEcosystemElement` and subclasses such as `dedl:API` or `dedl:IdentityProvider`), their directed dependencies (`dedl:dependsOn`) and who operates them (`dedl:operatedBy`).
- **Process layer:** processes, service tasks, gateways and sequence flows, reused from the BPMN-based ontology [BBO](https://www.irit.fr/recherches/MELODI/ontologies/BBO/index-en.html), with declared input and output sets.
- **Integration layer:** which service task invokes which endpoint (`dedl:invokesEndpoint`) and how each request parameter is filled (`dedl:ParameterMapping`).

Further reused vocabularies: schema.org, DCAT, W3C Web of Things (hypermedia controls and JSON schema), DMN FEEL for conditions, Dublin Core terms.

## Using DEDL-O

The ontology resolves by content negotiation: `https://w3id.org/dedl` returns the HTML documentation for browsers and Turtle, RDF/XML, JSON-LD or N-Triples for RDF clients.

```bash
curl -L -H "Accept: text/turtle" https://w3id.org/dedl
```

## Repository content

| Path | Content |
|---|---|
| `dedl.ttl` | the ontology (source of truth) |
| `docs/` | documentation of the current version, served at https://w3id.org/dedl |
| `docs/1.0.0/`, `docs/0.1/` | documentation of each released version |
| `docs/context.jsonld` | JSON-LD context with short names for all `dedl:` terms |

The documentation is generated with [WIDOCO](https://github.com/dgarijo/Widoco) 1.4.25. Introduction, references and namespace table are written by hand.

## Citation

> Lennart Klöpper, Jiahang Chen. Data Ecosystem Description Language Ontology (DEDL-O). Version 1.0.0. https://w3id.org/dedl/1.0.0

## License

The DEDL vocabulary (`dedl.ttl`) and its documentation are licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), see [LICENSE](LICENSE).
Third-party components bundled with the generated documentation in `docs/resources/` and `docs/webvowl/` (e.g. jQuery, D3, WebVOWL) remain under their own licenses.
