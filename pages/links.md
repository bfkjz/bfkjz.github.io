---
layout: mypost
title: 友情链接
---

欢迎各位朋友与我建立友链，如需友链请到[{{ site.linksName }}]({{ site.linksUrl }})提交表单，我看到表单后会添加上的，本站的友链信息如下

```
名称：{{ site.title }}
描述：{{ site.description }}
地址：{{ site.domainUrl }}{{ site.baseurl }}
头像：{{ site.domainUrl }}{{ site.baseurl }}/static/img/logo.jpg
```

<ul style="width: 100%;display: flex;align-items: center;justify-content: center;flex-wrap: wrap;" id="links_list">
  {%- for link in site.links %}
  <li>
    <p><a href="{{ link.url }}" title="{{ link.title }}" target="_blank" style="border-bottom: none;font-weight: 600;display: flex; justify-content: center;align-items: center;color: #666;"><img src="{{ link.icon }}" alt="{{ link.title }}" style="border-radius: 50%;height: 35px;display: inline;margin: 5px;">{{ link.title }}</a></p><p style="color: #b7b7b7;font-size: 0.8em;">{{ link.desc }}</p>
  </li>
  {%- endfor %}
</ul>
