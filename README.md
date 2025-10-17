## GraphRAG Application
### How to run
#### `uv` package manager
- Install `uv` package manager
```pip install uv```

- Install multiple Python versions
```uv python install 3.11 3.12```

- Run a file
```uv run python <filename.py>```

#### Virtual environment
`uv` automatically manages virtual environments. We do not need to get into venv like traditional pip or conda.

What `uv add graphrag` will do:
- Automatically creates a venv if one doesn't exist
- Install GraphRAG and its dependencies 

#### Setup GraphRAG workspace variables
Prereq: Follow [GraphRAG/Getting Started](https://microsoft.github.io/graphrag/get_started/) to set up data project.

`uv run graphrag init --root ./christmas`