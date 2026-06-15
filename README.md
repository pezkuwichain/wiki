# Pezkuwi Wiki

Source for the community knowledge base at **https://wiki.pezkuwichain.io**.

Built with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/).
Content lives in `docs/` as Markdown.

## Local preview

```bash
python3 -m venv .venv && . .venv/bin/activate
pip install -r requirements.txt
mkdocs serve        # http://127.0.0.1:8000
```

## Contributing

Edit any page via the ✏️ button on the site (opens a pull request), or edit the
Markdown in `docs/` and open a PR. `mkdocs build --strict` runs on every PR; merges
to `main` build and deploy automatically.
