# Architecture

- [Architecture](#architecture)
  - [`.circleci`](#circleci)
  - [`.vscode`](#vscode)
  - [`docs`](#docs)
  - [`generators`](#generators)
  - [`public`](#public)
    - [`index.html`](#indexhtml)
  - [`src`](#src)
    - [`assets`](#assets)
    - [`components`](#components)
    - [`design`](#design)
    - [`router`](#router)
    - [`state`](#state)
    - [`utils`](#utils)
    - [`app.config.json`](#appconfigjson)
    - [`app.vue`](#appvue)
    - [`main.js`](#mainjs)
  - [`tests`](#tests)

## `.circleci`

用于与[Circle CI](https://circleci.com/)持续集成的配置. 有关更多信息请参见 [the production doc](production.md#from-circle-ci) （这个东西是跟git相关的，加强脚本）。

## `.vscode`

对于vscode进行特定的设置和扩展，详见[the editors doc](editors.md#visual-studio-code) 。

## `docs`

You found me! :wink:

## `generators`

生成器可以加快开发速度。详见 [the development doc](development.md#generators) 。

## `public`

您将保留所有静态资产的位置，无需添加到我们的构建系统即可将其添加到`dist`目录。

### `index.html`

这个文件实际上确实由我们的构建系统处理，允许我们使用[EJS](http://ejs.co/)从Webpack注入一些信息，例如标题，然后添加我们的JS和CSS。

## `src`

保存我们资源文件的位置

### `assets`

这是由Vue Cli提供的静态文件管理. [在此了解更多信息](https://cli.vuejs.org/guide/html-and-static-assets.html).

### `components`

项目中大多数组件所在文件夹，包括我们的[全局基础组件](development.md#base-components).

### `design`

存放我们 [设计变量和工具的地方](tech.md#design-variables-and-tooling).

### `router`

路由器，路由以及所有与路由相关的组件所在的位置。有关更多信息，请参见[路由文档](routing.md) 。

### `state`

管理全局变量的地方. 详细参见[the state management doc](state.md) 。

### `utils` 实用程序

这些是你可能想在你的应用中有许多文件之间共享的实用功能。 他们将永远是纯洁和永远不会有副作用，这意味着，如果你提供了一个功能相同的参数，它总是返回相同的结果。 这些也应该不会直接影响到DOM或接口与我们Vuex状态。

### `app.config.json`

包含应用程序特定的元数据。

### `app.vue`

根的Vue部件，简单地委托给路由器视图。 通常，这是包含全局CSS的唯一组件。

### `main.js`

程序入口文件,是我们创建Vue的实例，并将其安装到DOM。

## `tests`

我们所有的测试都在这里， 详见 [the tests doc](tests.md)。
