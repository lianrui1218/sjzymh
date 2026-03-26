# 资源申请字段中文名显示 Spec

## Why
当前资源申请页面的列权限配置中，字段显示为英文名称（如 mine_code、production_date 等），用户难以理解字段含义。需要将字段显示为中文名称，提升用户体验。

## What Changes
- 列权限配置中的字段名称由英文改为中文显示
- 字段名称格式：中文名（英文原名可选）
- 已选字段列表中也显示中文名

## Impact
- Affected code: apply.html 中的列权限配置部分（约第996-1045行）
- Affected JS: updateSelectedColumns 函数

## ADDED Requirements

### Requirement: 字段中文名显示
列权限配置中的字段 SHALL 显示中文名称。

#### Scenario: 字段列表显示
- **WHEN** 用户查看列权限配置
- **THEN** 每个字段显示中文名称

#### Scenario: 已选字段显示
- **WHEN** 用户选择字段后
- **THEN** 已选字段列表显示中文名称

### Requirement: 字段名称映射
系统 SHALL 维护字段英文名到中文名的映射关系。

#### Scenario: 字段映射表
- **WHEN** 系统渲染字段列表
- **THEN** 根据映射表将英文名转换为中文名

## MODIFIED Requirements

### Requirement: 字段显示格式
字段显示格式 SHALL 为：中文名（可选显示英文原名）。

字段中文名映射表：
- mine_code → 矿山编码
- production_date → 生产日期
- output_volume → 产量
- employee_count → 员工人数
- safety_index → 安全指数
- equipment_usage → 设备使用率
- energy_consumption → 能耗
- cost_per_unit → 单位成本
- quality_rate → 合格率
