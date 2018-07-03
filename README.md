# ISTIO 文档汉化工作

Istio 官方文档中文翻译工作组，仅用来处理相关任务分派和跟踪。

当前已合并到 Istio 官方网站中的中文部分可以通过 https://preliminary.istio.io/zh/ 预览。

## 工作流程

1. 目前项目的 [Issue](https://github.com/servicemesher/istio-official-translation/issues) 中包含了尚待翻译的绝大多数文档，要参与的同学可以自行去 Issue 中回复认领，以避免重复工作。整个翻译进度通过 [project](https://github.com/servicemesher/istio-official-translation/projects/2) 追踪，[查看待领取的 Issue](https://github.com/servicemesher/istio-official-translation/issues?q=is%3Aissue+is%3Aopen+label%3Apending)。

2. 待任务被指派给你的后就可以开始翻译了，对于翻译文稿中涉及到的静态文件，直接沿用英文版的文件（例如 `![english image](/docs/conecept.....)`），不再需要自行拷贝。

3. 翻译之前可以请查阅[约定和术语表](https://github.com/servicemesher/istio-official-translation/issues/77)，若对某些词汇的翻译模棱两可，可以直接回复该 Issue。

4. 翻译过程中可以在项目根目录中运行 `hugo server`，能够启动一个本地 Web 服务器，访问 <http://localhost:1313> 在其中可以进行预览。

5. 提交 PR 之前，可以在项目根目录运行 `make lint`，初步做一下 CI 的检查，成功后再提交。

   因为该命令使用到了`gcr.io/istio-testing/website-builder:2018-06-15`镜像，为了便于中国用户使用，请执行下面的命令下载该镜像，然后再执行`make lint`检查：

   ```bash
   docker pull gcr.mirrors.ustc.edu.cn/istio-testing/website-builder:2018-06-15
   docker tag gcr.mirrors.ustc.edu.cn/istio-testing/website-builder:2018-06-15 gcr.io/istio-testing/website-builder:2018-06-15
   ```

6. 如果检查通过，就可以向 [Istio 官方网站提交 PR](https://github.com/istio/istio.github.io/pulls)，PR 被合并后就可以通过 [Istio 1.0 网站预览页面](https://preliminary.istio.io/zh/)看到被合并后的页面。

7. 若有发现[已经关闭的 Issue](https://github.com/servicemesher/istio-official-translation/issues?q=label%3Afinished+is%3Aclosed) 中的英文原文有更新，请直接在 Issue 中回复“有更新”。

8. 重复第一步开始的流程。

## 新增了一点自动化指令

所有指令，都在 Issue 中以 Comment 的形式输入，仅对 Member 有效。如果出错或者不符合条件，不会有任何提示。

1. `/accept`: 适用于 `pending` 状态的 Issue，输入该指令，会将该 Issue 指派给当前用户。并变更状态为 `translating`
1. `/pushed`: 适用于 `translating` 状态的 Issue，输入该指令，会将该 Issue 指派给当前用户。并变更状态为 `pushed`
1. `/merged`: 适用于 `pushed` 状态的 Issue，输入该指令，会将该 Issue 指派给当前用户。并变更状态为 `finished`，然后关闭 Issue