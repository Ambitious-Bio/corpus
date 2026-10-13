# Corpus by Ambitious Bio

**A donor-matched, whole-body human tissue multi-omic dataset, generated prospectively under a single protocol, for teams training biological AI.**

> No data files are hosted here. This README describes Corpus and how to request access. Corpus is licensed commercially by Ambitious Bio (Biological Data, Inc., Cambridge, Massachusetts). Sales: hello@ambitious.bio · Privacy and security: privacy@ambitious.bio

## What Corpus is

Corpus is built around a single design choice: measure many tissue sites from the same body, by quantitative mass-spectrometry proteomics, under one protocol. Each donor contributes about 30 tissue sites on average today, with a design target averaging more than 50. Every sample is profiled on the Thermo Fisher Orbitrap Astral and yields approximately 10,000–12,000 identified proteins. All tissue is recovered within 24 hours of death and in most cases far sooner. Collection is continuous.

Because every Corpus tissue comes with every other tissue from the same donor, the data supports questions that single-tissue and single-person resources cannot: how proteins distribute across a body, how that distribution varies from person to person, and how blood-borne signals relate to their tissue sources.

Full description and comparison with public references: https://ambitious.bio/corpus-comparison (Markdown: https://ambitious.bio/corpus-comparison.md)

## What is in Corpus today

- **Measurement:** Orbitrap Astral mass-spectrometry proteomics, approximately 10,000–12,000 proteins identified per tissue sample; depth varies by tissue.
- **Design:** about 30 tissue sites per donor on average (some donors more, some fewer), spanning systems, organs, structures and cell types.
- **Donors:** healthy, non-diseased; partial clinical records available.
- **With every measurement:** matched donor and specimen identifiers, tissue-site information, collection and processing metadata, assay protocols, and quality-control data.
- **Consent and privacy:** human-derived data is consented and de-identified at the source. Ambitious Bio does not attempt to re-identify donors and does not permit licensees to.

## What is planned (2027)

Beginning in 2027 the program adds, on the same material: short-read and long-read RNA sequencing on every tissue sample; 30× germline and 120× somatic whole-genome sequencing; H&E histopathology; single-cell and spatial transcriptomics on selected tissues; matched biofluids; full electronic health record linkage; and enrollment of both healthy and diseased donors. Ambitious Bio projects roughly 2,500 donors and 130,000 tissue samples in 2027. These are projections, not current figures.

## How Corpus compares with GTEx and the Human Protein Atlas

| | GTEx | Human Protein Atlas (tissue) | Corpus today | Corpus 2027 plan |
|---|---|---|---|---|
| Primary measurement | Bulk RNA-seq | Antibody immunohistochemistry | Orbitrap Astral MS proteomics | Proteomics + RNA-seq on every sample, plus WGS and histology |
| Quantitative protein abundance | Limited companion study (~200 samples, 32 tissues, 14 donors) | No | Yes | Yes |
| Tissue sites per donor | ~18 average (54 max) | Not donor-matched | ~30 average | >50 average |
| Donors per tissue | Varies widely | Typically 3 | Most donors, most sites | ~2,500 (projected) |
| Proteins identified | n/a (RNA) | ~15,000 mapped program-wide | ~10,000–12,000 per sample | ~10,000–12,000 per sample |
| Collection design | Retrospective, multi-site, 2010–2020 | Archival surgical/pathology | Prospective, single protocol, ongoing | Prospective, single protocol, ongoing |
| Tissue recovery | Post-mortem, variable interval | Surgical and post-mortem archives | Within 24 hours of death, usually much faster | Within 24 hours of death, usually much faster |
| Donor health | Mostly post-mortem, varied | Normal and cancer | Healthy, non-diseased | Healthy and diseased |
| Clinical history | Limited donor metadata | Limited | Partial records | Full EHR linkage |
| Access | Public | Public | Commercial license | Commercial license |

GTEx remains the larger resource by donor count today. To our knowledge, no other human tissue proteomics dataset samples as many tissue sites per donor as Corpus, and none is generated prospectively under a single protocol with continuous collection. Each Corpus sample yields approximately 10,000–12,000 identified proteins. In the 39 tissue types that Corpus and HPA share, adding Corpus expands the detected protein inventory in every one; the per-tissue counts are published as CSV at https://ambitious.bio/data/corpus-vs-hpa-detected-genes-per-tissue.csv.

References: GTEx Consortium, *Science* 369, 1318–1330 (2020), https://doi.org/10.1126/science.aaz1776 · Jiang et al., *Cell* 183, 269–283 (2020), https://doi.org/10.1016/j.cell.2020.08.036 · Uhlén et al., *Science* 347, 1260419 (2015), https://doi.org/10.1126/science.1260419 · Kim et al., *Nature* 509, 575–581 (2014), https://doi.org/10.1038/nature13302 · Wang et al., *Mol Syst Biol* 15, e8503 (2019), https://doi.org/10.15252/msb.20188503

### Corpus and the mass-spectrometry tissue maps

The closest technical peers to Corpus are the public MS proteome maps of healthy human tissue: the Human Proteome Map (Kim et al., 2014; 30 samples, each pooled from three individuals; 17,294 genes with protein evidence), the 29-tissue atlas (Wang et al., 2019; one specimen per tissue from different individuals; ~11,000 protein groups per tissue with deep fractionation; PRIDE PXD010154), and the GTEx proteomics study (Jiang et al., 2020; 201 samples, 32 tissues, 14 donors). Corpus keeps the GTEx study's within-donor design and runs it continuously: about 30 sites per donor on average, prospective, single protocol, Orbitrap Astral, roughly 10,000–12,000 proteins per sample. Its per-sample depth is comparable to the 29-tissue atlas's fractionated per-tissue depth, reached in each individual sample for each donor.


## Data structure (illustrative)

Deliveries are organized per release and per cohort. Each protein quantification is linked to a specimen, each specimen to a donor and a tissue site, and each donor to the clinical and collection metadata available for that release. The file `sample_metadata_example.csv` in this repository shows the *shape* of the specimen-level metadata with placeholder values; it is not real data, and the delivered schema is specified in the documentation for each release.

Illustrative specimen-level fields: `donor_id`, `specimen_id`, `tissue_site`, `tissue_system`, `collection_to_processing_hours`, `assay_platform`, `assay_protocol_version`, `proteins_identified`, `qc_status`, `release_id`.

## Intended uses

- Training and evaluating biological foundation models and tissue-level protein-abundance models.
- Mapping target expression and abundance across organs; prioritizing tissues for validation and safety studies.
- Relating biofluid signals to molecular abundance in specific tissues.
- Learning relationships between genetic variation, RNA expression and protein abundance across tissues (with the 2027 modalities).

## Access and licensing

Corpus is licensed for research and AI model training under a written commercial license from Ambitious Bio, which generates and owns the experimental data with full rights to license and sublicense it. Write to hello@ambitious.bio, or use the request form on the Hugging Face dataset page: https://huggingface.co/datasets/ambitious-bio/corpus. No data is distributed through GitHub or Hugging Face.

## Citation

If you reference Corpus in a publication, cite the dataset as:

> Ambitious Bio. *Corpus: a donor-matched, whole-body human tissue proteomics dataset.* Biological Data, Inc., Cambridge, MA. https://ambitious.bio/corpus-comparison (accessed YYYY-MM-DD).

```bibtex
@misc{ambitiousbio_corpus,
  title        = {Corpus: a donor-matched, whole-body human tissue proteomics dataset},
  author       = {{Ambitious Bio}},
  year         = {2026},
  howpublished = {\url{https://ambitious.bio/corpus-comparison}},
  note         = {Biological Data, Inc., Cambridge, MA. Commercial license.}
}
```

## About Ambitious Bio

Ambitious Bio (Biological Data, Inc.) is a Cambridge, Massachusetts company that produces Corpus, a large-scale multi-omic dataset from consented human tissue, generated prospectively under consistent protocols, for teams training the next generation of biological AI.

Website: https://ambitious.bio · Data sheet: https://ambitious.bio/corpus · Trust Center: https://trust.ambitious.bio · X: [@AmbitiousBio](https://x.com/AmbitiousBio)

*Card last updated: October 2026. Corpus™ is a trademark of Biological Data, Inc.*
