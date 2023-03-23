# Sphinx安装说明
## 官方文档：[Welcome — Sphinx documentation (sphinx-doc.org)](https://www.sphinx-doc.org/en/master/index.html)
## 环境准备：
1. note.js
2. python:[Python Release Python 3.6.8 | Python.org](https://www.python.org/downloads/release/python-368/)  
   配置python环境变量
## 安装：
1. pip3 install -U sphinx
2. sphinx-build --version
3. sphinx-quickstart docs
4. sphinx-build -b html docs/source/ docs/build/html
5. 使用第三方主题：  
   1. pip install furo
   2. docs/source/conf.py
    ```
    # The theme to use for HTML and HTML Help    pages.  See the documentation for
    # a list of builtin themes.
    #
    html_theme = 'furo'
    ```
    3. 另一个主题：`pip install sphinxjp.themes.dotted  `
    4. `html_theme = "dotted"`
    5. `pip install sphinx-book-theme`  
6. 使用Markdown需要安装转换扩展MyST-Parser  
pip install --upgrade myst-parser  
conf.py:
    ```
    extensions = ['myst_parser']
    ```
    ```
    source_suffix = {
    '.rst': 'restructuredtext',
    '.md': 'markdown',
    }
    ```
1. 浏览build/html/index.html
2. 把准备好的md文件夹note拖到source文件夹下,所有的md文件必须结构层次分明
3. 修改index.res  
    ```
    .. toctree::
   :maxdepth: 2
   :caption: Contents:
   :glob:

   note/*/*
    ```
4.  build项目`.\make.bat html`
5.  自动build扩展：
    1.  pip3 install sphinx-autobuild
    2.  sphinx-autobuild source build
    3.  http://127.0.0.1:8000/index.html
    4. sphinx-autobuild 要求操作系统提供一个空闲端口号并将其用于其服务器。通过 --port=0 将启用此行为。




