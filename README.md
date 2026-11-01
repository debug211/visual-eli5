# visual-eli5

`visual-eli5` 是一个面向 AI 编程助手的可移植 Skill。它将 PDF、Word、Markdown、网页内容或仓库文档提炼成准确、通俗的中文讲解，并在具备可用图像生成工具时产出知识信息图。

它不是网页、HTML、SVG 或 PPT 生成器。若当前宿主没有可用的图像生成能力，Skill 会交付可复用的提纲和绘图提示词，而不会伪造图片已生成。

## 目录结构

```text
visual-eli5/
├── SKILL.md
├── assets/
│   └── style-reference.png
└── references/
    ├── layouts-and-styles.md
    ├── prompt-template.md
    └── qa-checklist.md
```

`SKILL.md` 会通过相对路径读取 `assets/` 与 `references/`。安装时必须保留完整目录结构，不能只复制根目录下的单个 Markdown 文件。

## 安装

将仓库克隆或复制到目标客户端配置的 Skill 根目录，并保留目录名 `visual-eli5`。

以 Codex 为例：

```bash
git clone https://github.com/debug211/visual-eli5.git ~/.codex/skills/visual-eli5
```

WorkBuddy Codex 或其他支持 `SKILL.md` 的客户端，应将整个目录导入各自的 Skill 根目录。它们的具体导入路径由该客户端配置决定；不要拆散 `references/` 和 `assets/`。

## 使用

明确提出“图解”“知识大图”“信息图”“绘图解释”，或直接引用 `visual-eli5` 时触发。仅要求总结资料时，Skill 默认只输出文字，不会主动生成图片。

生成前应核实源材料，将明确事实、合理推断和未知信息分开。发送给第三方图像服务前必须脱敏，不得传出 token、密钥、身份证号、手机号、内部地址或订阅链接。

## 可移植性

- 不依赖固定的本机绝对路径。
- 不硬编码特定的阅读或图像生成工具；运行时检查实际可用能力。
- `assets/style-reference.png` 是无文字、无品牌的原创视觉参考，只用于色彩和版式方向。
- 发布到 GitHub 时以此完整目录为准。Gist 只建议发布明确标注为 `lite` 的单文件精简版。

## License

本仓库采用 [MIT License](LICENSE)。
