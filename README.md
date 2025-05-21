# UnityExcel2BytesCs

Unity项目中将Excel数据表转换为C#脚本和二进制文件的工具。

## 功能特性

- Excel数据表转换为C#类定义
- Excel数据转换为二进制文件
- 支持基础数据类型和数组类型
- 自动生成序列化/反序列化代码
- Unity编辑器集成

## 数据格式要求

Excel表格格式要求：
1. 第1行：字段名
2. 第2行：字段类型
3. 第3行：字段描述
4. 第4行及以后：具体数据

支持的数据类型：
- 基础类型：int、string、float等
- 数组类型：使用#分隔符，如：`1#2#3`表示`int[]`数组

## 使用方法

1. 将Excel文件(.xlsx)放入`ExcelData`目录

2. 在Unity编辑器中使用菜单：
   - `SDGSupporter/Excel/Excel2Cs`: 生成C#类文件
   - `SDGSupporter/Excel/Excel2Bytes`: 生成二进制数据文件

3. 在代码中读取数据：
```csharp
// 示例：读取武器数据
List<weapon> weapons = weapon.LoadBytes();
foreach(weapon w in weapons) {
    // 使用数据
    Debug.Log($"ID: {w.id}, Name: {w.name}");
}
```

## 文件结构

- `Assets/Editor/Excel2CsBytesTool.cs`: 核心转换工具
- `Assets/Scripts/DataTable/`: 生成的C#类文件目录
- `Assets/Resources/DataTable/`: 生成的二进制文件目录
- `ExcelData/`: Excel源文件目录

## 注意事项

1. Excel文件必须使用.xlsx格式
2. 确保Excel文件未被其他程序占用
3. 字段名不要使用C#关键字
4. 数组类型的值使用#符号分隔

## 开发环境

- Unity 2020.3或更高版本
- Excel格式：.xlsx
