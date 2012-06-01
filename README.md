ouch-words-cn
=============

中文敏感词库

近日，[google](http://www.google.com.hk)在其中文搜索引擎中加入了敏感词提醒功能。

网站开发中也许用得到这个敏感词库；github上似乎也没有这个repository；再加上可以对那些奇葩的敏感词，例如：“麦当劳”，不可思议的大笑一番。
所以建个库也没啥坏处。

数据格式方面，JSON和XML比较通用点，就选比较简单的JSON格式好了，noSql数据库也能用的上。

对于敏感词，暂时想到两个属性，一个当然是名字，还有一个是最近被验证为敏感的时间，因为词库肯定是不断更行的，所以这个时间可能还是需要的，过期的词可能影响到正常使用。
其他属性欢迎客官们提供思路。
所以数据格式暂时是这个样子：

```javascript
var ouchWordsCN = [
  {
    word : String, //该词
    lastVerifiedDate : "yyyy-mm-ddThh:mm:ss" //
  },
  {
    word : ...,
    lastVerifiedDate : ...
  },
  {
    ...
  },
  ...
]
```

可以使用javascript解析时间，转换成自 1 January 1970 00:00:00 UTC 以来的毫秒数;也可以将该毫秒数使用toJSON，转换回字符串：
```javascript
Date.parse(lastVerifiedDate);//to milliseconds
(new Date()).toJSON();//to string
```

欢迎推送已知的词库。我先把麦当劳加上去。

如果因为该项目影响到了github在国内的交通，或者让*有关部门*看得心头作呕，在issue list发条问题，我就义不容辞马上删掉它。*Please don't kuashen me*


For English Users

This is a part of China, but just a part.