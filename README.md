# ISTIO 文档汉化工作

> istio 文档中文翻译工作组，仅用来处理相关任务分派和跟踪。

一点注意事项：

1. 目前项目的 [Issue](https://github.com/servicemesher/istio-official-translation/issues) 中包含了尚待翻译的绝大多数文档，要参与的同学可以自行去 Issue 中回复认领，以避免重复工作。
2. 在项目根目录中运行 `hugo server`，能够启动一个本地 Web 服务器，在其中可以进行预览。
3. 目前大家统一意见，对于翻译文稿中涉及到的静态文件，直接沿用英文版的文件（，例如 `![english image](/docs/conecept.....)`），不再需要自行拷贝
4. 提交 PR 之前，可以在项目根目录运行 `make lint`，初步做一下 CI 的检查，成功后再提交。

> `make lint` 所需镜像 `gcr.io/istio-testing/website-builder:2018-06-15`，可能比较难下载
> [百度盘](https://pan.baidu.com/s/1w2UE-YEUO-79pNwbE5UM4w) 密码: 3vxe