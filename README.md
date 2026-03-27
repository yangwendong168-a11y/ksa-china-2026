# KSA 提取数据说明 / KSA Extraction Data Documentation

## 数据概览 / Data Overview

| 项目 / Item | 数量 / Count |
|------------|-------------|
| 总职业数 / Total Occupations | 1616 |
| 原子任务数 / Atomic Tasks | 16128 |
| KSA 单元数 / KSA Units | 14544 |
| ISCO-08 验证匹配 / ISCO-08 Verified | 1008 |
| ISCO-08 AI 建议 / ISCO-08 AI Suggested | 608 |

## 文件说明 / File Description

### 核心数据 / Core Data

| 文件名 / Filename | 说明 / Description | 大小 / Size |
|------------------|-------------------|------------|
| ksa_full_final.json | 完整 KSA 数据（后处理版）/ Complete KSA data (post-processed) | 16MB |
| ksa_full_results.json | 原始提取结果 / Raw extraction results | 13MB |
| isco08_mapping_bilingual.csv | ISCO-08 映射（中英文对照）/ ISCO-08 mapping (bilingual) | - |
| occupations_summary_bilingual.csv | 职业摘要（中英文对照）/ Occupation summary (bilingual) | - |

### CSV 数据 / CSV Data

| 文件名 / Filename | 行数 / Rows | 说明 / Description |
|------------------|------------|-------------------|
| csv/occupations_summary.csv | 1616 | 职业摘要 / Occupation summary |
| csv/atomic_tasks.csv | 16128 | 原子任务 / Atomic tasks |
| csv/ksa_units.csv | 14544 | KSA 单元 / KSA units |
| csv/cas_scores.csv | 1616 | CAS 评分 / CAS scores |

### 文档 / Documentation

| 文件名 / Filename | 说明 / Description |
|------------------|-------------------|
| codebook.json | 数据字典（中英文对照）/ Data codebook (bilingual) |
| analysis_report.txt | 数据分析报告 / Data analysis report |
| validation_report.json | 质量验证报告 / Quality validation report |

## 变量说明 / Variable Description

详见 `codebook.json` 文件 / See `codebook.json` for details.

## 数据来源 / Data Source

- **来源 / Source**: 《中国职业分类大典（2022）》/ Chinese Classification of Occupations (2022)
- **提取工具 / Tool**: OpenClaw KSA 提取系统 / OpenClaw KSA Extraction System
- **生成时间 / Generated**: 2026-03-27 17:32:11

## 质量说明 / Quality Notes

- **完成率 / Completion Rate**: 100% (1616/1616)
- **失败数 / Failures**: 0
- **权重偏差 / Weight Deviation**: 27 个职业权重总和≠1.00（偏差±0.12 以内）/ 27 occupations with weight sum≠1.00 (deviation within ±0.12)

## 使用许可 / License

本数据仅供研究使用 / This data is for research use only.
