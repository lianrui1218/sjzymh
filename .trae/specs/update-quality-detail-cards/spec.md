# 数据质量详情页卡片布局 Spec

## Why
当前数据质量详情页使用表格展示部门排行榜，与首页的卡片布局不一致。需要将详情页改为卡片布局，显示全部部门，与首页风格保持一致。

## What Changes
- 将详情页的部门质量排行榜改为卡片布局
- 显示全部部门卡片（不只是Top4）
- 卡片样式与首页一致
- 保留概览区域和趋势图表

## Impact
- Affected code: data-quality.html 中的部门质量排行榜部分（约第1339-1427行）
- Affected CSS: 卡片样式复用首页样式

## ADDED Requirements

### Requirement: 详情页卡片布局
详情页部门质量 SHALL 使用卡片式布局显示全部部门。

#### Scenario: 卡片数量
- **WHEN** 用户访问数据质量详情页
- **THEN** 显示全部部门卡片（10个部门）

#### Scenario: 卡片样式
- **WHEN** 用户查看部门卡片
- **THEN** 卡片样式与首页一致

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

## REMOVED Requirements

### Requirement: 表格排行榜布局
**Reason**: 改为卡片式布局，与首页保持一致。
**Migration**: 移除现有的表格结构，替换为卡片布局。
