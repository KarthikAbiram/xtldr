---
hide:
  - navigation
---
# MKDocs
[Material for MKDocs](https://github.com/squidfunk/mkdocs-material) is an open source project where you can write your documentation using markdown, host it in git and generate a static site for you, [like this site](https://xtldr.com/).

# Docker Dev Container
In your repository root directory, create a folder called ".devcontainer" and create a "devcontainer.json" with below file contents.  

```
{
	"name": "mkdocs",
	"image": "squidfunk/mkdocs-material",
	"customizations": {
		"vscode": {
			"extensions": [
				"ms-python.python",
				"mhutchie.git-graph",
				"yzhang.markdown-all-in-one",
				"zaaack.markdown-editor",
				"esbenp.prettier-vscode",
				"ms-python.vscode-pylance"
			]
		}
	},
		// Use 'postCreateCommand' to run commands after the container is created.
		"postCreateCommand": "pip install mkdocs-material[imaging] && pip install mkdocs-glightbox"
	}
```

In VSCode, click on the green `><` icon on the bottom left and choose 'Reopen in Container'.