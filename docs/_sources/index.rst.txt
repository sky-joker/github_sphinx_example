=============================================
はじめに
=============================================

.. raw:: html

    Sphinxで作ったドキュメントを <cite>github.io</cite> で公開するメモです。</br >
    Sphinxのドキュメント作成方法は書きません。既にドキュメントのrstが作られている前提です。<br />
    やっていることは <a href="https://help.github.com/articles/configuring-a-publishing-source-for-github-pages/" target="_blank">Configuring a publishing source for GitHub Pages</a> に書いてある事です。</br ></br >

=====================
概要
=====================

* githubにドキュメントをプッシュする
* githubの設定で `docs` を公開設定する

===================
ディレクトリ構成
===================

.. code-block:: bash

    github_sphinx_example/
    ├── docs
    └── docs_src

ディレクトリ説明
====================

.. csv-table::
    :header: ディレクトリ,説明

    docs,github.ioで公開するHTMLソースを保存するディレクトリ
    docs_src,Sphinxで作るドキュメントソースを保存するディレクトリ

===================
公開手順
===================

githubにプッシュ
==================

1. `docs_src` 内でビルドした `Sphinx HTMLドキュメント` を `docs` へコピーまたは移動します。

.. code-block:: bash

    $ cp -rp _build/html/* ../docs

2. `.nojekyll` を作成します。

.. code-block:: bash

    $ touch .nojekyll ../docs

.. warning::

    Githubでは標準で `Jekyll` を使います。Jekyllを使わないように `.nojekyll` を作成します。これを作成しないとgithub.ioでSphinxのスタイルシートなどをうまく読み込んでくれません。

3. ディレクトリツリー例は以下のようになります。

.. code-block:: bash

    github_sphinx_example
    ├── .gitignore
    ├── docs
    │   ├── .nojekyll
    │   (snip)
    └── docs_src

4. githubにプッシュします。

docs公開設定
==================

1. `Settings` をクリックします。

.. image:: img/2017-11-05\ 16.34.15.png

2. `Options` の `GitHub Pages` の `Source` を `master branch /docs folder` を設定して `Save` をクリックします。

.. image:: img/2017-11-05\ 16.37.44.png

3. 以下のURLにアクセスしてドキュメントを確認します。

.. csv-table::
    :header: URL

    https://githubアカウント名.github.io/リポジトリ名

.. note::

    ページが表示できるようになるまで少し待つ必要があります。
