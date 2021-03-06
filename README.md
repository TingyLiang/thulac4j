# thulac4j

thulac4j是[THULAC](http://thulac.thunlp.org/)的高效Java 8实现，具有分词速度快、准、强的特点；支持

- 自定义词典
- 繁体转简体
- 停用词过滤


## 使用示例

在项目中使用thulac4j，添加依赖：

```xml
<dependency>
  <groupId>io.github.yizhiru</groupId>
  <artifactId>thulac4j</artifactId>
  <version>1.1.0</version>
</dependency>
```

thulac4j支持两种分词模式：

1. SegOnly模式，只分词没有词性标注；
2. SegPos模式，分词兼有词性标注。


```java
// SegOnly mode
String sentence = "滔滔的流水，向着波士顿湾无声逝去";
SegOnly seg = new SegOnly("seg_only.bin");
System.out.println(seg.segment(sentence));
// [滔滔, 的, 流水, ，, 向着, 波士顿湾, 无声, 逝去]

// SegPos mode
SegPos pos = new SegPos("seg_pos.bin");
System.out.println(pos.segment(sentence));
// [滔滔/a, 的/u, 流水/n, ，/w, 向着/p, 波士顿湾/ns, 无声/v, 逝去/v]
```

模型数据较大，没有放在jar包与源码。训练模型下载及更多使用说明，请参看[Getting Started](https://github.com/yizhiru/thulac4j/wiki).


最后感谢THUNLP实验室！没有你们的努力，便没有这么好用的THULAC，也就没有thulac4j。


