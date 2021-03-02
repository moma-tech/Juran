## 介绍

用于基于 JSON 数据格式，直接生成 JAVA POJO 类

## 使用

- 市场搜索 GsonFormatPlus
- 创建空 Class
- 代码编辑区域，右键 -> Generate -> GsonFormatPlus
- 复制粘贴 Json 字符串
- setting 配置 converter 等，主要是各种常用注解，也可以自行定义
- 点击 OK -> 按需修改字段名词，类型等
- 成功

## 备注

- 使用特定的 converter 注解，需要确保项目中包含相关包
- 注意 json 格式，要确定格式正确，如引号等，需要符合规范，可利用互联网工具提前进行格式化和校验
- 复杂结构，会包含多个内部类，如果需要独立访问，可拆解 JSON，分别生成
