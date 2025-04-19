成绩单模拟器
每次新增成绩页面的标准步骤
1. index.html 文件
在 <ul id="simulatorList"> 标签内新增一个 <li> 元素，包含模拟器的关键信息（类型、城市、年份）和对应的链接。
示例：
html
<li data-simulator="省考" data-city="山东" data-year="2025">
  <a href="simulators/shengkao-shandong/山东省2025年度公务员考试成绩查询.html">省考-山东-2025</a>
</li>
2. 新增成绩子页面的 HTML 文件
（1）在 <head> 标签内添加 JavaScript 代码
用于在页面加载完成后设置元素的可编辑属性（排除表单元素）。
代码示例：
html
<script>
  window.onload = function () {
    // 获取所有元素
    var allElements = document.getElementsByTagName('*');
    for (var i = 0; i < allElements.length; i++) {
      // 排除输入框、文本框、选择框等表单元素
      if (!['INPUT', 'TEXTAREA', 'SELECT'].includes(allElements[i].tagName)) {
        allElements[i].contentEditable = true;
      }
    }
  };
</script>
（2）删除页面中 “高速下载” 文本
说明：该文本是 Chrome 浏览器保存网页时自动添加的广告内容，需手动删除。
（3）移除跳转登录界面相关的 JS 文件
若页面出现跳转登录界面，需找到并删除 HTML 中所有引入 JS 文件的 <script> 标签。
说明：JS 文件负责动态功能（如动画、跳转等），删除后可避免非静态行为。
