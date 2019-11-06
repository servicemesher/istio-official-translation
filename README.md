# Istio官方文档翻译指导手册

## 概要

2018年我们社区组织翻译了Istio官网文档的1.2版本（已归档于：<https://archive.istio.io/v1.2/zh/>），随着Istio版本的快速迭代，老版本有许多需要更新的地方。为了让国内对Istio感兴趣的工程师可以学习到最新的官方文档，我们打算重启翻译工作，并基于官方的主线分支进行翻译，保证每次Istio在发布新版本时，同步的发布中文文档。

感谢您加入我们的翻译团队，并为Istio的中文化工作作出贡献。本篇文档是帮助您进行高效翻译的指导手册，建议您在正式翻译前认真阅读。

## 基本流程

整个翻译的基本流程包括下面几个步骤：

- 任务领取：在本仓库的Issue页面领取待翻译的任务；
- 翻译：根据任务提示进行翻译工作；
- 提交：翻译人员提交PR等待review；
- 校对：其他翻译人员对当前任务进行review；
- 终审：管理员团队对翻译内容进行最后确认；
- 预览：和源文档进行比对，查看显示效果；
- 合并：merge进入官方仓库，任务结束。

我们通过校对、终审两轮review保证翻译的质量；通过预览保证显示的准确性。翻译人员在整个流程中需要做的是领取任务，翻译，提交PR，预览自查这几步。

## 翻译指南

下面具体介绍一下如何进行翻译工作。

### 准备工作

- 账号：您需要先准备一个钉钉号和GitHub账号。钉钉用来协作和沟通，Github进行任务认领和翻译提交。

- 申请加入：请扫描下面的二维码加入钉钉协作群，通过审批后您需要登记一下基本信息（具体见群公告），之后管理员会将您添加到ServiceMesher的GitHub组织，即可正式参与翻译。

  ![dingding](https://tva1.sinaimg.cn/large/006y8mN6ly1g8ffa1lksfj306b08cgm4.jpg)

- 为保证翻译的统一性和准确性，请在翻译前仔细阅读[术语表](term.md)
  - 常用词汇：对常见的技术词汇给出统一的翻译；
  - 术语：文档中出现的专有技术名词，关键词，**保持原文不翻译；**

- 仓库和分支管理
  - fork[官网](https://github.com/istio/istio.io)的仓库，并作为自己仓库的上游： `git remote add upstream` ；
  - 在自己的仓库，也就是origin上进行翻译；
  - 一个任务新建一个branch；建议名称为：`zh-trans-<isssueID>`

### 翻译流程

#### Step1：任务浏览

访问[任务列表](https://github.com/servicemesher/istio-official-translation/issues)，会看到待领取任务（默认Open状态，label中带有`pending`字样）。通常情况下，您只需要关心状态和优先级两个label。

**状态label：**

- `pending`：待领取的任务；
- `translating`：已经有人领取，正在翻译的任务；
- `pushed`：已翻译并生成PR，正在进行review；
- `merged`：PR已合并，任务完成。

**优先级label：**

- 优先级从高到低分别为priority/P0 ~ priority/P3。优先选择优先级高的进行翻译。

除此以外，我们还设置了版本号、中文标示和类型等标签。

可以简单的通过点击标签来进行过滤，也可以参考 [github 查询语法](https://help.github.com/articles/searching-issues-and-pull-requests/)，来完成更复杂的查询。

#### Step2：任务领取

找到未经认领的任务（pending状态），在 issue 中回复 `/accept` 可以领取任务，Bot会将任务分配给你，并修改状态为translating。

> 注意：为保证质量，同一译者只能拥有三个 `translating` 状态的 Issue，超过数量无法继续认领。

#### Step3：翻译

- 请随时参考[翻译约定和术语表](term.md)，若对某些词汇的翻译模棱两可，可以直接回复该 Issue，或者在钉钉群请求帮助。

- 文档由若干 `md` 和 `html` 文档构成，将issue中给出的原始文件复制一份到对应中文目录下进行翻译。

- 译文中的英文与中文建议用空格分隔,可以使用这个[自动化中英文格式化 md 的软件](https://pypi.org/project/zhlint/)。
- 锚点：所有的标题都要补充英文锚点，如英文标题为`What is a service mesh?`，则中文翻译的标题应该为`什么是服务网格？{#what-is-a-service-mesh}`。其中锚点及所有英文单词小写，空格以连字符替代。如遇到复杂格式，可以在<https://istio.io>对应页面查看英文锚点。
- `md` 代码块与代码输出内容不要翻译。
- 对于翻译文稿中涉及到的静态文件，直接沿用英文版的文件（例如 `![english image](/docs/concept.....)`），不再需要自行拷贝。

#### Step4：本地构建和预览

翻译结束后可以先在本地构建网站进行预览。有两种方式可以将Istio的website运行起来：

**通过本地运行hugo启动**

hugo提供了一个本地的web服务器，可以启动网站。如果您本地没有安装hugo，可以去[这里](https://gohugo.io/getting-started/quick-start/)查看如何安装。

然后，在Istio.io仓库的[根目录](https://github.com/istio/istio.io)下，运行`hugo server`在本地启动web服务器，通过`http://localhost:1313/zh`进行中文网站的预览。如看到类似下面的输出，则表示web服务器已经启动成功：

```text
                   | EN  | ZH
+------------------+-----+-----+
  Pages            | 545 | 545
  Paginator pages  |   0 |   0
  Non-page files   | 164 | 164
  Static files     |  54 |  54
  Processed images |   0 |   0
  Aliases          |   1 |   0
  Sitemaps         |   2 |   1
  Cleaned          |   0 |   0

Total in 47355 ms
Watching for changes in /work/{archetypes,assets,content,data,generated,i18n,layouts,static}
Watching for config changes in /work/config.toml
Environment: "development"
Serving pages from memory
Web Server is available at http://localhost:1313/ (bind address 0.0.0.0)
Press Ctrl+C to stop
```

**通过Docker启动**

另外一种是直接使用docker镜像启动。

运行`docker pull gcr.io/istio-testing/build-tools:2019-10-24T14-05-17`下载镜像，然后在Istio[网站仓库的根目录](https://github.com/istio/istio.io)下，执行`make serve`启动web服务器。

如果您的网络环境无法访问此资源，可以执行下面的命令使用替代镜像启动web服务：
```
make serve IMG=jimmysong/istio-testing-build-tools:2019-10-24T14-05-17
```

启动成功后通过`http://localhost:1313/zh`进行网站的预览。

#### Step5：提交PR

执行`make lint`，初步做一下 CI 的检查，当看到有蓝色文字输出后没有报错就可以 `ctrl^c` 了，检查成功后再提交 PR。

> 可以使用 `make INTERNAL_ONLY=True lint` 命令，在不进行外部链接检查的情况下，完成 Lint 步骤

```
docker pull jimmysong/istio-testing-build-tools:2019-10-24T14-05-17
docker tag jimmysong/istio-testing-build-tools:2019-10-24T14-05-17 gcr.io/istio-testing/build-tools:2019-10-24T14-05-17
```

**提交PR**

如果检查通过，就可以向 [Istio 官方网站提交 PR](https://github.com/istio/istio.github.io/pulls)，PR 被合并后就可以通过 [Istio 网站预览页面](https://preliminary.istio.io/zh/)看到被合并后的页面。为方便管理和辨识，请遵守下面的模板定义您的PR：

```text
标题：
zh-translation:<file_full_path>
内容：
ref: https://github.com/servicemesher/istio-official-translation/issues/<issueID>
[ ] Configuration Infrastructure
[ ] Docs
[ ] Installation
[ ] Networking
[ ] Performance and Scalability
[ ] Policies and Telemetry
[ ] Security
[ ] Test and Release
[ ] User Experience
[ ] Developer Infrastructure
```

其中，标题中的<file_full_path>是翻译的源文件路径；内容中的ref是当前翻译任务的issue链接。

#### Step6：校对（review）

校对工作由没有翻译过当前文档的其他翻译人员执行，即翻译人员互为校对人员。为保证质量，我们设置了两轮Review：

所有翻译人员互为校对人员，分配一个翻译任务同时要确定校对任务；

- 初审：负责对翻译的内容和原文较为精细的进行对比，保证语句通顺，无明显翻译错误；
- 终审：负责对翻译的文档做概要性的检查，聚焦在行文的通顺性、一致性、符合中文语言习惯，词汇、术语准确。终审通过后由管理员approve当前PR，就可以进行合并了。

**参与Review**：所有 istio.io 的 PR都会通过 Github 机器人同步在钉钉群里，如果看到感兴趣的 PR 就在[本项目](https://github.com/servicemesher/istio-official-translation)中对应的 issue 回复一下，我们社区的 maintainer 会通过 `/assign`命令手动将Review工作指派给您。

**Review的基本流程**

- 认领Review：
  - 新提交的PR每天会在协作群发布，供大家认领；
  - 进入要认领的PR，回复/review，maintainer会将reviewer指派给您；
- Review重点：
  - 打开PR提交的中文翻译，并找到对应issue中指定的源文件，逐段进行走查；
  - 词汇检查：检查译文中出现的术语、常用词汇是否遵照了术语表的要求进行翻译；
  - 格式检查：对照原文，检查译文中的标题和层次是否对应；代码块是否指定了语言；标点符号是否正确且无英文标点；超链接、图片链接是否可达；是否有错别字；
  - 语句检查：分段落通读一遍，检查是否有不通顺、语病、或者不符合中文习惯的译文（啰嗦、重复、过多的助词等）
- 提交comment：
  - 根据发现的问题，在PR提交文件的对应行添加comment，格式为`原译文=>修改后译文`；不确定的地方可加建议或询问，或发到协作群求助。

#### Step7：任务完成

通过终审后的任务会被管理员approve，并合并到Istio的官方仓库中。需要您在对应的 Issue 中输入指令 `/merged`，Bot 会设置 Issue 的状态为 `finished`，并关闭 Issue。整个翻译任务就算正式完成了。您可以继续领取新的任务进行翻译，或参与校对工作。

## FAQ

术语、词汇翻译问题回复[这里](https://github.com/servicemesher/istio-official-translation/issues/77)。

CI报错等其他问题回复[这里](https://github.com/servicemesher/istio-official-translation/issues/1445)。

#### 有哪些修改Issue的自动化命令？

所有指令，都在 Issue 中以 Comment 的形式输入，仅对 Member 有效。如果出错或者不符合条件，不会有任何提示。

1. `/accept`: 适用于 `pending` 状态，且当前无人指派的 Issue，输入该指令，会将该 Issue 指派给当前用户。并变更状态为 `translating`
2. `/pushed`: 适用于 `translating` 状态的 Issue，输入该指令，会将该 Issue 指派给当前用户。并变更状态为 `pushed`
3. `/merged`: 适用于 `pushed` 状态的 Issue，输入该指令，会将该 Issue 指派给当前用户。并变更状态为 `finished`，然后关闭 Issue

#### 初次使用hugo启动找不到静态资源问题：

初次使用`hugo server`在本地启动web服务，web页面会出现如下问题，找不到静态资源。
```
Failed to load resource: the server responded with a status of 404 (Not Found)
Refused to apply style from 'http://localhost:1313/css/all.css' because its MIME type ('text/plain') is not a supported stylesheet MIME type, and strict MIME checking is enabled.
```

>解决方法：

1. 在项目根目录下执行`sh scripts/build_site.sh`命令，即可生成所需静态文件。但是这种方式需要安装比较多`node`的命令行工具，例如：`sass`、`tsc`、`babel`、`svgstore`，安装起来比较繁琐。
2. 这里建议首次可以采用`docker`方式启动，参考docker启动教程，在Istio[网站仓库的根目录](https://github.com/istio/istio.io)运行`make serve`启动，如果您的网络环境无法访问此资源，请使用`make serve IMG=jimmysong/istio-testing-build-tools:2019-10-24T14-05-17`命令，启动时docker镜像会在项目目录中生成`generated`、`tmp`和`resources`静态资源目录。
3. 在初次生成静态资源目录后，就可以正常使用`hugo server`来启动项目了。

#### 文档更新了怎么办？

如果发现文档更新，并且根据文档名称在 [Issue 库](https://github.com/servicemesher/istio-official-translation/issues)中找不到对应的 Issue，可以 [新建 Issue](https://github.com/servicemesher/istio-official-translation/issues/new)，Issue 标题写入变更的文件名，例如 `content/docs/reference/config/policy-and-telemetry/adapters/_index.md`，并在 Body 中加入 `@dustise, @rootsongjc`。这样就可以避免在你进行翻译的同时，Bot 重新将该文件放入任务队列。

#### 定义的锚点报拼写错误

给标题添加的锚点完全和官方英文的一致，报类似如下错误：

![anchor err](https://user-images.githubusercontent.com/36752240/68187530-e0750280-ffe1-11e9-8878-887f1d0c03ca.png)

主要的原因是在对于这些专有名词在`.spelling`文件中只定义了大写而没有定义小写导致。需要在`spelling`文件中添加对应的专有名词。

#### CI deploy/netlify 报错

本地make serve没问题，但官方的deploy/netlify报如下错误：

```bash
10:07:37 AM: added 35 packages from 9 contributors and audited 43 packages in 1.553s
10:07:37 AM: found 0 vulnerabilities
10:07:41 AM: TypeError: Cannot set property inList of [object Object] which has only a getter
10:07:41 AM:     at PluginPass.exit (/opt/build/repo/node_modules/babel-plugin-minify-simplify/lib/index.js:549:40)
10:07:41 AM:     at newFn (/opt/buildhome/.nvm/versions/node/v12.8.0/lib/node_modules/@babel/core/node_modules/@babel/traverse/lib/visitors.js:179:21)
10:07:41 AM:     at NodePath._call (/opt/buildhome/.nvm/versions/node/v12.8.0/lib/node_modules/@babel/core/node_modules/@babel/traverse/lib/path/context.js:55:20)
10:07:41 AM:     at NodePath.call (/opt/buildhome/.nvm/versions/node/v12.8.0/lib/node_modules/@babel/core/node_modules/@babel/traverse/lib/path/context.js:42:17)
10:07:41 AM:     at NodePath.visit (/opt/buildhome/.nvm/versions/node/v12.8.0/lib/node_modules/@babel/core/node_modules/@babel/traverse/lib/path/context.js:99:8)
10:07:41 AM:     at TraversalContext.visitQueue (/opt/buildhome/.nvm/versions/node/v12.8.0/lib/node_modules/@babel/core/node_modules/@babel/traverse/lib/context.js:112:16)
10:07:41 AM:     at TraversalContext.visitSingle (/opt/buildhome/.nvm/versions/node/v12.8.0/lib/node_modules/@babel/core/node_modules/@babel/traverse/lib/context.js:84:19)
10:07:41 AM:     at TraversalContext.visit (/opt/buildhome/.nvm/versions/node/v12.8.0/lib/node_modules/@babel/core/node_modules/@babel/traverse/lib/context.js:140:19)
10:07:41 AM:     at Function.traverse.node (/opt/buildhome/.nvm/versions/node/v12.8.0/lib/node_modules/@babel/core/node_modules/@babel/traverse/lib/index.js:84:17)
10:07:41 AM:     at NodePath.visit (/opt/buildhome/.nvm/versions/node/v12.8.0/lib/node_modules/@babel/core/node_modules/@babel/traverse/lib/path/context.js:97:18)
10:07:41 AM: Makefile.core.mk:49: recipe for target 'netlify' failed
10:07:41 AM: make: *** [netlify] Error 1
```

这是官方的一个[bug](https://github.com/istio/istio.io/pull/5379)，已经解决。

## 感谢

感谢您的辛勤付出！相信在大家共同的努力下Istio和Service Mesh技术会更加蓬勃的发展！

![ServiceMesher微信公众号二维码](https://tva1.sinaimg.cn/large/006y8mN6gy1g872im58vmj312m0begp8.jpg)