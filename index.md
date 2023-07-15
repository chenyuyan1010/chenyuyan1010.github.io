---
layout: page
---

# About Me

<img src="https://chenkang455.oss-cn-shanghai.aliyuncs.com/image-20230714164119718.png" class="floatpic" width="960" height="720">

Here is **Kang Chen** (Click [***here***](https://chenkang455.github.io/others/CV-chenkang.pdf) to check my CV). I am a junior majoring in **Communication Engineering** at WuHan University currently. 

<br>

## Academic Background

- **Sep 2017 - July 2020:**  The No.1 Middle School Affiliated To Central China Normal University 
- **Sep 2020 - now:**  WuHan University 

<br>

---

## Research Interests

- Event-based Image Enhancement and Visual Perception
- Spiking neural network
- Electric vehicle public charging network

My current research focuses on the event-based motion deblurring tasks. In the near future, I will work in the Spiking Neural Network (SNN) research area.

---
## News and Updates
- **<font color='red'>[Highlight] </font> 07-2023：**Happy to be selected as the outstanding camper at the Peking University 2023 Summer Camp of Computer Science, advised by  [Prof. Tiejun Huang](https://cs.pku.edu.cn/info/1008/1103.htm) and [Prof. Zhaofei Yu](https://www.ai.pku.edu.cn/info/1139/1252.htm).
- **<font color='red'>[Highlight] </font> 06-2023：**One paper "Motion Deblur by Learning Residual from Events" submitted to IEEE TMM under the guidance of Prof. Lei Yu.
- **05-2023：**One paper "Planning method of electric vehicle public charging network with overloaded charging nodes" accepted by Electrical Measurement & Instrumentation.
- **04-2023：** Happy to be designated as Honorable Mention in MCM 2023.
- **11-2022：** Happy to win the first price of Hubei Province in China Undergraduate Mathematical Contest in Modeling 2022.
- **10-2022：** Happy to join the **[DVS-WHU-Group](https://dvs-whu.cn/)**, advised by [Prof. Lei Yu](http://eis.whu.edu.cn/ryDetail.shtml?rsh=00030713).
- **<font color='red'>[Highlight] </font>  9-2022：** Happy to be awarded the National Scholarship.
- **05-2022：** Happy to win the second price in Mathorcup 2022.
- **04-2022：** Happy to be designated as Honorable Mention in MCM 2022.
- **11-2021：** Happy to join the Network Communication Laboratory, advised by Prof. Xun Gao.
- **11-2021：** Happy to take part in the National Undergraduate Electronic Design Competition 2021.
- **10-2021：** Happy to be awarded the Huang Zhangren Scholarship and the first Class Scholarship of Wuhan University.
- **09-2020：** Happy to become a member of Wuhan University.
<br>

<script src="https://giscus.app/client.js"
        data-repo="chenkang455/comment_system"
        data-repo-id="R_kgDOJ7nAdg"
        data-category="Announcements"
        data-category-id="DIC_kwDOJ7nAds4CX5Eh"
        data-mapping="url"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="bottom"
        data-theme="preferred_color_scheme"
        data-lang="zh-CN"
        crossorigin="anonymous"
        async>
</script>

浏览量:&nbsp;<span id="" class="leancloud_visitors" data-flag-title=""> - </span>次.

<script src="//unpkg.com/leancloud-storage@4.12.2/dist/av-min.js"></script>
<script>
    // 第一个参数是appid，第二个参数是appkey，此处的只是示例
    AV.init({
      appId: "wQZ0cGbJkMGHNxrBER4b003l-gzGzoHsz",
      appKey: "bNnjy1X8ZWD3c5bC2OJTNmBW",
      serverURL: "https://leancloud.api.whuzfb.cn"
    });
    // 自己创建的Class的名字
    var name='Counter';
    function createRecord(Counter){
      // 设置 ACL
      var acl = new AV.ACL();
      acl.setPublicReadAccess(true);
      acl.setPublicWriteAccess(true);
      // 获得span的所有元素
      var elements=document.getElementsByClassName('leancloud_visitors');
      // 一次创建多条记录
      var allcounter=[];
      for (var i = 0; i < elements.length ; i++) {
        // 若某span的内容不包括 '-' ，则不必创建记录
        if(elements[i].textContent.indexOf('-') == -1){
          continue;
        }
        var title = elements[i].getAttribute('data-flag-title');
        var url = elements[i].id;
        var newcounter = new Counter();
        newcounter.setACL(acl);
        newcounter.set("title", title);
        newcounter.set("url", url);
        newcounter.set("time", 0);
        allcounter.push(newcounter);
        // 顺便更新显示span为默认值0
        elements[i].textContent=0;
      }
      AV.Object.saveAll(allcounter).then(function (todo) {
        // 成功保存记录之后
        console.log('创建记录成功！');
      }, function (error) {
        // 异常错误 
        console.error('创建记录失败: ' + error.message);
      });
    }
    function showCount(Counter){
      // 是否需要创建新纪录的标志（添加一篇新文章）
      var flag=false;
      var query = new AV.Query(name);
      query.greaterThanOrEqualTo('time', 0);
      query.find().then(function (results) {
        // 当获取到的记录为0时置默认值
        if(results.length==0){
          $('.leancloud_visitors').text('-');
          flag=true;
          console.log('返回查询记录为空');
          // 如果获取到空记录就创建新记录
          createRecord(Counter);
          return;
        }
        // 将获取到的数据设置为text
        for (var i = 0; i < results.length; i++) {
          var item = results[i];
          var url = item.get('url');
          var time = item.get('time');
          var element = document.getElementById(url);
          element.textContent = time;
        }
        // 当某个span含有默认值时说明需要创建记录
        if($('.leancloud_visitors').text().indexOf("-") != -1){
          flag=true;
        }
        // 当获取的记录数与span个数不吻合时
        if(results.length != $('.leancloud_visitors').length){
          flag=true;
        }
        if(flag){
          createRecord(Counter);
        }
      }, function (error) {
        console.log('query error:'+error.message);
      });
    }
    $(function() {
      var Counter = AV.Object.extend(name);
      showCount(Counter);
    });
</script>