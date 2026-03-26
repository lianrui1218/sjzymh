# 顶部标签栏优化 Spec

## Why
当前待办事项模块的标签栏样式较为传统，存在底部边框线和激活态下划线，视觉上不够简洁。需要优化为扁平化、无分割线的现代风格，并新增"查看全部"按钮以提升用户体验。

## What Changes
- 添加一级大标题"我的待办"
- 保留四个标签：我的待办、我的申请、我的收藏、已办结（顺序不变）
- 标签栏最右侧新增蓝色文字按钮"查看全部"
- 激活标签文字颜色改为 #1677ff，去掉底部蓝色下划线
- 未激活标签文字颜色改为 #666
- 去掉所有标签底部边框线/分割线
- 优化标签间距和内边距
- 添加 hover 效果

## Impact
- Affected code: index.html 中的待办事项模块标签栏部分（约第2426-2435行）
- Affected CSS: .todo-tabs-header、.todo-tab 相关样式（约第1085-1110行）

## ADDED Requirements

### Requirement: 标签栏大标题
系统 SHALL 在标签栏上方显示一级大标题"我的待办"。

#### Scenario: 显示大标题
- **WHEN** 用户访问首页待办事项模块
- **THEN** 标签栏上方显示"我的待办"大标题

### Requirement: 查看全部按钮
系统 SHALL 在标签栏最右侧显示蓝色"查看全部"文字按钮。

#### Scenario: 显示查看全部按钮
- **WHEN** 用户访问首页待办事项模块
- **THEN** 标签栏最右侧显示蓝色"查看全部"按钮

#### Scenario: 点击查看全部
- **WHEN** 用户点击"查看全部"按钮
- **THEN** 跳转到待办事项列表页面

### Requirement: 激活态样式
系统 SHALL 使用文字颜色区分激活/未激活标签，不使用下划线或边框。

#### Scenario: 激活标签样式
- **WHEN** 某个标签处于激活状态
- **THEN** 文字颜色为 #1677ff，无底部下划线

#### Scenario: 未激活标签样式
- **WHEN** 某个标签处于未激活状态
- **THEN** 文字颜色为 #666

### Requirement: Hover 效果
系统 SHALL 为标签和按钮提供合适的 hover 效果。

#### Scenario: 标签 hover
- **WHEN** 鼠标悬停在标签上
- **THEN** 文字颜色变为 #333，无背景色变化

#### Scenario: 查看全部 hover
- **WHEN** 鼠标悬停在"查看全部"按钮上
- **THEN** 保持蓝色不变

## MODIFIED Requirements

### Requirement: 标签栏布局
标签栏 SHALL 采用水平排列，左右内边距增大，标签间距均匀。

- 每个标签左右 padding: 0 16px
- 每个标签上下 padding: 12px 0
- 标签之间间距均匀
- 整体干净、扁平、无分割线、无边框
