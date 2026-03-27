# CSV 数据文件说明 / CSV Data Files Description

## 文件列表 / File List

所有 CSV 文件均提供中英文对照版本 / All CSV files have bilingual versions.

| 文件名 / Filename | 行数 / Rows | 说明 / Description |
|------------------|------------|-------------------|
| occupations_summary_bilingual.csv | 1616 | 职业摘要（中英文对照）/ Occupation summary |
| atomic_tasks_bilingual.csv | 16128 | 原子任务（中英文对照）/ Atomic tasks |
| ksa_units_bilingual.csv | 14544 | KSA 单元（中英文对照）/ KSA units |
| cas_scores_bilingual.csv | 1616 | CAS 评分（中英文对照）/ CAS scores |
| isco08_mapping_bilingual.csv | 1616 | ISCO-08 映射（中英文对照）/ ISCO-08 mapping |

## 变量说明 / Variable Description

详见 `codebook.json` 文件 / See `codebook.json` for variable details.

## 评分说明 / Score Explanation

### CAS 评分 / CAS Scores

| 评分 / Score | 0-1 分制 / 0-1 Scale | 1-5 分制 / 1-5 Scale |
|-------------|---------------------|---------------------|
| 低 / Low | 0.0-0.2 | 1-2 |
| 中低 / Medium-Low | 0.2-0.4 | 2-3 |
| 中等 / Medium | 0.4-0.6 | 3-4 |
| 中高 / Medium-High | 0.6-0.8 | 4-5 |
| 高 / High | 0.8-1.0 | 5 |

### 任务属性 / Task Attributes

| 变量 / Variable | 范围 / Range | 说明 / Description |
|----------------|-------------|-------------------|
| Cognitive Requirement / 认知门槛 | 1-100 | 1=简单重复，100=顶尖决策 / 1=simple, 100=expert |
| Physicality Intensity / 体力强度 | 1-100 | 1=纯脑力，100=重体力 / 1=office, 100=labor |
| Language Intensity / 语言强度 | 1-100 | 1=无语言，100=高依赖 / 1=none, 100=high |

## 权重类别 / Weight Categories

| 类别 / Category | 权重 / Weight | 说明 / Description |
|----------------|--------------|-------------------|
| Primary / 主要任务 | 60% | 核心工作任务 / Core work tasks |
| Secondary / 次要任务 | 30% | 支持性任务 / Supporting tasks |
| Ancillary / 辅助任务 | 10% | 辅助性任务 / Ancillary tasks |
