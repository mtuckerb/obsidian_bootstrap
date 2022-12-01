# Obsidian Code Emitter

![GitHub release (latest by date including pre-releases)](https://img.shields.io/github/v/release/mokeyish/obsidian-code-emitter?display_name=tag&include_prereleases)
![GitHub all releases](https://img.shields.io/github/downloads/mokeyish/obsidian-code-emitter/total?style=flat-square)


This plugin allows code blocks executed interactively like jupyter notebooks. 

Currently, support languages:
- Rust
- Kotlin
- JavaScript
- TypeScript
- Python
- Java


**Note**: Only `Python`、`TypeScript`、`JavaScript` are run locally in sandbox(js / webassembly). Other's will send
code to third-party website to eval the results (eg: https://play.kotlinlang.org, https://play.rust-lang.org).
Please take care to avoid sending your potentially-sensitive source code.


**Ads**: You might like my other plugins 🤪
- [Obsidian Enhancing Export](https://github.com/mokeyish/obsidian-enhancing-export)

---

![.](./screenshots/code-emitter.gif)

## Installation

1. Create plugin folder `<your obsidian vault>/.obsidian\plugins\code-emitter`
2. Download files from [releases](https://github.com/mokeyish/obsidian-code-emitter/releases) into plugin folder.


## Examples

### Python
Install numpy through `micropip`. All available packages are list in [here](https://github.com/mokeyish/pyodide-dist/find/master) (search `whl`).

```python
import micropip
await micropip.install('numpy')  
import numpy as np
a = np.random.rand(3,2)
b = np.random.rand(2,5)

print(a@b)
```