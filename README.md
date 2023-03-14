# React 開発環境構築してみる

## 1.Vite でプロジェクトを作成

[vite](https://ja.vitejs.dev/)を使用して、React+Typescript プロジェクトを作成する。以下のコマンドを実行。

```sh
$ npm create vite {project-name} --template=react-ts
```

生成された各ファイルの役割は以下の通り。
|ディレクトリ名/ファイル名|内容|
|----|----|
|src/|ソースコードを置く。|
|node_modules/|npm パッケージが保存されている。|
|public/|公開用アセットファイルを置く。|
|package.json|パッケージの情報等が書かれた設定ファイル。|
|package-lock.json|パッケージの依存情報が保存されたファイル。|
|tsconfig.json|Typescript をコンパイルするための設定ファイル。|
|tsconfig.node.json|Vite の設定を Typescript で書くためのファイル。|
|vite.config.ts|Vite の設定ファイル。|
|gitignore|Git リポジトリに含めないものリスト。|

## 2.リンターとフォーマッターの導入
