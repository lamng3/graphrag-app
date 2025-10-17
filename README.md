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

### Run the Indexer
Prereq: Follow [GraphRAG/Getting Started](https://microsoft.github.io/graphrag/get_started/) to set up data project.

Set up workspace variables
```uv run graphrag init --root ./christmas```

Run indexing pipeline
```uv run graphrag index --root ./christmas```

#### Takeaway
`gpt-4-turbo-preview` does not support structured outputs (json schema). Some alternative models to use are: `gpt-4o`, `gpt-4o-mini`, `gpt-4-turbo`

### Use the Query Engine
Let's ask some questions using the dataset

Global search to ask a high-level question:
```
uv run graphrag query \
--root ./christmas \
--method global \
--query "What are the top themes in this story?"
```

Local search to ask a more specific question about a particular character
```
uv run graphrag query \
--root ./christmas \
--method local \
--query "Who is Scrooge and what are his main relationships?"
```

#### Takeaway
[GraphRAG/Query Engine](https://microsoft.github.io/graphrag/query/overview/) contains interesting information about leveraging local and global search mechanisms