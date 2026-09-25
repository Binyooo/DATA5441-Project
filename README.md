# DATA5441 Project
Author: Michael Chang

This repository contains the code for DATA5441 Project.

## Environment

This project uses `graph-tool`, which should be installed from `conda-forge`
rather than `pip`.

Create the analysis environment:

```sh
conda env create -f environment.yml
conda activate data5441-graph-tool
```

If matplotlib or fontconfig writes cache warnings to stderr, keep their caches
inside the project:

```sh
mkdir -p .cache/matplotlib .cache/fontconfig
export MPLCONFIGDIR="$PWD/.cache/matplotlib"
export XDG_CACHE_HOME="$PWD/.cache"
```

For non-drawing analysis, prefer importing the core graph-tool API:

```python
import graph_tool as gt
# or
from graph_tool import Graph
```

`import graph_tool.all` also imports drawing/UI backends, which can emit macOS
display warnings on stderr even when graph-tool itself is working.

The exact local environment is also captured in:

- `environment.full.yml`: full conda package export without build strings.
- `conda-explicit.txt`: exact macOS arm64 conda package URLs.
- `conda-requirements.txt`: full conda MatchSpec requirements.
- `requirements.txt`: full conda MatchSpec requirements.
