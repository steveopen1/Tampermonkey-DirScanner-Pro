# Tampermonkey-DirScanner-Pro
Tampermonkey DirScanner Pro是一款功能强大的目录扫描工具，基于油猴脚本开发，旨在为安全测试人员和开发者提供便捷的目录扫描功能。支持GET&amp;POST请求简单的发送poc，以及备忘录功能。

# 🎯 DirScan：强大的目录扫描工具
一款功能强大的目录扫描工具，基于油猴脚本开发，旨在为安全测试人员和开发者提供便捷的目录扫描功能。它参考了 dirsearch 工具进行优化，具备多项实用功能和良好的用户体验。🚀
## 🌟 功能特性
基础扫描功能
支持对指定 URL 进行目录扫描，可自定义字典路径，支持 GET 和 POST 请求方式。能自动填充当前页面 URL，方便快速开始扫描。🌐
- 自定义设置
  允许用户自定义请求头，以满足不同的测试需求。支持任意形式的 POST 数据包，为复杂场景下的扫描提供了灵活性。🔧
- 界面优化
  拥有美观的界面设计，设置字体为黑绿色，整体风格舒适。界面元素布局合理，不遮挡原页面内容。提供开关、展开 / 缩小、拖动等交互功能，操作便捷。扫描结果展示 UI 经过优化，支持双模式展示布局（表格视图和卡片视图），且结果宽度可拖动调整。🎨
- 功能拓展
  具备字典路径管理功能，限制字典文件为 txt 格式，方便用户管理和使用字典。新增备忘录功能，可用于记录重要信息，支持编辑、保存和删除操作。📝
-性能优化
  优化了请求处理逻辑，添加请求缓存机制，提升扫描速率。采用 Web Worker 进行后台扫描，避免阻塞页面，实现实时显示扫描结果。解决了多次扫描后显示异常和无法大量扫描的问题，增强了工具的稳定性和可靠性。📈

## 📚 使用方法
1. 安装油猴插件
在浏览器中安装 Tampermonkey（油猴）插件，支持 Chrome、Firefox 等主流浏览器。🔧
2. 安装脚本
将 DirScan 脚本安装到油猴插件中。可以通过直接复制脚本代码到油猴新建脚本页面，或者在油猴插件中搜索相关脚本进行安装。🔍
3. 配置扫描参数
打开需要扫描的页面，点击 “展开扫描工具” 按钮，打开扫描工具面板。在 URL 输入框中输入要扫描的基础 URL，默认为当前页面的 origin。在字典输入框中输入或粘贴扫描目录的路径，每行一个路径。选择请求类型（GET 或 POST），如果是 POST 请求，需在 POST 参数输入框中填写数据包内容。可在请求头输入框中自定义请求头信息，每行一个键值对。📝
4. 开始扫描
配置好参数后，点击 “执行” 按钮，即可开始扫描。扫描过程中会显示进度条和加载动画，扫描结果将实时显示在结果表格中。🏃
5. 查看和导出结果
扫描完成后，可在结果表格中查看详细的扫描结果，包括序号、URL、状态码、长度和标题等信息。点击 “全屏结果” 按钮可全屏查看结果，方便分析。如需导出结果，点击 “导出数据” 按钮，将生成 CSV 格式的文件供下载保存。📊
6. 使用备忘录
点击 “备忘录” 按钮，可打开备忘录面板。在编辑模式下，输入标题和内容后点击 “保存” 按钮进行保存。可对已保存的备忘录进行复制、编辑和删除操作。📝

## ⚠️ 注意事项
- 字典每个路径需要换行输入，建议使用小字典（千以内），以避免扫描过程中崩溃。📚
- 确保输入的 URL 格式正确，以 http:// 或 https:// 开头。🔗
- 由于目录扫描可能对目标服务器造成一定压力，请在合法合规且获得授权的情况下使用本工具。🛡️

# 未来计划
## 优化扫描性能
- 目标：进一步提升扫描效率，减少扫描时间。
- 具体措施：
  对并发控制逻辑进行优化，动态调整并发数量，根据使用率和网络状况自动调整并发量，避免过高并发导致的系统卡顿和网络拥塞。
  优化请求缓存机制，对已扫描的 URL 进行更智能的缓存，避免重复扫描
## 增强稳定性
- 目标：减少扫描过程中的错误和异常。
- 具体措施：
  增加对网络异常的自动重试机制，当检测到网络请求失败时，自动进行重试，最多重试 3 次。
  对可能出现的内存泄漏问题进行排查和修复，确保长时间扫描不会导致浏览器卡顿或崩溃。
  增加对扫描中断的支持，用户可以随时暂停或停止扫描，并在后续继续扫描。
## 改进用户界面
- 目标：提升用户交互体验，使界面更加友好。
- 具体措施：
  为扫描结果表格添加排序功能，用户可以按序号、状态码、长度等字段进行排序，方便快速定位目标。
  在扫描结果中增加响应时间的显示，帮助用户了解每个目录的响应速度。
  优化全屏结果面板的布局，使其在不同屏幕尺寸下都能保持良好的显示效果。
## 优化扫描结果分析
- 目标：帮助用户更好地分析扫描结果。
- 具体措施：
  增加扫描结果的统计功能，如统计不同状态码的数量、扫描到的目录总数等，并以图表形式展示。
  提供扫描结果的筛选功能，用户可以根据状态码、URL 包含的关键字等条件筛选结果。
  增加对扫描结果的导出格式支持，除了现有的 CSV 格式外，新增 JSON、HTML 等格式，方便用户在不同场景下使用。
## 优化备忘录功能
- 目标：提升备忘录功能的实用性。
- 具体措施：
  增加备忘录的分类功能，用户可以为备忘录添加标签或分类，方便管理和查找。![示例图片](https://img.shields.io/badge/措施-分类功能-green?style=flat-square)
  提供备忘录的搜索功能，用户可以通过关键字快速搜索到相关的备忘录。
  增加备忘录的导出功能，用户可以将备忘录导出为文本文件或 Markdown 格式。
