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
  import os
  from urllib.request import urlopen

  # load your autoconfig, use this, if the rest of your config is empty!
  config.load_autoconfig()

  if not os.path.exists(config.configdir / "theme.py"):
      theme = "https://raw.githubusercontent.com/iruzo/matrix-qutebrowser/main/matrix-qutebrowser.py"
      with urlopen(theme) as themehtml:
          with open(config.configdir / "theme.py", "a") as file:
              file.writelines(themehtml.read().decode("utf-8"))
  if os.path.exists(config.configdir / "theme.py"):
      config.source('theme.py')
  ```
  - Remove your current theme from your `.qutebrowser` directory & reload `config.py`
