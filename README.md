# psp

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)

psp is a Python library for power system protection.

| Subpackage     | Contents                                                        |
| -------------- | --------------------------------------------------------------- |
| `psp.core`     | Core calculations: phasors, symmetrical components, impedances  |
| `psp.dsp`      | Digital signal processing: DFT, true RMS                        |
| `psp.comtrade` | Loading channels from COMTRADE records                          |
| `psp.plotting` | Protection plots with matplotlib (RX, phasor, time series, ...) |
| `psp.relay`    | Functions for specific relay types (REx670, 7SA8x)              |

## Disclaimer
**This package is currently under active development and may undergo significant changes. Features may be incomplete, unstable, or subject to breaking modifications without notice.**

## Installation

Use the package manager [uv](https://docs.astral.sh/uv/) to install psp.

```bash
uv pip install "git+https://github.com/U-RxI/psp"
```

## Usage

```python
from psp.core import P2R, symmetrical_components
from psp.plotting import RXplot

myplot = RXplot('RX plot with phasors')
myplot.add_phasor(value=1+0j, color='Red', name='U1')
myplot.add_phasor(value=-0.5-0.866j, color='Blue', name='U2')
myplot.add_phasor(value=-0.5+0.866j, color='Green', name='U3')
myplot.show()
```

## Development

```bash
uv sync                 # installs psp in editable mode plus dev tools
uv run pytest           # run the tests
uv run jupyter lab      # work on notebooks against the local source
```

Repository layout:

- `src/psp/` the library
- `tests/` tests per subpackage, with shared COMTRADE files in `tests/data/`
- `notebooks/templates/` notebook templates for analysis work
- `notebooks/examples/` worked examples

## History

This repository merges the former repositories psp-core, psp-dsp, psp-comtrade,
psp-plotting and psp-relay, with their commit history. `from psp import ...`
(previously provided by psp-core) is now `from psp.core import ...`.

## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)
