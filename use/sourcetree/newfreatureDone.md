# 完成新功能

由于远程develop分支是受保护的分支，除了Maintainer，其他人不能推送自己本地的develop分支到远程develop上，所以，我们不能点击`仓库 --> git工作流 --> 完成新功能`，而是需要把feature分支推送到远程，申请合并请求，Maintainer审核代码后，合并回develop分支。参考[Gitlab 代码审核](./../gitlab/review.md)。
