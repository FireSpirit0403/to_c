# 提升用户体验的一些简易方法

## 功能内容速览

- 命令行启动影刀（点击运行启动，不用查找应用）
- 批量点击XPath（实现某个网页批量点击）
- 点击桌面批处理文件实现启动操作

## 详细内容

### 命令行启动影刀（桌面点击启动）

要在命令行中启动影刀，可以使用以下命令：
"D:\tools\yingdao\ShadowBot.exe" shadowbot:Run?robot-uuid=fa041321-c47d-47ef-98e4-f179dd3460a0

### 批量点击XPath（开发者模式运行批量点击）

为了在网页上批量点击符合特定XPath表达式的元素，可以使用以下代码：
const xpathExpression = '//div/span[text()="未监听"]'; // 注意这里使用了双引号
const nodes = document.evaluate(
xpathExpression,
document,
null,
XPathResult.ORDERED_NODE_SNAPSHOT_TYPE,
null
);

for (let i = 0; i < nodes.snapshotLength; i++) {
const node = nodes.snapshotItem(i);
node.click(); // 确保这里的元素是可以被点击的
}


### 进入某个文件夹，输入命令行（桌面点击启动）

要创建一个批处理文件来自动执行进入指定文件夹并执行命令的操作，可以使用以下脚本：
@echo off
pushd "C:\your\directory"
your-command-here
