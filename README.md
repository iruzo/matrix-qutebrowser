# [Qutebrowser](https://qutebrowser.org) [Matrix](https://www.schemecolor.com/matrix-code-green.php) theme

<p align="center">
	<img src="https://raw.githubusercontent.com/iruzo/matrix-qutebrowser/main/assets/preview.png"/>
</p>

## Usage

- Manual config
  - Clone this repo or copy `matrix-qutebrowser.py` or `matrix-qutebrowser-no-tab-icons.py`.
  - Symlink (or just copy) the file `matrix-qutebrowser.py` to your `.qutebrowser` directory.
  - Add `config.source('qutebrowser-matrix.py')` at the _end_ of your `config.py` file.

- Let qutebrowser manage your themes.
  - Insert in your `config.py` the next code:
  ```python
  if not os.path.exists(config.configdir / "theme.py"):
      themes = [
              "https://raw.githubusercontent.com/iruzo/matrix-qutebrowser/main/matrix-qutebrowser.py",
              # "another theme...",
              ]
      if len(themes) > 0:
          for theme in themes:
              with urlopen(theme) as themehtml:
                  with open(config.configdir / "theme.py", "a") as file:
                      file.writelines(themehtml.read().decode("utf-8"))
  if os.path.exists(config.configdir / "theme.py"):
      config.source('theme.py')
  ```
  - Remove from your `.qutebrowser` directory your current theme and reload `config.py`
