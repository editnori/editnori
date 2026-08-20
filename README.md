<p align="center">
  <picture>
    <source media="(max-width: 600px)" srcset="./assets/ctakes-usdhub-mobile.svg" />
    <img src="./assets/ctakes-usdhub.svg" width="100%" alt="cTAKES USDHUB clinical NLP. In the fictional note, No fever becomes a reviewable concept row with span 85 to 90, fictional candidate DEMO-C002, and assertion negated because cTAKES keeps the source words and adds coded fields around them. Batch 1 completed 1,708,157 notes." />
  </picture>
</p>

<p align="center">
  <a href="https://ctakesusd.dev/clinical-basics/">Clinical basics</a>&nbsp;&nbsp;
  <a href="https://ctakesusd.dev/batch-1/">Batch 1</a>&nbsp;&nbsp;
  <a href="https://codeberg.org/editnori/Ctakes_USD">Source</a>
</p>

## Clinical NLP with the source attached

In the fictional fixture, `No fever` stays attached to characters 85–90 while cTAKES adds fictional candidate `DEMO-C002` and assertion `negated`. The row opens back to those exact words, so a reviewer can inspect what the extractor saw. It does not rewrite the note or establish that the patient has fever.

The default recipe structures sections, sentences, and tokens, then matches spans to dictionary candidates. Word-sense disambiguation (WSD) is the step that ranks several meanings attached to the same span while keeping every candidate. Drug named-entity recognition (Drug NER) is the step that extracts medication dose, route, frequency, and duration. Context follows, then writers return the results. WSD remains clinically `not-evaluated`.

After the manifest is complete, the sanity report passes, and both CSVs match their SQLite views, the routine handoff is exactly `concepts.csv` and `drugs.csv`. SQLite, receipts, manifests, and logs stay local for review and recovery.

[Batch 1](https://ctakesusd.dev/batch-1/) processed 1,708,157 notes in 9 hours and 47 minutes. The 1,708,157 count measures input notes, while 142,891,564 concept rows and 11,004,425 medication candidate rows measure separate output tables; the row tables overlap by source note and do not partition the input count or each other. These are extraction inventories, not validated phenotypes or a clinical-accuracy result.
