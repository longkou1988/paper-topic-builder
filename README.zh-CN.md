# Paper Topic Builder

Paper Topic Builder 是一个 Codex Skill，用于基于 Zotero 文献库生成有证据支撑的实证论文选题。它尤其适合管理学、创业、组织行为、战略管理、信息系统、市场营销等领域的文献分析和论文选题开发。

它的核心目标不是“凭空想选题”，而是从 Zotero Collection 中读取真实文献，基于论文元数据、摘要、PDF 全文、笔记和批注，提取研究发现、研究局限、变量角色、机制线索和理论缺口，再生成可被审稿人视角检验的实证研究模型和选题卡片。

## 作者信息

- 作者：视频号「扣子说AI」
- 项目定位：帮助研究者把 Zotero 文献库转化为结构化、可追溯、有理论主线的实证论文选题。

## 适合谁使用

- 正在做管理学、创业、组织、战略、营销、信息系统等方向论文选题的研究者
- 已经在 Zotero 中整理了某个主题文献库，但不知道如何提炼理论缺口和研究模型的人
- 希望从已有文献中系统识别自变量、因变量、中介变量、调节变量的人
- 希望把定性研究中的机制、主题和边界条件转化为定量模型的人
- 需要从 SSCI 管理学期刊审稿人视角评估选题可行性的人

## 核心功能

1. 优先读取指定 Zotero Collection、子目录、标签或文献列表
2. 判断文献类型：定量、定性、混合方法、理论、综述、方法、元分析
3. 提取通用文献信息、研究发现、研究局限和未来研究方向
4. 对定量文献识别变量角色、假设路径、显著/不显著结果和测量来源
5. 对定性文献识别一阶概念、二阶主题、聚合维度、过程机制和边界条件
6. 归纳理论缺口、机制缺口、情境缺口、方法缺口和变量角色缺口
7. 构建变量网络，识别高频变量、过度使用变量和可重新定位的变量
8. 重组“前因-机制-结果-边界条件”研究模型
9. 生成不少于 10 个实证论文选题卡片
10. 选出排名前 3 的重点选题并生成完整研究故事链
11. 以 SSCI 管理学期刊审稿人标准评价选题风险和发表潜力

## 安装方法

把这个仓库克隆到 Codex 的 Skills 目录，并使用新的 Skill 文件夹名 `paper-topic-builder`：

```bash
git clone https://github.com/longkou1988/management-empirical-topic-builder.git ~/.codex/skills/paper-topic-builder
```

然后重启 Codex。重启后可以使用：

```text
$paper-topic-builder
```

如果你之前已经安装过旧文件夹名 `management-empirical-topic-builder`，建议把本地文件夹重命名为：

```text
~/.codex/skills/paper-topic-builder
```

## 使用方法

最简单的使用方式：

```text
使用 $paper-topic-builder 分析我的 Zotero Collection：创业相关/女性创业
```

也可以加入更具体的约束：

```text
使用 $paper-topic-builder 分析我的 Zotero Collection：创业相关/女性创业。请重点关注女性创业者融资、创业韧性、制度环境和数字平台情境下的理论缺口。
```

或者：

```text
使用 $paper-topic-builder 分析我的 Zotero 标签：digital entrepreneurship。请生成适合 SSCI 管理学期刊投稿的实证论文选题，并评估发表风险。
```

## Zotero 使用原则

这个 Skill 会优先调用 Codex 当前环境中的 Zotero 插件能力读取文献，不会默认要求用户手动导出 `.bib` 或 PDF。

只有在以下情况才使用 fallback：

- Zotero 插件不可用
- 无法访问指定 Collection、子目录或标签
- Zotero 元数据缺失严重
- PDF 附件缺失、无法读取、乱码或权限不足
- 用户明确提供 `.bib`、`.ris`、`.csv` 或本地 PDF 文件夹作为替代输入

## 输出文件

运行完成后，Skill 会生成以下文件：

1. `output/literature_matrix.xlsx`
2. `output/variable_role_matrix.xlsx`
3. `output/qualitative_mechanism_matrix.xlsx`
4. `output/theory_gap_matrix.xlsx`
5. `output/variable_network_summary.md`
6. `output/topic_cards.md`
7. `output/model_candidates.md`
8. `output/final_research_story.md`
9. `output/reviewer_evaluation.md`

## 质量控制

- 不编造文献内容、变量名称、理论基础、研究结论、DOI 或期刊信息
- 所有文献事实必须来自 Zotero 元数据、PDF、摘要、笔记、批注或 fallback 文件
- 所有变量角色必须有证据来源，例如模型图、假设部分、方法部分、变量测量部分、结果表或讨论部分
- 如果证据不足，必须标注“不足以判断”或“低置信度”
- 如果只能读取摘要，必须标注“仅基于摘要分析”
- 如果全文不可用，必须标注“全文不可用”并说明原因
- 生成选题时必须说明为什么变量组合不是简单拼凑
- 每个选题都必须包含理论主线、方法建议、数据来源建议、创新点、可行性和发表风险

## 示例输出方向

这个 Skill 不会直接生成泛泛的题目，而会尽量输出类似以下结构的选题：

- 中文标题和英文标题
- 核心研究问题
- 研究对象和研究情境
- 理论基础
- 自变量、因变量、中介变量、调节变量和控制变量
- 理论故事链
- 研究假设
- 方法建议和数据来源建议
- 创新点、可行性和发表风险
- 适合投稿方向

## 许可证

MIT
