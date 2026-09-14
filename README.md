# AI Risk and Mitigation Datasets

Supplementary data for the Research Master's thesis *"[Thesis Title Here]"*, submitted by Robert Verbeeten (MSc Business Informatics, Utrecht University, 2026), supervised by Prof. dr. Fabiano Dalpiaz and Dr. Joris Hulstijn.

This repository contains the cleaned risk and mitigation databases used as the analytical framework throughout the thesis: to train and evaluate an automated risk-mitigation mapping classifier (RQ1), to code organizational AI ethics statements (RQ2), and to identify mitigations relevant to documented AI incidents (RQ3).

## Contents

| File | Description | Rows |
|---|---|---|
| `risk_database.csv` | Cleaned risk database, derived from the MIT AI Risk Repository | `<N>` |
| `mitigation_database.csv` | Cleaned mitigation database, derived from the Saeri et al. mitigation database | `<N>` |

## Provenance and preprocessing

### Risk database

Derived from the [MIT AI Risk Repository](https://airisk.mit.edu/) (Slattery et al.). The original repository's risk entries were reduced from 2,574 to 2,500 through paper-level filtering, then further consolidated to 1,111 unique risks through evidence aggregation across duplicate or overlapping entries.

Columns:

| Column | Description |
|---|---|
| `Paper_ID` | Identifier of the source paper/review this risk entry was drawn from |
| `Cat_ID` | Numeric identifier of the risk category |
| `SubCat_ID` | Numeric identifier of the risk subcategory |
| `Risk_ID` | Unique identifier for the risk |
| `Domain` | Risk domain (RD1–RD7), per the MIT AI Risk Repository taxonomy |
| `Sub-domain` | Finer-grained subdomain within the risk domain |
| `num. combined evidences` | Number of source evidence entries merged into this row during preprocessing |
| `Category level` | Taxonomy level (domain- or subdomain-level) at which this entry is defined |
| `Risk category` | Risk category name |
| `Risk subcategory` | Risk subcategory name |
| `Description` | Risk description text |
| `Additional ev.` | Supplementary evidence or supporting text associated with the risk |

### Mitigation database

Derived from the Saeri et al. mitigation database (830+ mitigation strategies). Cleaning involved generating definitions for entries missing one (via Gemini 2.5 Flash), semantic duplicate detection (SBERT `all-MiniLM-L6-v2`, similarity threshold 0.75), and graph-based clustering (NetworkX) to consolidate near-duplicate strategies.

Columns:

| Column | Description |
|---|---|
| `Mitigation_ID` | Unique identifier for the mitigation strategy |
| `Action Name` | Short name of the mitigation strategy |
| `Action Definition` | Full definition of the mitigation strategy |
| `MitigationCode` | Mitigation category code (MC1–MC4) |

## Citing this data

If you use this data, please cite the thesis:

```bibtex
@mastersthesis{verbeeten2026,
  author = {Verbeeten, Robert},
  title  = {[Thesis Title Here]},
  school = {Utrecht University},
  year   = {2026},
  type   = {MSc Thesis, Business Informatics}
}
```

Please also cite the original source datasets this repository builds on:

- Slattery, P., Saeri, A. K., Grundy, E. A. C., Graham, J., Noetel, M., Uuk, R., Dao, J., Pour, S., Casper, S., & Thompson, N. *The AI Risk Repository: A Comprehensive Meta-Review, Database, and Taxonomy of Risks From Artificial Intelligence.*
- Saeri, A. K., George, S. L., Graham, J., Lacarriere, C. D., Slattery, P., Noetel, M., & Thompson, N. *Mapping AI Risk Mitigations: Evidence Scan and Preliminary AI Risk Mitigation Taxonomy.*

## License

[Specify a license here — e.g., CC BY 4.0 for the data itself. Check the license terms of the MIT AI Risk Repository and the Saeri et al. mitigation database before redistributing derived data, since this repository's license can't override theirs.]

## Contact

Robert Verbeeten — r.f.y.verbeeten@students.uu.nl
