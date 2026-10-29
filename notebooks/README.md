# Notebooks

- `templates/` starting points for analysis work; copy one and fill in the parameters cell.
- `examples/` worked examples using the files in `tests/data/`.

Put case parameters (file paths, CT/VT ratios, relay settings) in a single cell at
the top of each template, and clear outputs before committing.

Run the notebooks as tests with:

```bash
uv run pytest --nbmake notebooks/
```
