# Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

# Setup

## Local Setup

1. Download and install Python 3.10. 
2. `pip install pipenv` - Install pipenv for creating and managing python virtual environments.
3. `pipenv shell` - Create python virtual environment.
4. `pipenv install` - Install the dependencies inside the virtual environment.

## Local Run

1. `pipenv shell` - Activate the python virtual environment
2. `mkdocs serve` - Start the live-reloading docs server.

## Other Commands
- `mkdocs build` - Build the documentation site.

# Mkdocs Useful Links
- [Admonitions aka Collapsible Callouts](https://squidfunk.github.io/mkdocs-material/reference/admonitions/)
- [Setting up Social Cards](https://squidfunk.github.io/mkdocs-material/setup/setting-up-social-cards/)
- [Sequence Diagrams and Co](https://squidfunk.github.io/mkdocs-material/reference/diagrams/)
- [Content Tabs](https://squidfunk.github.io/mkdocs-material/reference/content-tabs/)
- [Buttons](https://squidfunk.github.io/mkdocs-material/reference/buttons/)
- [Grids](https://squidfunk.github.io/mkdocs-material/reference/grids/)