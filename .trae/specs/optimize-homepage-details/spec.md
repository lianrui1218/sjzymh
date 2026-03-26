# 首页细节优化 Spec

## Why
首页存在一些细节问题需要优化：更多按钮文案不统一、数据质量排行榜布局太空、资源推送标签间距不合理。

## What Changes
- 所有"更多 →"按钮修改为"查看全部"，与我的待办模块一致
- 数据质量排行榜改为两列表格布局，共5行展示前10名数据
- 资源推送模块标签增加间距，不贴住边框

## Impact
- Affected code: index.html 中的模块标题、数据质量排行榜、资源推送标签
- Affected CSS: .assets-tabs 样式

## ADDED Requirements

### Requirement: 统一更多按钮文案
所有模块的更多按钮 SHALL 统一为"查看全部"。

#### Scenario: 核心数据概览模块
- **WHEN** 用户查看核心数据概览模块
- **THEN** 右侧按钮显示"查看全部"

#### Scenario: 通知公告模块
- **WHEN** 用户查看通知公告模块
- **THEN** 右侧按钮显示"查看全部"

#### Scenario: 数据管理标准规范模块
- **WHEN** 用户查看数据管理标准规范模块
- **THEN** 右侧按钮显示"查看全部"

### Requirement: 数据质量排行榜双列布局
数据质量排行榜 SHALL 使用双列表格布局，展示前10名数据。

#### Scenario: 双列布局
- **WHEN** 用户查看数据质量排行榜
- **THEN** 显示两列表格，每列5行，共展示前10名

#### Scenario: 表头字段
- **WHEN** 用户查看数据质量排行榜
- **THEN** 每列表格包含：排名、部门名称、质量分、资源数量、问题数

### Requirement: 资源推送标签间距
资源推送模块标签 SHALL 有合理的间距，不贴住边框。

#### Scenario: 标签间距
- **WHEN** 用户查看资源推送模块
- **THEN** 标签与边框有适当间距，不贴住线

## MODIFIED Requirements

### Requirement: 资源推送标签样式
标签容器 SHALL 有适当的内边距。

- 标签容器添加 padding
- 标签与边框保持合理间距
