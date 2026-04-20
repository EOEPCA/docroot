# docroot

Documentation for the EO Exploitation Platform Common Architecture, published with Read the Docs and Zensical.

## Local development

Preview the site locally with the self-contained Docker-based serve script:

```bash
./serve
```

If you want to build the site without Docker:

```bash
pip install -r requirements.txt
python -m zensical build
```

The site configuration now lives in `zensical.toml` and replaces the previous MkDocs-specific setup.
