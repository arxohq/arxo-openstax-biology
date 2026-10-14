# Reproduce the selected consumer worlds

Use the exact released CLI `@arxo/cli@0.2.5`, `law.core/0.2.11` and Python 3.12. `registry/package` holds native own IR; `registry/world` holds linked dependencies. Historical dependency IR, where it existed, is retained under `registry/original`; new models have no claimed historical IR. The source pin records captured working-tree bytes separately from native outputs. Raw SHA-256, native artifact/content hashes and evaluation resultHash are distinct identities.

Rebuild a selected package in a disposable copy. Keep generated caches and contexts out of the release allowlist:

```sh
law engine imports-context packages/openstax.biology_genetics --clir registry/package > imports.json
law engine lower packages/openstax.biology_genetics --imports imports.json --exact-release law.core/0.2.11 > lowered.json
law engine canon lowered.json
```

Save the canonical own IR under a new output name. Use `law engine lock <package-root> --clir registry/package --write` and `law engine link <own-ir> --package <package-root>`. Vendored dependency IR and exact versions are included. To capture a suite, pass a JSON array of its paths to `law engine lower-test <list.json> --lawtest-list --program <world-ir> --imports imports.json`. The explicit context is necessary for qualified foreign assertions such as bio.codon::translation_table. Preserve each native step's canonical case/query/expectations and run `law eval` on the resulting request.

Source capture reused the existing OpenStax extractor. Exact section UUIDs, URLs, retrieval times, source sizes/hashes, raw-page hashes and extractor hash are in sources/**/manifest.json. Raw HTML wrappers remain outside the public archive; retained extracted text is not silently rewritten to repair mathematical layout.

The `bio.codon` 0.1.1 API revision exports Transcript, Codon and AminoAcid, already present in public relation signatures. Its rule bodies, code assignments and publisher source bytes remain unchanged. SECIS is still a private case input; this kit demonstrates selected-table codon meanings, not cross-package recoding. Original 0.1.0 IR is retained. Native suites of this revised dependency passed separately.

The release uses the maintained `canon_publication.py` and an exact `publication.toml` allowlist. Export a fresh artifact directory, verify its inventory and build the archive from those exact files; never copy Git history, caches, node_modules or temporary deps/*.source inputs. New sources/cases need new pins and addressed checks. Do not implement formulas or biological interpretation in preparation scripts.

Access for free at [OpenStax Biology 2e](https://openstax.org/books/biology-2e/pages/1-introduction). OpenStax/Rice University and content contributors; textbook content and adaptations: [CC BY-NC-SA 4.0](../licenses/CC-BY-NC-SA-4.0.txt).
