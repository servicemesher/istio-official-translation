# ISTIO 中文文档追踪工作组

Istio 官方文档中文翻译和问题追踪工作组，仅用来处理相关任务分派和跟踪。

当前已合并到 Istio 官方网站中的中文部分可以通过 https://preliminary.istio.io/zh/ 预览。

交流微信群：[联系我](http://www.servicemesher.com/contact)

Slack 工作组：[**Service Mesher Slack Workplace**](https://join.slack.com/t/servicemesher/shared_invite/enQtNDE2OTkwMjkxNzEzLTQwOTcxNTAxMmMxMDU4OTliYTJmYjY5NjY2YzJlNWE3N2FkZjFjM2UzNDU0ZGVlZTliODBhZGUxNjI0ZmNjZmI)

## 工作流程

1. 目前项目的 [Issue](https://github.com/servicemesher/istio-official-translation/issues) 中包含了尚待翻译的绝大多数文档，要参与的同学可以自行去 Issue 中通过回复 issue 的方式认领，以避免重复工作。整个翻译进度通过 [project](https://github.com/servicemesher/istio-official-translation/projects/2) 追踪，[查看待领取的 Issue](https://github.com/servicemesher/istio-official-translation/issues?q=is%3Aissue+is%3Aopen+label%3Apending)。

2. Issue 中支持的自动化指令，这些自动化指令可以自动为 issue 打标签、分配任务和关闭 issue：

   - 在 issue 中回复 `/accept` 可以领取任务
   - 若已向官方提交 PR 再回复 `/pushed`
   - 若被合并再回复 `/merged`

3. 待任务被指派给你的后就可以开始翻译了，对于翻译文稿中涉及到的静态文件，直接沿用英文版的文件（例如 `![english image](/docs/conecept.....)`），不再需要自行拷贝。

4. 翻译之前可以请查阅[约定和术语表](https://github.com/servicemesher/istio-official-translation/issues/77)，若对某些词汇的翻译模棱两可，可以直接回复该 Issue。

5. 翻译过程中可以在项目根目录中运行 `hugo server`，能够启动一个本地 Web 服务器，访问 <http://localhost:1313> 在其中可以进行预览。

6. 提交 PR 之前，可以在项目根目录运行 `make gen` 用来在项目的 `public` 目录下生成 HTML 代码，然后执行`make lint`，初步做一下 CI 的检查，当看到有蓝色文字输出后没有报错就可以 `ctrl^c` 了，检查成功后再提交 PR。

> 可以使用 `make INTERNAL_ONLY=True lint` 命令，在不进行外部链接检查的情况下，完成 Lint 步骤

   因为该命令使用到了`gcr.io/istio-testing/website-builder:2018-10-08`镜像，为了便于中国用户使用，请执行下面的命令下载该镜像，然后再执行`make lint`检查：

   ```bash
   docker pull gcr.mirrors.ustc.edu.cn/istio-testing/website-builder:2018-10-08
   docker tag gcr.mirrors.ustc.edu.cn/istio-testing/website-builder:2018-10-08 gcr.io/istio-testing/website-builder:2018-10-08
   ```

7. 如果检查通过，就可以向 [Istio 官方网站提交 PR](https://github.com/istio/istio.github.io/pulls)，PR 被合并后就可以通过 [Istio 网站预览页面](https://preliminary.istio.io/zh/)看到被合并后的页面。

8. 重复第一步开始的流程。

## 新增了一点自动化指令

所有指令，都在 Issue 中以 Comment 的形式输入，仅对 Member 有效。如果出错或者不符合条件，不会有任何提示。

1. `/accept`: 适用于 `pending` 状态，且当前无人指派的 Issue，输入该指令，会将该 Issue 指派给当前用户。并变更状态为 `translating`
1. `/pushed`: 适用于 `translating` 状态的 Issue，输入该指令，会将该 Issue 指派给当前用户。并变更状态为 `pushed`
1. `/merged`: 适用于 `pushed` 状态的 Issue，输入该指令，会将该 Issue 指派给当前用户。并变更状态为 `finished`，然后关闭 Issue

> 注意：每个用户只能同时有三个处于 `translating` 状态的 Issue，超过上限之后，Bot 不会回应 `/accept` 指令。所以务必确认指派已经完成之后才开始翻译工作。

## 发现文档更新怎么办？
如果发现文档更新，并且根据文档名称在 [Issue 库](https://github.com/servicemesher/istio-official-translation/issues)中找不到对应的 Issue，可以
[新建 Issue](https://github.com/servicemesher/istio-official-translation/issues/new)，Issue 标题写入变更的文件名，例如 `content/docs/reference/config/policy-and-telemetry/adapters/_index.md`，并在 Body 中加入 `@dustise, @rootsongjc`。这样就可以避免在你进行翻译的同时，Bot 重新将该文件放入任务队列。

## 翻译注意事项

在翻译 Istio 官方文档前需要注意以下几点：

- 仔细阅读[术语和习惯用语](https://preliminary.istio.io/zh/about/contribute/terms/)。
- 文章标头中的 keyword 用作 SEO，不需要翻译，见 [该 PR](https://github.com/istio/istio.io/pull/3055)。

![ServiceMesher微信公众号二维码](https://ws1.sinaimg.cn/large/006tNc79ly1fz058o9546j31jt0beq9s.jpg)

[ServiceMesher Community](http://www.servicemesher.com) All Right Reserved