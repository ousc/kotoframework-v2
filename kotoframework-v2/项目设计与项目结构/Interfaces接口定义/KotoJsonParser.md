---
sticker: emoji//1f50c
---
#interface 


> [!NOTE] 简介
> 使用Koto的JSON解析和转换能力时，配置类需继承此接口，我们不限制您使用第三方库如Gson、Jackson、fastjson等实现JSON和各种数据结构之间的转换。

##### 将字符串解析为指定类型T
<span style='color:var(--mk-color-purple)'>fun</span> <span style='color:var(--mk-color-red)'>&lt;T&gt;</span> <span style='color:var(--mk-color-turquoise)'>parseJSON</span>(json: <span style='color:var(--mk-color-red)'>String</span>, kClass: <span style='color:var(--mk-color-teal)'>KClass&lt;*&gt;</span>): <span style='color:var(--mk-color-red)'>T</span>

##### 将变量转换为JSON字符串
<span style='color:var(--mk-color-purple)'>fun</span> <span style='color:var(--mk-color-turquoise)'>toJSONString</span>(obj: <span style='color:var(--mk-color-red)'>Any</span>): <span style='color:var(--mk-color-red)'>String</span>