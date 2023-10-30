# Python で GihHub からインストールできるアプリをつくる

- `poetry`を使ってみる
  - `python -m pip install poetry`
  - `poetry new py-app-sample`
  - `cd py-app-sample`
  - `poetry shell`

## `__main__.py` をつくる

- [`py_app_sample/__main__.py`](py_app_sample/__main__.py)
- [`pyproject.toml`](pyproject.toml) にエントリーポイント情報を追加する

```
[tool.poetry.scripts]
py-app-sample = "py_app_sample.__main__:main"
```

- `poetry install` を実行すると `py-app-sample` で実行できる状態になった
  - この状態で `__main__.py` を編集して `py-app-sample` を実行するとちゃんと変更が反映された
  - `poetry install` はデフォルトで編集可能モードでインストールされる
  - `pip install -e .` と同じような振る舞い
- `python -m py_app_sample` でも実行できる（ハイフンはアンダースコアに置換）

## GitHub からインストールする

- `pip install git+https://github.com/te9yie/py-app-sample.git` でインストールできるようになった
