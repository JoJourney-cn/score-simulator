# 成绩单模拟器
每次新增成绩页面的标准步骤
1.index.html文件：
    在 <ul id="simulatorList"> 标签内新增一个 <li> 元素，包含模拟器的关键信息（类型、城市、年份）和对应的链接即可
    示例：<li data-simulator="省考" data-city="山东" data-year="2025"><a href="simulators/shengkao-shandong/山东省2025年度公务员考试成绩查询.html">省考-山东-2025</a></li>
2.新增成绩子页面的html文件：
    （1）在 <head> 标签内添加了一段 JavaScript 代码，用于在页面加载完成后设置元素的可编辑属性。具体代码如下：
    
<script>
    window.onload = function () {
        // 获取所有元素
        var allElements = document.getElementsByTagName('*');
        for (var i = 0; i < allElements.length; i++) {
            // 排除输入框、文本框、选择框等表单元素，因为它们本身就可编辑
            if (!['INPUT', 'TEXTAREA', 'SELECT'].includes(allElements[i].tagName)) {
                allElements[i].contentEditable = true;
            }
        }
    };
</script>
   （2）如果页面中存在'高速下载'文本，则需删除
        注：因为这段文字是chrome浏览器保存网页时，在html自动添加的一段说明介绍，相当于给自己打广告了
   （3）如果成绩网页出现跳转登录界面的情况，找到html中所有引入 JS 文件的 <script> 标签并删除
        注：js文件会提供动态页面功能，即各种非静态的诸如动画、跳转等功能
    


    
