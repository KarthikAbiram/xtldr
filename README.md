# Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

# Setup

## Option 1: Docker Dev Container

In VSCode, click on the green `><` icon on the bottom left and choose 'Reopen in Container'. Inside the terminal of dev docker terminal, start the live-reloading docs server using `mkdocs serve.` 

Once launched, you would be able to access the local site at `http://127.0.0.1:8000/`

## Option 2: Local Setup

1. Download and install Python 3.10. 
2. `pip install pipenv` - Install pipenv for creating and managing python virtual environments.
3. `pipenv shell` - Create python virtual environment.
4. `pipenv install` - Install the dependencies inside the virtual environment.

To Run:

1. `pipenv shell` - Activate the python virtual environment
2. `mkdocs serve` - Start the live-reloading docs server.

To Build:

- `mkdocs build` - Build the documentation site.

# Mkdocs Useful Links
- [Page Description](https://squidfunk.github.io/mkdocs-material/reference/#setting-the-page-description)
- [Admonitions aka Collapsible Callouts](https://squidfunk.github.io/mkdocs-material/reference/admonitions/)
- [Code Highlighting](https://squidfunk.github.io/mkdocs-material/reference/code-blocks/#usage)
- [Setting up Social Cards](https://squidfunk.github.io/mkdocs-material/setup/setting-up-social-cards/)
- [Sequence Diagrams and Co](https://squidfunk.github.io/mkdocs-material/reference/diagrams/)
- [Content Tabs](https://squidfunk.github.io/mkdocs-material/reference/content-tabs/)
- [Buttons](https://squidfunk.github.io/mkdocs-material/reference/buttons/)
- [Grids](https://squidfunk.github.io/mkdocs-material/reference/grids/)
- [Footer Text link](https://github.com/squidfunk/mkdocs-material/issues/5134#issuecomment-1453316243)

  