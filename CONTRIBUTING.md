# 贡献指南 · Contributing to wswz

> 🐿️ 欢迎来到 **松鼠 AI 培训助手前端代码** 仓库
> 我们欢迎任何形式的贡献:Issue、PR、文档改进、Bug 反馈

---

## 📋 目录

- [行为准则](#行为准则)
- [我能贡献什么](#我能贡献什么)
- [如何开始](#如何开始)
- [提 Issue](#提-issue)
- [提 Pull Request](#提-pull-request)
- [代码规范](#代码规范)
- [文档规范](#文档规范)
- [提交信息规范](#提交信息规范)
- [Review 流程](#review-流程)

---

## 🤝 行为准则

本项目采用 [Contributor Covenant](https://www.contributor-covenant.org/zh-cn/version/2/1/code_of_conduct/) 行为准则。

**核心原则**:
- ✅ 友善、包容、尊重
- ✅ 欢迎新手提问
- ✅ 建设性反馈
- ❌ 不容忍任何形式的骚扰、歧视、人身攻击
- ❌ 不容忍恶意刷 Issue/PR

违反行为准则的评论、Issue、PR 会被直接关闭,严重者会被举报拉黑。

---

## 🎁 我能贡献什么

| 类型 | 适合谁 | 难度 |
|---|---|---|
| 🐛 **Bug 报告** | 所有人 | ⭐ |
| 💡 **功能建议** | 所有人 | ⭐ |
| 📝 **文档改进** | 所有人 | ⭐ |
| 🎨 **新增代码块** | 有前端经验 | ⭐⭐ |
| 🧩 **新模块开发** | 资深前端 | ⭐⭐⭐ |
| 🔧 **Bug 修复** | 有调试经验 | ⭐⭐ |

**首次贡献推荐路径**:文档改进 → Bug 报告 → 小代码块 → 新模块

---

## 🚀 如何开始

### 1. Fork 仓库

点仓库右上角 **Fork** 按钮 → 你账号下会出现 `your-name/wswz`

### 2. 克隆你的 fork

```bash
git clone https://github.com/your-name/wswz.git
cd wswz
```

### 3. 添加上游仓库

```bash
git remote add upstream https://github.com/newnewge/wswz.git
git fetch upstream
```

### 4. 创建特性分支

```bash
# 从 main 拉新分支(分支名要描述性强)
git checkout -b feat/add-scenario-card-component
# 或者
git checkout -b fix/homepage-mobile-layout
# 或者
git checkout -b docs/improve-installation-guide
```

### 5. 修改 + 提交

```bash
# 修改后
git add .
git commit -m "feat: 新增场景卡片组件"
git push origin feat/add-scenario-card-component
```

### 6. 在 GitHub 上开 PR

去你的 fork 页面 → **Compare & pull request** → 填写 PR 模板

---

## 🐛 提 Issue

### Bug 报告模板

```markdown
## Bug 描述
<一句话说清楚是什么 bug>

## 复现步骤
1. 打开 ...
2. 点击 ...
3. 看到 ...

## 期望行为
<应该发生什么>

## 实际行为
<实际发生了什么>

## 截图/录屏
<如果适用>

## 环境
- 模块: [色卡/首页/对练/...]
- 浏览器/平台: [Chrome 120 / 微信小程序 / ...]
- 设备: [iPhone 15 / MacBook Pro M2 / ...]

## 备注
<其他信息>
```

### 功能建议模板

```markdown
## 功能描述
<你想加什么>

## 使用场景
<什么时候会用到,谁会用>

## 建议实现方式
<如果有关于实现的建议,这里写>

## 替代方案
<考虑过其他方式吗>

## 备注
<其他信息>
```

---

## 🔀 提 Pull Request

### PR 标题格式

使用 [Conventional Commits](https://www.conventionalcommits.org/zh-hans/) 格式:

```
<type>(<scope>): <subject>
```

**示例**:
- `feat(homepage): 新增课程推荐位组件`
- `fix(practice): 修复对练界面按钮错位`
- `docs(readme): 补充安装步骤截图`
- `style(design): 调整主色卡饱和度`
- `refactor(scenario): 提取场景卡片公共组件`
- `test(homepage): 添加首页组件单元测试`

### PR 描述模板

PR 页面会自动加载模板,核心要写清楚:

```markdown
## 改动类型
- [ ] Bug 修复
- [ ] 新功能
- [ ] 文档改进
- [ ] 代码重构
- [ ] 样式调整

## 改动说明
<这个 PR 做了什么,为什么>

## 关联 Issue
Closes #<issue-number> / Fixes #<issue-number>

## 测试情况
- [ ] 在本地测试过
- [ ] 添加/更新了相关文档
- [ ] 截图/录屏(如果涉及 UI 改动)

## 截图对比(可选)
- 改动前:<截图>
- 改动后:<截图>

## 备注
<其他需要 reviewer 知道的事>
```

### 提 PR 前的检查清单

- [ ] 我在本地跑过,功能正常
- [ ] 我更新了相关文档
- [ ] 我没有引入新的 lint 错误
- [ ] commit 信息符合规范
- [ ] PR 描述完整

---

## 💻 代码规范

### 前端组件代码

- **命名**:帕斯卡命名法(`ScenarioCard.vue` / `HomePage.tsx`)
- **缩进**:2 空格
- **引号**:单引号优先
- **注释**:复杂逻辑必须有中文注释
- **代码块标注**:每个独立代码块前标注**模块名 + 语言类型**

```vue
<!-- 模块三:家长图鉴库 -->
<!-- 文件:ParentRoleCard.vue -->
<template>
  <view class="parent-role-card">
    <!-- 头像区 -->
    <image :src="avatar" class="avatar" />
    <!-- 信息区 -->
    <view class="info">
      <text class="name">{{ name }}</text>
      <text class="tag">{{ tag }}</text>
    </view>
  </view>
</template>
```

### 样式

- 使用项目统一的设计 token(色卡、字号、间距)
- 不要写 magic number,所有值尽量用变量
- 移动端优先(小程序场景)

### 注释风格

```javascript
// ✅ 好的注释:解释"为什么"
// 用 setTimeout 而不是 nextTick:避免小程序渲染卡顿
setTimeout(() => this.refresh(), 100)

// ❌ 不好的注释:描述"是什么"(代码自己会说话)
// 设置 timeout
setTimeout(() => this.refresh(), 100)
```

---

## 📚 文档规范

### Markdown 文件结构

每个 .md 模块文件应包含:

```markdown
# 模块名(中文 + 英文)

> 来源:飞书文档「...」
> 模块:N · N/9

---

## 📋 模块说明
<一段话介绍这个模块是干什么的>

## 🎨 设计要点
<关键设计决策>

## 💻 代码块
<独立可复制的代码块>

### 代码块 1:<名称>
```language
<code>
```

### 代码块 2:<名称>
```language
<code>
```

## ⚠️ 注意事项
<踩坑提醒>

## 🔗 关联模块
<与其他模块的关系>
```

### 代码块标注

每个代码块前**必须**标注:
- 模块名
- 用途
- 语言类型

```
代码块
模块:03-Parent-Role-Library
用途:家长角色卡片组件
语言:Vue 3

<view>...</view>
```

---

## 📝 提交信息规范

使用 [Conventional Commits](https://www.conventionalcommits.org/zh-hans/):

### Type 类型

| Type | 含义 | 示例 |
|---|---|---|
| `feat` | 新功能 | `feat: 新增场景对练记录功能` |
| `fix` | Bug 修复 | `fix: 修复首页白屏` |
| `docs` | 文档变更 | `docs: 更新 README 模块索引` |
| `style` | 代码格式 | `style: 统一缩进为 2 空格` |
| `refactor` | 重构 | `refactor: 提取公共组件` |
| `test` | 测试 | `test: 添加对练界面单测` |
| `chore` | 构建/工具 | `chore: 升级依赖` |
| `perf` | 性能优化 | `perf: 优化对练数据加载` |

### 完整示例

```bash
git commit -m "feat(practice): 新增 AI 对练复盘报告 PDF 导出

- 集成 PDF 渲染库
- 支持自定义页眉页脚
- 优化大报告生成性能

Closes #123"
```

---

## 🔍 Review 流程

### 作者

1. 提 PR 后,**保持响应**——24 小时内回复 reviewer 的问题
2. 收到 review 意见后,在本地修改并 force-push
3. 解决所有 conversation 后,@ reviewer 复审
4. 合并后**删除特性分支**

### Reviewer

1. **48 小时内**给首次反馈
2. 评论要**具体、建设性**——指出问题 + 提供建议
3. 区分**必改 (blocking)** 和**建议 (nit)**
4. 用 emoji 表达:
   - 💬 普通评论
   - ❓ 疑问
   - 🐛 必改 bug
   - 💅 建议(可改可不改)
   - ✅ LGTM (Looks good to me)

### 合并标准

PR 必须满足:
- [ ] 通过 CI 检查
- [ ] 至少 1 位 maintainer approve
- [ ] 所有 conversation resolved
- [ ] 与目标分支无冲突

---

## 🎉 首次贡献奖励

如果是你的**第一个 PR**,合并后可以:
- 在 README 贡献者列表里加名字
- 获得 **🐿️ First Squirrel** 徽章
- 我们会 @ 你致谢

---

## 📬 联系方式

- **GitHub Issue**:本仓库 Issue 区
- **邮件**:(待补充)
- **微信群**:(待补充)

---

## 🙏 致谢

感谢所有贡献者!你们的每一个 Issue、PR、文档改进,都让这个项目变得更好。

🐿️ **Happy Contributing!**
