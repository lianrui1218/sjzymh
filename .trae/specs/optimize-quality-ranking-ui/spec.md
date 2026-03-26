# 数据质量排行榜 UI 优化 Spec

## Why
当前数据质量排行榜模块的视觉样式较为传统，需要优化为更现代、扁平、简洁的设计风格，提升用户体验和视觉效果。

## What Changes
- 标题改名为「数据质量排行榜」，移至左上角加粗
- 数据更新时间移至右上角，改为浅灰小字
- 表格添加白色圆角卡片样式
- 行高增大，去除多余边框，仅保留浅灰行分隔线
- 排名列保留圆形角标，前三名特殊样式
- 质量分去除彩色标签，改为纯数字显示
- 数字列右对齐，部门名称左对齐
- hover 行变浅灰背景
- 仅展示 5 条数据

## Impact
- Affected code: index.html 中的数据质量模块（约第2605-2700行）
- Affected CSS: .quality-section、.quality-ranking-container、.quality-ranking-table 相关样式（约第877-1013行）

## ADDED Requirements

### Requirement: 标题布局优化
系统 SHALL 将标题和时间按新布局显示。

#### Scenario: 标题位置
- **WHEN** 用户访问首页数据质量模块
- **THEN** 标题「数据质量排行榜」显示在左上角，加粗显示

#### Scenario: 时间位置
- **WHEN** 用户访问首页数据质量模块
- **THEN** 数据更新时间显示在右上角，浅灰小字

### Requirement: 表格样式优化
系统 SHALL 使用白色圆角卡片样式，简化边框。

#### Scenario: 卡片样式
- **WHEN** 用户访问首页数据质量模块
- **THEN** 表格显示为白色圆角卡片

#### Scenario: 行分隔线
- **WHEN** 用户访问首页数据质量模块
- **THEN** 仅显示浅灰行分隔线，无多余边框

#### Scenario: 行高
- **WHEN** 用户访问首页数据质量模块
- **THEN** 表格行高增大，更宽松透气

### Requirement: 数据展示优化
系统 SHALL 按新规则展示数据。

#### Scenario: 排名列
- **WHEN** 用户查看排名列
- **THEN** 显示圆形角标，前三名有特殊颜色

#### Scenario: 质量分列
- **WHEN** 用户查看质量分列
- **THEN** 显示纯数字，无彩色标签

#### Scenario: 对齐方式
- **WHEN** 用户查看表格数据
- **THEN** 数字列右对齐，部门名称左对齐

### Requirement: 数据条数限制
系统 SHALL 仅展示前 5 条数据。

#### Scenario: 数据条数
- **WHEN** 用户访问首页数据质量模块
- **THEN** 仅显示前 5 个部门的排行榜数据

## MODIFIED Requirements

### Requirement: Hover 效果
表格行 hover 时 SHALL 显示浅灰背景。

- hover 时行背景变为浅灰色
- 无其他视觉干扰
