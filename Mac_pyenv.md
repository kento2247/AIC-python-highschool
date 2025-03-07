## Mac版

### パッケージマネージャ(Homebrew) インストール
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew update
brew upgrade
```

### 処理系(Python) の仮想環境設定
```sh
brew install pyenv
cat <<EOF >> ~/.zshrc

export PYENV_ROOT="\$HOME/.pyenv"
export PATH="\$PYENV_ROOT/bin:\$PATH"
eval "\$(pyenv init --path)"
eval "\$(pyenv init -)"
EOF
source ~/.zshrc
```

### Pythonインストール+設定
```sh
pyenv install 3.10.13
pyenv virtualenv 3.10.13 myenv
pyenv global myenv
```

### 今回使用するGUIライブラリ(tkinter) インストール
```sh
brew install tcl-tk
export PATH="/opt/homebrew/opt/tcl-tk/bin:$PATH"
export LDFLAGS="-L/opt/homebrew/opt/tcl-tk/lib"
export CPPFLAGS="-I/opt/homebrew/opt/tcl-tk/include"
export PKG_CONFIG_PATH="/opt/homebrew/opt/tcl-tk/lib/pkgconfig"
pip install pytk
````