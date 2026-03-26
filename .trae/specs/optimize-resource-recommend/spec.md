# 资源推荐模块优化 Spec

## Why
资源推送模块需要优化为资源推荐，增加上架时间字段，并支持排序功能，提升用户体验和数据展示效果。

## What Changes
- 模块标题由"资源推送"改为"资源推荐"
- 右侧"共计 128 项资源"改为"查看全部"，跳转至数据资源页面
- 表格增加"上架时间"字段
- 表头"热度"和"上架时间"支持排序功能
- 默认按热度降序排列

## Impact
- Affected code: index.html 中的资源推荐模块（约第2770-3000行）
- Affected CSS: 表格样式、排序图标样式

## ADDED Requirements

### Requirement: 模块标题修改
资源推荐模块 SHALL 使用新的标题和操作按钮。

#### Scenario: 标题修改
- **WHEN** 用户访问首页资源推荐模块
- **THEN** 模块标题显示为"资源推荐"

#### Scenario: 查看全部按钮
- **WHEN** 用户点击右侧"查看全部"按钮
- **THEN** 跳转至数据资源页面

### Requirement: 上架时间字段
资源推荐表格 SHALL 增加上架时间字段。

#### Scenario: 显示上架时间
- **WHEN** 用户查看资源推荐表格
- **THEN** 每行数据显示上架时间

#### Scenario: 上架时间格式
- **WHEN** 用户查看上架时间
- **THEN** 显示格式为 YYYY-MM-DD

### Requirement: 排序功能
资源推荐表格 SHALL 支持热度和上架时间排序。

#### Scenario: 默认排序
- **WHEN** 用户首次访问资源推荐模块
- **THEN** 默认按热度降序排列

#### Scenario: 热度排序
- **WHEN** 用户点击"热度"表头
- **THEN** 按热度升序/降序切换排列

#### Scenario: 上架时间排序
- **WHEN** 用户点击"上架时间"表头
- **THEN** 按上架时间升序/降序切换排列

#### Scenario: 排序指示器
- **WHEN** 表头支持排序
- **THEN** 显示排序箭头图标，当前排序状态高亮

## MODIFIED Requirements

### Requirement: 表格字段顺序
表格字段顺序 SHALL 调整为：资源名称、类型、所属分类、热度、上架时间、状态、操作。
