# 移除数据质量模块更多按钮 Spec

## Why
数据质量模块右边的"更多"按钮功能不明确，且排行榜已展示完整信息，无需跳转，需要移除以简化界面。

## What Changes
- 移除数据质量模块标题栏右侧的"更多 →"链接

## Impact
- Affected code: index.html

## ADDED Requirements

### Requirement: 移除更多按钮
系统应移除数据质量模块标题栏右侧的"更多"链接按钮。

#### Scenario: 更多按钮移除
- **WHEN** 用户访问首页数据质量模块
- **THEN** 标题栏右侧不显示"更多"按钮
