# Setup and development

- [Setup and development](#setup-and-development)
  - [首次设置](#首次设置)
  - [安装](#安装)
  - [开发服务器](#开发服务器)
    - [使用生产API开发](#使用生产API开发)
  - [生成器](#生成器)
  - [别名](#别名)
  - [Globals](#globals)
    - [Base components](#base-components)
  - [Docker (optional)](#docker-optional)

## 首次设置

确定下面的你都安装了:

- [Node](https://nodejs.org/en/) (at least the latest LTS)
- [Yarn](https://yarnpkg.com/lang/en/docs/install/) (at least 1.0)

之后更新下面的文件来适合你的应用:

- `src/app.config.json` (提供你应用的元数据)
- `.circleci/config.yml` (假设你想要通过持续集成自动 [部署到生产环境](production.md))

## 安装

```bash
# 从 package.json 安装开发依赖
yarn install
```

## 开发服务器

> 注意: 如果你使用的是Lininux， 并且运行一下命令时看到ENOSPC错误， 你必须t [增加可用文件监视程序的数量](https://stackoverflow.com/questions/22475849/node-js-error-enospc#answer-32600959).

```bash
# Launch the dev server
yarn dev

# Launch the dev server and automatically open it in
# your default browser when ready
yarn dev --open

# 与Cypress客户端一起启动开发服务器，以友好的界面进行测试驱动的开发。
yarn dev:e2e
```

### 使用生产API开发

默认情况下, 开发人员和测试人员通过`tests/mock-api`中的 [模拟API](/docs/tests.md#the-mock-api) 过滤请求. 要改为直接针对本地/实时API进行测试，请运行具有 `API_BASE_URL` 环境变量集的dev和test命令。例如:

```bash
# 针对本地后端服务器进行开发
API_BASE_URL=http://localhost:3000 yarn dev

# 针对生产服务器进行测试和开发
API_BASE_URL=https://example.io yarn dev:e2e
```

## 生成器

该项目包括生成器，以加快常见的开发任务。命令包括：

```bash
# 生成带有相邻单元测试的新组件
yarn new component

# 生成具有相邻单元测试的新视图组件
yarn new view

# 生成带有相邻单元测试的新布局组件
yarn new layout

# 生成带有相邻单元测试的新Vuex模块
yarn new module

# 使用相邻的单元测试生成新的实用程序功能
yarn new util

# 生成新的端到端测试
yarn new e2e
```

在[Hygen 文档](http://www.hygen.io/)的帮助下，更新generators文件夹中现有的生成器或者创建新的生成器

## 别名

为了简化引用本地模块和重构的过程，您可以在`aliass.config.js`中设置要在开发测试和单元测试之间共享的别名。按照惯例，该项目使用@前缀表示别名。

## Globals

### 基本组件

应用特定于应用程序的样式和约定的[基本组件](https://vuejs.org/v2/style-guide/#Base-component-names-strongly-recommended)（也就是表示性组件，哑类组件或纯组件）都应以`_base-`前缀开头。 由于这些组件通常代替原始HTML元素使用（因此经常使用），因此为方便起见，它们会自动进行全局注册。 这意味着您无需导入和本地注册它们即可在模板中使用它们。

## Docker (optional)

If you'd prefer to use Docker for development, it's recommended to install and run [Docker Desktop](https://www.docker.com/products/docker-desktop). Once the app is started, you'll be able to run commands like:

```bash
# Build and run a containerized version of your app in the background
docker-compose up --detach
```

Once your container has started, you can run any script from `package.json` inside the container by prefixing the command with `yarn docker` instead of just `yarn`. For example:

```bash
# Install dependencies in the container
yarn docker install

# Run the dev environment in the container
yarn docker dev

# Run tests in the container
yarn docker test
```

To list your containers and their statuses, you can run:

```bash
docker-compose ps
```

To stop your running containers, run:

```bash
docker-compose stop
```

If ever update the following files:

- `.dockerignore`
- `docker-compose.yml`
- `docker-dev.dockerfile`

Then you'll want to stop and remove all containers, networks, volumes, and images created for your app with:

```bash
docker-compose down --volumes --rmi all --remove-orphans
```

This command can also be useful in case something goes wrong with a container and you'd like to start over. All containers, networks, volumes, and images defined in `docker-compose.yml` will be rebuilt the next time you run `docker-compose up`.

See the docs for [Docker](https://docs.docker.com/) and [Docker Compose](https://docs.docker.com/compose/) for more information on how to use and configure Docker tooling.
