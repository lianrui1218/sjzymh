# 移除质量详情页维度和问题清单模块 Spec

## Why
用户希望进一步简化数据质量详情页面，移除"六大质量维度得分"和"质量问题清单"两个模块，使页面更加简洁。

## What Changes
- 移除六大质量维度得分模块（quality-dimensions）
- 移除质量问题清单模块（quality-issues）
- 保留部门质量概览模块

## Impact
- Affected code: data-quality.html
- Affected CSS: 移除相关模块的样式定义

## REMOVED Requirements

### Requirement: 六大质量维度得分模块
**Reason**: 页面简化需求，移除该模块。
**Migration**: 移除 quality-dimensions 相关HTML结构和CSS样式。

### Requirement: 质量问题清单模块
**Reason**: 页面简化需求，移除该模块。
**Migration**: 移除 quality-issues 相关HTML结构和CSS样式。
