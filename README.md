# Biopharma Agent Skills

两套可移植的中文生物医药智能体技能，面向创新药疾病领域调研与管线资产战略评估。核心指令采用纯 Markdown 和标准 `SKILL.md` 目录结构，不绑定单一模型或供应商。

## Skills

| Skill | 用途 | 最少输入 |
|---|---|---|
| `disease-area-research` | 疾病负担、指南、标准疗法、全球/中国创新药管线、临床数据、近 24 个月 BD 交易与技术展望 | 疾病名称 |
| `drug-asset-strategy-review` | 从生物学、药物形式、临床监管、商业与知识产权四象限压力测试单个管线资产 | 项目/资产基本信息 |

## 一键获取

仓库地址：<https://github.com/lujiaqi1992-prog/biopharma-agent-skills>

- [下载标准 Agent Skills 安装包](./biopharma-agent-skills.zip)
- [直接读取疾病领域调研 skill](./disease-area-research.md)
- [直接读取管线资产战略评估 skill](./drug-asset-strategy-review.md)

```bash
git clone https://github.com/lujiaqi1992-prog/biopharma-agent-skills.git
```

## Codex

先下载并解压标准安装包，再将所需目录复制到个人 skills 目录：

```bash
curl -L -o biopharma-agent-skills.zip \
  https://github.com/lujiaqi1992-prog/biopharma-agent-skills/raw/refs/heads/main/biopharma-agent-skills.zip
unzip biopharma-agent-skills.zip
mkdir -p ~/.codex/skills
cp -R biopharma-agent-skills/skills/disease-area-research ~/.codex/skills/
cp -R biopharma-agent-skills/skills/drug-asset-strategy-review ~/.codex/skills/
```

重启或新建任务后，可直接说：

- “使用 disease-area-research 调研特发性肺纤维化。”
- “使用 drug-asset-strategy-review 评估这个 ADC 项目。”

## Claude Code 与支持 Agent Skills 的智能体

将完整 skill 目录复制到该产品文档指定的 skills 目录。例如，项目级使用时可以保留本仓库的 `skills/<skill-name>/SKILL.md` 结构，并在项目指令中要求智能体按需读取对应 skill。

如果产品支持 Agent Skills 目录发现，直接安装整个 skill 文件夹；不要只复制 `SKILL.md`，因为疾病调研 skill 还会按需读取 `references/`。

## Cursor、Windsurf、Gemini CLI 及其他智能体

这些产品的规则/技能发现方式可能不同，但都可以使用以下通用方式：

1. 把本仓库根目录的 `AGENTS.md` 加入项目上下文。
2. 直接提供 `disease-area-research.md` 或 `drug-asset-strategy-review.md` 的链接/文件。
3. 在任务中明确说“读取并遵循该技能文件”。

对于只接受单个系统提示或知识文件的智能体，使用仓库根目录的单文件版；疾病调研单文件已内嵌数据源协议、报告结构和质量检查。

## 数据连接器与降级运行

`disease-area-research` 不强制依赖任何商业数据库：

- 有 InnoSight、Citeline、Cortellis、Evaluate、Pharmaprojects、PatSnap 或内部数据连接器时，先发现其 schema，再查询并完整翻页。
- 没有结构化连接器时，使用监管机构、试验注册、指南机构、论文、公司公告等公开一手来源完成报告，并明确公开信息局限。
- 不得猜测工具名、字段、阶段、交易金额、专利状态或临床结果。

## 仓库结构

```text
.
├── AGENTS.md
├── README.md
├── LICENSE
├── disease-area-research.md
├── drug-asset-strategy-review.md
└── biopharma-agent-skills.zip
```

ZIP 内保留标准目录结构：`skills/<skill-name>/SKILL.md`、`agents/openai.yaml` 和按需加载的 `references/`。

## 重要边界

输出用于研发立项、竞争情报、BD 和组合决策支持，不构成医疗建议、监管意见、投资建议、法律意见或正式专利自由实施（FTO）结论。涉及临床、监管或知识产权决策时，应由相应专业人员复核。

## License

Creative Commons Attribution 4.0 International（CC BY 4.0）。允许复制、修改和商用，但须保留适当署名。
