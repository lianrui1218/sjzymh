# 统一模块标题样式 Spec

## Why
当前首页各模块标题样式不统一，有的标题在卡片外，有的在卡片内，视觉风格不一致。需要统一所有模块标题样式，参考"我的待办"模块的标题样式，使标题都在模块白底卡片内，提升视觉一致性。

## What Changes
- 统一核心数据概览模块标题样式
- 统一数据质量排行榜模块标题样式
- 统一资源推送模块标题样式
- 统一通知公告模块标题在白底卡片内显示。

## What Changes
- 统一核心数据概览、数据质量排行榜、资源推送、通知公告、数据管理标准规范模块的标题样式
- 所有模块标题都在白底卡片内显示
- 标题样式参考"我的待办"模块：左对齐加粗，右侧可选操作按钮

## Impact
- Affected code: index.html 中的各模块标题结构
- Affected CSS: 统一的模块标题样式类

## ADDED Requirements

### Requirement: 统一标题样式
所有模块 SHALL 使用统一的标题样式，标题在白底卡片内。

#### Scenario: 标题位置
- **WHEN** 用户访问首页
- **THEN** 所有模块标题都在白底卡片内显示

#### Scenario: 标题样式
- **WHEN** 用户查看模块标题
- **THEN** 标题左对齐、加粗、字体大小18px

#### Scenario: 右侧操作区
- **WHEN** 模块需要右侧操作按钮
- **THEN** 操作按钮右对齐显示

## MODIFIED Requirements

### Requirement: 模块标题结构
模块标题结构 SHALL 统一为：
- 外层容器使用 `.module-header` 类
- 标题使用 `.module-title` 类
- 右侧操作区使用 `.module-action` 类
