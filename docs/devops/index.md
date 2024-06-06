# DevOps

work flow : code -> test -> deploy -> ops

## 产品迭代模式/项目管理

- 瀑布流式
- 敏捷开发

像gitlab/github这样的平台都是兼具代码管理、代码审核、任务管理、文档维护的功能，而早期这些能力都是分散的不在一个平台上，比如代码审核有gerrit、代码管理自建git server、任务管理redmine、Phabricator、jira，文档维护有cf。

团队规模分类

- 早期创业研发团队：2人android  2人ios  3个server   1个测试
- 中厂研发团队: 150多人android 大致也150人ios

## git 工作流程
1. git flow(版本发布)

存在两种长期分支

- master:面向用户，稳定版本
- develop:面向开发者，不稳定版本

存在三种临时分支

- feature分支在于开发功能的时候创建的，由develop分支衍生出来的，开发完成会被并入develop分支
- release分支用于发布版本之前创建的分支，由develop分支衍生出来的，如果测试有bug需要在此上面修复，然后会被并入master分支和develop分支；如果测试没有bug直接并入。
- hotfix分支，在上线之后出现bug，由master分支衍生出来。修复之后并入master分支和develop分支。

很多手机厂商都是使用git flow这种工作流程

2. github flow（持续发布）

github flow的开发模式相对来说就更好理解了，只有master这个长期分支, 通过提交pr让大家讨论pr从而促进团队交流。

3. gitlab flow(前两者的有点结合)

Chromium项目采用gitlab flow工作流程

## 参考文章

- [Git 工作流程](http://www.ruanyifeng.com/blog/2015/12/git-workflow.html)
