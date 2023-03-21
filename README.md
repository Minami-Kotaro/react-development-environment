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

<br>

vite のデフォルト環境では Typescript の<code>baseUrl</code>の設定が聞かないため、プラグインを追加する必要がある。

```sh
$ npm i -D vite-tsconfig-paths
```

vite.config.ts に読み込む設定を追加する。

## 2.リンターとフォーマッターの導入

### 2.1. ESLint の環境を作る

ESLint のエコシステムのパッケージは以下の三種類。

- パーサー
  - ソースコードを特定の言語仕様に沿って解析してくれるライブラリー。
- プラグイン
  - ESLint の組み込み以外に独自のルールを追加するもの。それらを適用した共有設定をパッケージングして提供される。
- 共有設定

  - 複数のルールの適用をまとめて設定するもの。

  eslint をインストールする。

  ```sh
  $ npm i -D eslint
  ```

  設定ファイルのひな型を作成する。

  ```sh
  $ npx eslint --init
  You can also run this command directly using 'npm init @eslint/config'.
  ? How would you like to use ESLint? ...
  To check syntax only
  √ How would you like to use ESLint? · style
  √ What type of modules does your project use? · esm
  √ Which framework does your project use? · react
  √ Does your project use TypeScript? · No / Yes
  √ Where does your code run? · browser
  √ How would you like to define a style for your project? · guide
  √ Which style guide do you want to follow? · standard-with-typescript
  √ What format do you want your config file to be in? · JSON
  Checking peerDependencies of eslint-config-standard-with-typescript@latest
  The config that you've selected requires the following dependencies:

  eslint-plugin-react@latest eslint-config-standard-with-typescript@latest @typescript-eslint/eslint-plugin@^5.43.0 eslint@^8.0.1 eslint-plugin-import@^2.25.2 eslint-plugin-n@^15.0.0 eslint-plugin-promise@^6.0.0 typescript@*
  √ Would you like to install them now? · No / Yes
  √ Which package manager do you want to use? · npm
  ```
