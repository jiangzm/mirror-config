
[![NPM version](https://img.shields.io/npm/v/mirror-config.svg?style=flat-square)](https://www.npmjs.com/package/mirror-config)
[![Travis](https://img.shields.io/travis/jiangzm/mirror-config.svg?&label=Linux)](https://travis-ci.org/jiangzm/mirror-config)
[![AppVeyor](https://img.shields.io/appveyor/ci/jiangzm/mirror-config.svg?&label=Windows)](https://ci.appveyor.com/project/jiangzm/mirror-config)
[![codecov](https://img.shields.io/codecov/c/github/jiangzm/mirror-config.svg)](https://codecov.io/gh/jiangzm/mirror-config)

为中国内地的Node.js开发者准备的镜像配置，大大提高node模块安装速度。

## 特性

- 支持Windows和其他操作系统
- 自动配置各个node模块的安装源为淘宝镜像

## 安装

```bash
npm i -g mirror-config --registry=https://registry.npmmirror.com
# 查看npm配置
npm config list
# 查看环境变量
source ~/.bashrc && env
```

## 参数

### `--registry=https://registry.npmmirror.com`
registry.npmjs.com 镜像URL

### `--bin-mirrors-prefix=https://cdn.npmmirror.com/binaries`
cdn.npmmirror.com/binaries 镜像URL，会覆盖下文中的`{bin-mirrors}`

### `--nodejs-org-mirror={bin-mirrors}/node` (别名: `--disturl`)
nodejs.org/dist 镜像URL

### `--iojs-org-mirror={bin-mirrors}/iojs`
iojs.org/dist 镜像URL

### `--nvmw-npm-mirror={bin-mirrors}/npm`
github.com/npm/npm/releases 镜像URL

### 其他
其他参数将被写入`.npmrc`文件中

## 安装成功后，针对以下组件的镜像URL，将被写入npm用户配置文件(~/.npmrc)中

- [ChromeDriver](https://www.npmjs.com/package/chromedriver)
- [Electron](https://www.npmjs.com/package/electron)
- [git-win](https://www.npmjs.com/package/git-win)
- [node-gyp](https://www.npmjs.com/package/node-gyp)
- [node-inspector](https://www.npmjs.com/package/node-inspector)
- [node-sass](https://www.npmjs.com/package/node-sass)
- [sqlite3](https://www.npmjs.com/package/sqlite3)
- [nodegit](https://www.npmjs.com/package/nodegit)
- [nodist](https://github.com/marcelklehr/nodist)
- [nvm-windows](https://github.com/coreybutler/nvm-windows)
- [nvm](https://github.com/creationix/nvm)
- [OperaDriver](https://www.npmjs.com/package/operadriver)
- [phantomjs](https://www.npmjs.com/package/phantomjs)
- [Puppeteer](https://www.npmjs.com/package/puppeteer)
- [selenium-standalone](https://www.npmjs.com/package/selenium-standalone)
- [windows-build-tools](https://www.npmjs.com/package/windows-build-tools)
- [@swc/core](https://www.npmjs.com/package/@swc/core)

## 为项目生成镜像配置文件

```
cd ~/my-project
mirror-config --registry=https://registry.npmmirror.com

```

## Docker构建时使用

```dockerfile
RUN npm config set registry https://registry.npmmirror.com && npm install --unsafe-perm -g mirror-config
RUN npm ci
```
