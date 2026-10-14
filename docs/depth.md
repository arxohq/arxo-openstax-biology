# Structural depth of the Biology 2e slice

This delivery uses the unchanged common `boundaries.depth` classifier and its existing `openstax_section` convention. The adapter collects inputs, verifies SHA-256 before parsing and aggregates the original classification; it is not another classifier.

Eight publisher section headings are declared in the exact retained text snapshots. Literal titles exclude numerical examples and figures from the denominator. Each publication uses its own source hash and exact edition. Imported nodes and foreign editions are excluded. Source-accounting scope covers fragment-bearing sections; structural denominator still comes from every declared heading.

EXECUTABLE requires an anchored deriving rule. The measure does not establish complete section/book coverage, scientific validation of assumptions or successful execution for every input. Per-unit rows preserve counts, unresolved/other-edition anchors, unmeasured publications and unanchored helpers. Technical/teaching dependencies lack a textbook division; the NCBI HTML source has a different unit and remains explicitly not_measured.

Run `python3.12 tools/measure_depth.py --check` and the six addressed `tools/test_section_depth.py` regressions. These commands require only Python 3.12's standard library, no private runtime/corpus.

Access for free at [OpenStax Biology 2e](https://openstax.org/books/biology-2e/pages/1-introduction). OpenStax/Rice University and content contributors; textbook content and adaptations: [CC BY-NC-SA 4.0](../licenses/CC-BY-NC-SA-4.0.txt).
