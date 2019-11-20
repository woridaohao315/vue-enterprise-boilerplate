> 这是一个不断发展的，且对于VUE cli3非常有思想的vue开发体系，欢迎您提出问题，反馈，或者指正。如果您想增加我在这个项目上所花的时间，请考虑成为这个模板的赞助商

## 特点

- [**详尽的开发文档**](#documentation): 像VUE.js的核心文档一样精心编写，以便于快速培训新成员并且让他们巩固知识。
- [**保持一致性**](docs/linting.md): 独具一格的vue代码格式化, JavaScript/JSON, SCSS, 和 Markdown格式化, 已经集成到了vscode中并且将会在预提交时针对暂存文件运行。（ctrl+s保存文件也会执行）
- [**一流的测试**](docs/tests.md): 通过单元测试和端到端测试，实现测试驱动的开发。当开发时，Cypress提供可靠的端对端测试图形界面，有一流的测试模块，单元测试以及Jest live在你的源文件旁边
- [**快速发展**](docs/development.md): 通过 [可配置的生成器](docs/development.md#generators), [方便的命名](docs/development.md#aliases), and [全局基础组件](docs/development.md#base-components), 你的开发效率将大幅提高。

## 开始

```bush
# 1. 克隆仓库。
git clone https://github.com/chrisvfritz/vue-enterprise-boilerplate.git my-new-project

# 2. 进入你克隆的仓库。
cd my-new-project

# 3. 安装依赖，前提确保你已经安装了yarn
yarn

# 4. 替换一下这个文件的CI badge 通过一个标记关于你什么时候开始的并且创立一个链接以便于比较地址，由此你能够从你克隆之后一直获得一个加入到模板中的新特性的概览
node _start.js

# 5. 删除开始脚本，因为只能有一个开始
rm _start.js

# 6. 阅读下面的文档 "Setup and development".
```

## 文档
这一块是更详细的文档；

1.  [Setup and development](docs/development.md)
2.  [结构](docs/architecture.md)
3.  [语言和技术](docs/tech.md)
4.  [路由 布局以及视图](docs/routing.md)
5.  [状态管理(vuex)](docs/state.md)
6.  [测试和虚拟接口](docs/tests.md)
7.  [检测以及代码格式化](docs/linting.md)
8.  [编辑器集成](docs/editors.md)
9.  [生产的打包和部署](docs/production.md)
10.  [故障排除](docs/troubleshooting.md)

## 问答
**为什么我在创建新项目的时候要用这个样板而不是直接用 [Vue CLI](https://github.com/vuejs/vue-cli) ?**

Vue CLI的目标是灵活性，无论团队大小，无论是应用程序还是库，或者使用什么语言和技术，任何团队都可以尽可能轻松地建立一个新项目。

这个样板作了更多的假设。 假设您正在构建大型应用程序，可能是由大型团队开发的。 根据对大型企业项目而言最有效的选择，它还会为您提供许多默认选择。 同时，它旨在教授和授权用户配置这些默认值，以便于这个模板能适应他们自己的项目和团队。

**为什么我要用这个模板而不是 [Nuxt](https://nuxtjs.org/)?**

Nuxt就像一个非常聪明的私人助理，通过为您解决许多问题，立即使您的工作效率更高。 该样板更像是个人教练，旨在教授和授权用户从根本上配置他们的own_framework框架，非常适合其应用程序和团队。

如果你正在开发的项目，目标明确，并且需求和使用的技术不会发生重大变化，那么我可能建议使用Nuxt。对于常见应用程序的需求，这不仅仅是任务。 如果您是一家试图证明产品适合市场的初创企业，而您的主要目标是最初的开发速度，那也正是Nuxt所青睐的一点。

以下这几种情况，您可能更适合用我们的样板构建项目：

- 需求在将来很有可能改变，并且你想要保持项目的灵活性和可操控性。
- 你想集中精力开发可以在任何Vue项目中移植的技能。
- 您在一个大型团队中工作，因此需要使用工具来帮助每一个人避免常见的错，保持一致的风格，并且避免bikeshedding in PRs.

最后，这不是一个非此即彼的情况。 该样板演示了许多用于构建健壮应用程序的有用模式，这些模式也可以应用于Nuxt应用程序。 这意味着您可以使用Nuxt建立一个项目，同时仍然使用此样板作为学习指南。


**你能建立这个样板的Nuxt版本吗?**

我没打算写这个，但是你可以找到Nuxt叉子在 [debs-obrien/nuxt-boilerplate-project](https://github.com/debs-obrien/nuxt-boilerplate-project) 和 [wemake-services/wemake-vue-template](https://github.com/wemake-services/wemake-vue-template).

**这个模板不是我要找的，在哪里我能找到类似的模板和项目呢?**

开这[awesome-vue](https://github.com/vuejs/awesome-vue#scaffold) 在其他大型项目中找。
