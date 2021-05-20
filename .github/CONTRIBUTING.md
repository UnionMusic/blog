## 提交 Issue

我们的 Issue 使用 [Jira](https://unionmusic.atlassian.net) 进行管理。

- 确定 Issue 类型
- 避免提交重复的 Issue，在提交之前搜索现有的 Issue
- 在标签或标题中体现明确意图

随后由项目负责人确认 Issue 意图，更新 Issue，关联 milestone 并指派组件负责人。

### Issue 类型

- `缺陷/Bug`: 一旦发现可能是 bug 的问题，请选择 Issue 类型为 `缺陷` ，然后等待确认，一旦确认是 bug，此 issue 会被打上 `Status/Confirmed` 的标签。
  - 此时 issue 会以 `P1` 优先级进行处理。
  - 如果此 bug 影响线上应用正常运行，则会变更为 `P0` 优先级，需要马上立刻处理。
  - bug 会在最低需要修复的版本进行修复，P0 优先级的 bug 需要在下一个 Release 中修复。
- `新增功能/Feature`: 还有待开发一项产品的新功能。
- `改进/Improvement`: 改进或增强现有功能或任务。
- `任务/Task`: A task that needs to be done.
- `故事/Story`:
- `长篇故事/Epic`:

## 提交代码

### 提交 Pull Request

```bash
# 先创建开发分支开发，分支名应该有含义，避免使用 update、tmp 之类的
$ git checkout -b branch-name

# 开发完成后跑下测试是否通过，必要时需要新增或修改测试用例
$ make test

# 测试通过后，提交代码，message

$ git add . # git add -u 删除文件
$ git commit -m "fix(role): role.use must xxx"
$ git push origin branch-name
```

### 代码风格

你的代码风格必须遵循 [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md) 编码标准和 [PSR-4](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-4-autoloader.md) 自动加载标准。

不过我们的 CI 支持自动修正，这使我们可以专注于贡献的内容而不是代码样式。

### Commit 提交规范

根据 [angular 规范](https://docs.lianhe.art/styleguide/git-guide.html#commit-message-%E7%9A%84%E6%A0%BC%E5%BC%8F) 提交 commit，
这样 history 看起来更加清晰，还可以自动生成 CHANGELOG。

## 发布管理

Aux 基于 [semver](https://semver.org/lang/zh-CN/) 语义化版本号进行发布。

所有的 Stable 版本均在 master 分支上发布

所有的 beta 与 alpha 等非 Stable 版本均在 release 分支上发布，在 Stable 发布之后会删除所有在
release 上发布的版本。
