# 多人游戏框架搭建

我通过 https://github.com/ourcade 里学习的多人游戏教程，在 client 方面，我使用了 Phaser 3.50，服务端使用了 Colyseus https://www.colyseus.io/ ，在这个 git 中，里面的代码已经成功让两个客户端通信了。

# Usage

## 1. start server
```bash
npm install
npm run start-server # 运行成功时，可以看到服务端的监控页：http://localhost:2567/colyseus
```
## 2. start client
```bash
npm install
npm run start
```

client 连接成功后，在 监控页 中可以看到新的 client

## 3. 通信测试

在这个 demo 中，我在 client 监听了 keydown 事件，并广播给其他客户端。从 console 中可以看到另一个客户端输入的 keydown 事件，这样证明通信已经成功了。

## 4. 后记

我并不熟悉 ts 或 node.js ，对其中的一些编程都仅仅是拿来即用。但 Phaser 和多人游戏是一个有意思的项目，希望可以更多地了解。游戏的具体同步方式是比较多样的，期待更深入的学习。

happy coding！



-- 分割线 ---------------------------------

![phaser3-parceljs-template](https://user-images.githubusercontent.com/2236153/71606463-37a0da80-2b2e-11ea-9b5f-5d26ccc84f91.png)

# Phaser 3 + TypeScript + Parcel Template
> For people who want to spend time making Phaser 3 games in TypeScript instead of configuring build tools.

![License](https://img.shields.io/badge/license-MIT-green)

This is a TypeScript specific fork of [phaser3-parcel-template](https://github.com/ourcade/phaser3-parcel-template).

## Prerequisites

You'll need [Node.js](https://nodejs.org/en/), [npm](https://www.npmjs.com/), and [Parcel](https://parceljs.org/) installed.

It is highly recommended to use [Node Version Manager](https://github.com/nvm-sh/nvm) (nvm) to install Node.js and npm.

For Windows users there is [Node Version Manager for Windows](https://github.com/coreybutler/nvm-windows).

Install Node.js and `npm` with `nvm`:

```bash
nvm install node

nvm use node
```

Replace 'node' with 'latest' for `nvm-windows`.

Then install Parcel:

```bash
npm install -g parcel-bundler
```

## Getting Started

Clone this repository to your local machine:

```bash
git clone https://github.com/ourcade/phaser3-typescript-parcel-template.git
```

This will create a folder named `phaser3-typescript-parcel-template`. You can specify a different folder name like this:

```bash
git clone https://github.com/ourcade/phaser3-typescript-parcel-template.git my-folder-name
```

Go into your new project folder and install dependencies:

```bash
cd phaser3-typescript-parcel-template # or 'my-folder-name'
npm install
```

Start development server:

```
npm run start
```

To create a production build:

```
npm run build
```

Production files will be placed in the `dist` folder. Then upload those files to a web server. 🎉

## Project Structure

```
    .
    ├── dist
    ├── node_modules
    ├── public
    ├── src
    │   ├── scenes
    │   │   ├── HelloWorldScene.ts
    │   ├── index.html
    │   ├── main.ts
    ├── package.json
```

The contents of this template is the basic [Phaser 3 getting started example](http://phaser.io/tutorials/getting-started-phaser3/part5).

This template assumes you will want to organize your code into multiple files and use TypeScript.

TypeScript files are intended for the `src` folder. `main.ts` is the entry point referenced by `index.html`.

Other than that there is no opinion on how you should structure your project. There is a `scenes` folder in `src` where the `HelloWorldScene.ts` lives but you can do whatever you want.

## Static Assets

Any static assets like images or audio files should be placed in the `public` folder. It'll then be served at http://localhost:8000/images/my-image.png

Example `public` structure:

```
    public
    ├── images
    │   ├── my-image.png
    ├── music
    │   ├── ...
    ├── sfx
    │   ├── ...
```

They can then be loaded by Phaser with `this.image.load('my-image', 'images/my-image.png')`.

## TypeScript ESLint

This template uses a basic `typescript-eslint` set up for code linting.

It does not aim to be opinionated.

## Dev Server Port

You can change the dev server's port number by modifying the `start` script in `package.json`. We use Parcel's `-p` option to specify the port number.

The script looks like this:

```
parcel src/index.html -p 8000
```

Change 8000 to whatever you want.

## Other Notes

[parcel-plugin-clean-easy](https://github.com/lifuzhao100/parcel-plugin-clean-easy) is used to ensure only the latest files are in the `dist` folder. You can modify this behavior by changing `parcelCleanPaths` in `package.json`.

[parcel-plugin-static-files](https://github.com/elwin013/parcel-plugin-static-files-copy#readme) is used to copy static files from `public` into the output directory and serve it. You can add additional paths by modifying `staticFiles` in `package.json`.

## License

[MIT License](https://github.com/ourcade/phaser3-typescript-parcel-template/blob/master/LICENSE)
