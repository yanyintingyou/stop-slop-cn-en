# Stop Slop CN-EN for Hermes Agent

简体中文 | [English](README.md)

这是一个面向 Hermes Agent 的中英双语去 AI 腔写作 skill。

本项目**不是从零原创**，而是基于 Hardik Pandya 的开源项目 [hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop) 修改、重组和适配而来。原项目主要用于移除英文 AI 写作痕迹；本版本在保留其核心思想的基础上，改造成 Hermes 可加载的 Agent Skill，并加入中文写作、中英混合文本、中文财经/研究文章、微信公众号风格和 Hermes 工具使用规则。

## 相比原项目做了什么改造

相较原版 `stop-slop`，本版本主要做了以下调整：

- 改为 Hermes / Agent Skills 可识别的标准 skill tap 结构：`skills/stop-slop-cn-en/SKILL.md`。
- 将原本偏英文的 AI 写作痕迹规则扩展为中文和中英混合文本可用的规则。
- 增加中文 AI 腔高频短语清单，例如“赋能”“助力”“生态”“闭环”“高质量发展”“未来可期”等。
- 增加中文结构问题识别，例如 PPT 式分层、机械三段式、伪深度句式、万能结尾和过度格式化。
- 加入 Hermes 工具使用说明：文件改写时优先 `read_file` + `patch`，大段重写才用 `write_file`。
- 加入金融、宏观、上市公司研究场景下的事实边界要求：不编造数据，不混淆披露事实和分析推断，缺数据时写“未披露”。
- 加入 Telegram、微信公众号、GitHub README/技术文档等不同输出场景的格式差异说明。

## 用途

用于改写中文、英文或中英混合文本，减少 AI 写作痕迹，让输出更自然、更像真人写作。

特别适合：

- 中文公众号文章
- 宏观金融短评
- 上市公司研究笔记
- 学术段落轻度去 AI 腔
- AI 工具评测
- GitHub README/技术文档
- Telegram 或社媒长回复
- 中英混合文本的自然化改写

## 仓库结构

```text
skills/stop-slop-cn-en/
├── SKILL.md
└── references/
    ├── phrases-cn.md
    ├── structures-cn.md
    ├── examples-cn.md
    └── checklist-cn.md
```

## 安装到 Hermes

### 方式一：本地复制

把 `skills/stop-slop-cn-en` 复制到：

```bash
~/.hermes/skills/stop-slop-cn-en
```

然后新开一个 Hermes 会话，或在对话中加载：

```text
/skill stop-slop-cn-en
```

### 方式二：作为 GitHub skill tap 安装

```bash
hermes skills tap add yanyintingyou/stop-slop-cn-en
hermes skills install yanyintingyou/stop-slop-cn-en/stop-slop-cn-en --force
```

## 使用示例

```text
/skill stop-slop-cn-en

把下面这段中文财经评论改得自然一点，少点 AI 腔。保留事实边界，不要编造数据，不要写万能总结。
```

## 来源说明

原始项目：[hardikpandya/stop-slop](https://github.com/hardikpandya/stop-slop)

原作者：Hardik Pandya

原始许可证：MIT

本版本保留 MIT 许可，并在原项目基础上增加 Hermes Agent 兼容、中英双语写作规则和中文研究/财经文本适配。

## 许可

MIT。原始项目为 MIT，本改造版同样使用 MIT。
