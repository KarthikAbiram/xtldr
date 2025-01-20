---
hide:
  - navigation
---

# Wasp

## Install
1. Set up [WSL for Windows](/wsl).
2. In WSL, install nvm for managing node installations.
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash
```
3. Install node via nvm (in WSL)
```
nvm install 20
```
4. Install wasp (in WSL).
```
curl -sSL https://get.wasp-lang.dev/installer.sh | sh
```
If you get a warning stating that '.local/bin' is not on your path, then do the following:
```
nano ~/.bashrc
```
Scroll to the end of the file and add the 'export PATH ...' string specified in the wasp installation warning. This would be something like below:
```
export PATH=$PATH:/home/{user}/.local/bin
```

Press Ctrl + O to save, then Ctrl + X to exit.

5. Check wasp installation and addition of path using
```
wasp version
```
6. Install [wasp VS code extension](https://marketplace.visualstudio.com/items?itemName=wasp-lang.wasp)

## Quick Start
Instantiate new project using wasp:
```
wasp new
```
Choose one of the available templates. Eg: SaaS.

## Open SaaS Template with Wasp
https://docs.opensaas.sh/start/getting-started/

## Useful Examples
- [Wasp x Supabase Combo Example](https://dev.to/wasp/wasp-x-supabase-smokin-hot-full-stack-combo-ioe)

## Deploy
https://wasp-lang.dev/docs/advanced/deployment/overview

## Resources
- 