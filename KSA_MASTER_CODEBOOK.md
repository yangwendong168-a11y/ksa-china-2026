# KSA 完整总表变量说明 / KSA Master Table Variable Description

**生成时间 / Generated**: 2026-03-27 18:11:35  
**数据来源 / Source**: 《中国职业分类大典（2022）》  
**总行数 / Total Rows**: 145152  
**总变量 / Total Variables**: 30

---

## 一、基础身份与对齐变量 (Identification & Mapping)

| # | 变量名 (EN/CN) | 类型 | 示例 | 说明 |
|---|---------------|------|------|------|
| 1 | Occupation Code / 职业代码 | String | 1-01-00-01 | 《中国职业分类大典（2022）》6 位标准代码 |
| 2 | Occupation Name / 职业名称 | String | 中国共产党机关负责人 | 官方中文名称 |
| 3 | ISCO-08 Code / ISCO-08 代码 | String (4 位) | 1349 | 国际标准职业分类代码 |
| 4 | ISCO-08 Title (EN) / ISCO-08 英文名称 | String | Business Services Administrators | ISCO-08 英文名称 |
| 5 | Major Category / 所属大类 | Integer (1-7) | 1 | 1-7 大类标识 |

---

## 二、任务原子化与权重变量 (Task Atomization & Weighting)

| # | 变量名 (EN/CN) | 类型 | 示例 | 说明 |
|---|---------------|------|------|------|
| 6 | Task ID / 任务编号 | String | T001 | 每个职业拆解出的独立任务唯一编号 |
| 7 | Task Description (CN) / 任务描述 (中文) | String | 编制财务报表 | 动宾结构的原子化任务文本 |
| 8 | Task Importance Weight / 任务重要性权重 | Float (0-1) | 0.12 | 标准化权重，所有任务之和=1.00 |
| 9 | Weight Category / 权重类别 | String | Primary | 主要 (60%)、次要 (30%)、辅助 (10%) |
| 10 | Weight Percentage / 权重百分比 | Float (0-1) | 0.12 | 该任务的具体权重值 |

---

## 三、KSA 核心实体变量 (The 3+3+3 Matrix)

| # | 变量名 (EN/CN) | 类型 | 示例 | 说明 |
|---|---------------|------|------|------|
| 11 | KSA ID / KSA 编号 | String | K001, S001, A001 | K=知识，S=技能，A=能力 |
| 12 | KSA Type / KSA 类型 | String | Knowledge / 知识 | 知识/技能/能力 |
| 13 | KSA Subcategory / KSA 子类别 | String | Declarative | K: 陈述性/程序性/战略性; S: 技术/人际/认知; A: 认知/身体/社会 |
| 14 | KSA Unit Name (CN) / KSA 单元名称 (中文) | String | 宏观经济知识 | KSA 单元名称 |
| 15 | KSA Definition (CN) / KSA 定义 (中文) | String | ... | 该职业语境下的定义 |
| 16 | Semantic Cluster ID / 语义聚类 ID | String | SC_0123 | 余弦相似度θ=0.88 下生成的统一标识 |
| 17 | Related Task IDs / 关联任务 ID | String | T001, T003 | 该 KSA 关联的任务 ID 列表 |

---

## 四、AI 冲击评价指标 (CAS & Exposure Indices)

| # | 变量名 (EN/CN) | 类型 | 范围 | 说明 |
|---|---------------|------|------|------|
| 18 | Substitutivity Score (1-5) / 替代性评分 (1-5 分制) | Float | 1-5 | AI 独立接管任务的可能性 |
| 19 | Augmentation Score (1-5) / 增强性评分 (1-5 分制) | Float | 1-5 | AI 改变工作模式并提升决策质量的程度 |
| 20 | Complementarity Score (1-5) / 互补性评分 (1-5 分制) | Float | 1-5 | AI 作为思维助手且不改变人类核心投入的程度 |
| 21 | Assessment Justification (CN) / 评分理由 (中文) | String | - | 模型给分后的 1-2 句逻辑推论 |
| 22 | Exposure Index (ρ) / 技术暴露指数 (ρ) | Float | 0-1 | 基于任务权重计算的综合得分 ρ=∑(Weight×S) |
| 23 | Agentic Potential (0/1) / 智能体化潜力 (0/1) | Integer | 0/1 | 该任务链是否能由 AI Agent 端到端自主完成 |

---

## 五、任务属性与异质性控制变量 (Heterogeneity Controls)

| # | 变量名 (EN/CN) | 类型 | 范围 | 说明 |
|---|---------------|------|------|------|
| 24 | Physicality Intensity (1-100) / 体力强度 (1-100) | Integer | 1-100 | 任务对肢体动作和环境互动的依赖程度 |
| 25 | Connecting Labor Flag (0/1) / 连接性劳动标识 (0/1) | Integer | 0/1 | 是否涉及人际间的情感互动与信任构建 |
| 26 | Connecting Labor Depth (1-5) / 连接性劳动深度 (1-5) | Integer | 1-5 | 情感互动深度（仅 Flag=1 时有效） |
| 27 | Language Intensity (1-100) / 语言强度 (1-100) | Integer | 1-100 | 任务对自然语言处理的依赖度 |
| 28 | Cognitive Requirement (1-100) / 认知门槛 (1-100) | Integer | 1-100 | 任务的复杂程度 |
| 29 | Vibe Coding Flag (0/1) / 氛围编码标识 (0/1) | Integer | 0/1 | 任务是否正在从"直接操作"转向"自然语言交互与审计" |
| 30 | Vibe Coding Depth (1-5) / 氛围编码深度 (1-5) | Integer | 1-5 | 自然语言交互深度（仅 Flag=1 时有效） |

---

## 数据结构说明 / Data Structure

**三级关联 / Three-Level Association**:
```
职业代码 (Occupation Code)
  └─ 任务 ID (Task ID)
      └─ KSA ID (KSA ID)
```

**每行数据代表**: 一个职业的一个任务的一个 KSA 单元

**总行数**: 145152 行 = 1616 职业 × 平均 10 任务 × 平均 9 KSA

---

## 使用示例 / Usage Example

### 计算"高替代性技能的溢价贬值率"

```python
import pandas as pd

df = pd.read_csv('ksa_complete_master_bilingual.csv')

# 筛选高替代性技能 (替代性评分 >= 4)
high_sub_skills = df[df['Substitutivity Score (1-5) / 替代性评分 (1-5 分制)'] >= 4]

# 按职业分组计算高替代性技能占比
high_sub_ratio = high_sub_skills.groupby('Occupation Code / 职业代码').size() / df.groupby('Occupation Code / 职业代码').size()

# 后续可与薪资数据合并计算贬值率
```

---

## 文件位置 / File Location

**文件 / File**: `ksa_complete_master_bilingual.csv`  
**大小 / Size**: 约 50MB  
**编码 / Encoding**: UTF-8  
**分隔符 / Delimiter**: 逗号 (,)
