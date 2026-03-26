# 数据质量详情页简化 Spec

## Why
数据质量详情页面内容过多，用户希望简化页面，只保留部门质量概览模块，移除其他不必要的模块。

## What Changes
- 移除概览卡片模块
- 移除质量趋势图表模块
- 移除质量维度模块
- 移除质量问题清单模块
- 保留部门质量概览模块

## Impact
- Affected code: data-quality.html（移除多个模块的HTML和CSS）
- Affected CSS: 移除相关模块的样式

## REMOVED Requirements

### Requirement: 概览卡片模块
**Reason**: 页面简化，只保留部门质量概览。
**Migration**: 移除概览卡片HTML和相关CSS。

### Requirement: 质量趋势图表模块
**Reason**: 页面简化，只保留部门质量概览。
**Migration**: 移除趋势图表HTML和相关CSS。

### Requirement: 质量维度模块
**Reason**: 页面简化，只保留部门质量概览。
**Migration**: 移除质量维度HTML和相关CSS。

### Requirement: 质量问题清单模块
**Reason**: 页面简化，只保留部门质量概览。
**Migration**: 移除质量问题清单HTML和相关CSS。
