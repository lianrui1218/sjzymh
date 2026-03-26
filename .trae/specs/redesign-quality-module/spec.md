# 数据质量模块重构 Spec

## Why
当前数据质量模块使用排行榜表格展示，用户希望改为卡片式布局展示Top4部门，更直观地展示各部门的质量指标，并支持点击查看详情。

## What Changes
- 首页数据质量模块改为卡片式布局，展示Top4部门
- 每张卡片包含：部门名称、数据资源数、完整性/准确性/及时性百分比、综合达标率进度条
- 颜色规则：≥95%绿色达标，90%-94%蓝色预警，<90%红色未达标
- 右侧添加"查看更多"按钮
- 详情页包含：顶部概览、部门质量排行榜、部门资产明细、单表详情

## Impact
- Affected code: index.html 数据质量模块（约第2645-2765行）
- Affected CSS: 数据质量模块样式
- New pages: data-quality.html 详情页需要更新

## ADDED Requirements

### Requirement: 首页卡片布局
数据质量模块 SHALL 使用卡片式布局展示Top4部门。

#### Scenario: 卡片数量
- **WHEN** 用户访问首页数据质量模块
- **THEN** 显示Top4部门卡片

#### Scenario: 卡片内容
- **WHEN** 用户查看部门卡片
- **THEN** 显示部门名称、数据资源数、完整性/准确性/及时性百分比、综合达标率

### Requirement: 颜色规则
质量指标 SHALL 根据数值显示不同颜色。

#### Scenario: 达标状态
- **WHEN** 指标 ≥95%
- **THEN** 显示绿色，标记为"达标"

#### Scenario: 预警状态
- **WHEN** 指标在 90%-94%
- **THEN** 显示蓝色，标记为"预警"

#### Scenario: 未达标状态
- **WHEN** 指标 <90%
- **THEN** 显示红色，标记为"未达标"

### Requirement: 查看更多按钮
模块右侧 SHALL 显示"查看更多"按钮。

#### Scenario: 点击查看更多
- **WHEN** 用户点击"查看更多"
- **THEN** 跳转至数据质量详情页

### Requirement: 详情页概览
详情页顶部 SHALL 显示概览信息。

#### Scenario: 概览内容
- **WHEN** 用户访问详情页
- **THEN** 显示全部门平均质量分、已校验资产总数、未达标部门数、质量问题总数

#### Scenario: 时间筛选
- **WHEN** 用户查看概览
- **THEN** 可选择时间范围进行筛选

### Requirement: 部门质量排行榜
详情页 SHALL 显示部门质量排行榜。

#### Scenario: 排行榜字段
- **WHEN** 用户查看排行榜
- **THEN** 显示排名、部门名称、质量分、资源数量、问题数

#### Scenario: 排序规则
- **WHEN** 用户查看排行榜
- **THEN** 按质量分降序排列

#### Scenario: 颜色标识
- **WHEN** 质量分 ≥90%
- **THEN** 显示绿色
- **WHEN** 质量分在 80%-89%
- **THEN** 显示黄色
- **WHEN** 质量分 <80%
- **THEN** 显示红色

#### Scenario: 下钻功能
- **WHEN** 用户点击部门名称
- **THEN** 跳转至部门资产明细页

## REMOVED Requirements

### Requirement: 双列表格布局
**Reason**: 改为卡片式布局，不再使用表格展示。
**Migration**: 移除现有的双列表格结构，替换为卡片布局。
