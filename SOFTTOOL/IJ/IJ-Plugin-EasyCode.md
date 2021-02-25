### 介绍

基于数据库表结构的模板化代码生成插件

### 使用

- 下载插件
- 通过 IJ-Datasource 配置目标数据源
- 右键目标表，选择 EasyCode，配置结构映射，配置生成属性（Package，模板）
- 生成

### 模板配置

- 类似正常代码模板，通过 Group 概念进行不同场景的模板管理
- 表属性主要通过 tableInfo 等对象访问
- 使用 tool 进行格式操作
- 变量使用：
  >     - 通过$!进行变量或者函数调用
  >     - $!autoImport
  >     - import $!{tableInfo.savePackageName}.model.domain.$!{tableInfo.name};
  >     - 具体可参考示例模板

### 说明文档：

>     属性
>     $author 设置中的作者 java.lang.String
>     $modulePath 选中的module路径 java.lang.String
>     $projectPath 项目绝对路径 java.lang.String
>
>     对象
>     $tableInfo 表对象
>         obj 表原始对象 com.intellij.database.model.DasTable
>         name 表名（转换后的首字母大写）java.lang.String
>         comment 表注释 java.lang.String
>         fullColumn 所有列 java.util.List<ColumnInfo>
>         pkColumn 主键列 java.util.List<ColumnInfo>
>         otherColumn 其他列 java.util.List<ColumnInfo>,除主键以外的列
>         savePackageName 保存的包名 java.lang.String
>         savePath 保存路径 java.lang.String
>         saveModelName 保存的model名称 java.lang.String
>     columnInfo 列对象
>         obj 列原始对象 com.intellij.database.model.DasColumn
>         name 列名（首字母小写） java.lang.String
>         comment 列注释 java.lang.String
>         type 列类型（类型全名） java.lang.String
>         shortType 列类型（短类型） java.lang.String
>         custom 是否附加列 java.lang.Boolean
>         ext 附加字段（Map类型） java.lang.Map<java.lang.String, java.lang.Object>
>     $tableInfoList java.util.List<TableInfo>所有选中的表
>     $importList 所有需要导入的包集合 java.util.Set<java.lang.String>
>
>     回调
>     &callback 回调对象
>         setFileName(String) 设置文件储存名字
>         setSavePath(String) 设置文件储存路径，默认使用选中路径
>         setReformat(Boolean) 设置是否重新格式化生成后的代码，默认为true
>
>     工具
>     $tool
>         firstUpperCase(String name) 首字母大写方法
>         firstLowerCase(String name) 首字母小写方法
>         getClsNameByFullName(String fullName) 通过包全名获取类名
>         getJavaName(String name) 将下划线分割字符串转驼峰命名(属性名)
>         getClassName(String name) 将下划线分割字符串转驼峰命名(类名)
>         hump2Underline(String str) 将驼峰字符串转下划线字符串
>         append(Object... objs) 多个数据进行拼接
>         newHashSet(Object... objs) 创建一个HashSet对象
>         newArrayList(Object... objs) 创建一个ArrayList对象
>         newLinkedHashMap() 创建一个LinkedHashMap()对象
>         newHashMap() 创建一个HashMap()对象
>         getField(Object obj, String fieldName) 获取对象的属性值,可以访问任意修饰符修饰的属性.配合debug方法使用.
>         call(Object... objs) 空白执行方法,用于调用某些方法时消除返回值
>         debug(Object obj) 调式方法,用于查询对象结构.可查看对象所有属性与public方法
>         serial() 随机获取序列化的UID
>         service(String serviceName, Object... param)远程服务调用
>         parseJson(String) 将字符串转Map对象
>         toJson(Object, Boolean) 将对象转json对象，Boolean：是否格式化json，不填时为不格式化。
>         toUnicode(String, Boolean) 将String转换为unicode形式，Boolean：是否转换所有符号，不填时只转换中文及中文符号。
>     $time
>         currTime(String format) 获取当前时间，指定时间格式（默认：yyyy-MM-dd HH:mm:ss）
>     $generateService
>         run(String, Map<String,Object>) 代码生成服务，参数1：模板名称，参数2：附加参数。
>     $dasUtil Database提供的工具类，具体可方法请查看源码，适用于高端玩家
>     $dbUtil  Database提供的工具类，具体可方法请查看源码，适用于高端玩家
