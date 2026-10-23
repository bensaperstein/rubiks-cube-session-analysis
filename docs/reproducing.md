# Viewing and reproducing the work

## View saved outputs

Open notebook links from the README to inspect saved figures, tables and narrative. Download existing `report.html` and `code.html` to view them locally. No dataset is needed to read saved outputs.

## Suggested environment

Use Python 3.12 or newer; some original f-string syntax requires 3.12. Regression notebooks were saved with Python 3.13.5.

```bash
python -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
python -m ipykernel install --user --name cube-analysis --display-name "Cube analysis"
jupyter lab
```

On Windows use `.venv\Scripts\activate`. Select **Cube analysis** in Jupyter. Original conda kernel names need not exist on another computer. Requirements are inferred compatibility ranges, not an original environment lockfile; a complete rerun has not been verified.

## Input

Original code reads `cstimer_data.txt`, a JSON-formatted csTimer export containing `session36`. The full export is not committed and includes other personal sessions. Uploading the entire export is unnecessary for this portfolio.

With the original data available locally, launch Jupyter from the repository root and set each notebook’s `filename` to its local path. Different exports will not necessarily reproduce saved sample counts. The course stages use different snapshots.

## Execution constraints

- Run exploratory `code.ipynb` top to bottom with the earlier snapshot.
- Original `report.ipynb` depends on variables created by the code notebook; it is not self-contained in a fresh kernel. Read saved outputs, or explicitly run the code notebook in the same kernel before report cells.
- Each regression notebook includes its loading/parser cell and modeling sequence. Run either top to bottom with the later snapshot.
- The regression report references `virtualcubekeymap.png`, absent from the supplied folder and not bundled here.
- Portfolio context notes and a portable kernel selector were added to regression notebooks; analytical code and outputs are preserved.
- No fresh data-dependent run or corrected validation experiment was completed during packaging. Read [validation notes](methods-and-limitations.md) before interpreting original scores.
