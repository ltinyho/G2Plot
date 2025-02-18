---
title: 桑基图
order: 27
---

### Plot Container

`markdown:docs/common/chart-options.en.md`

### Data Mapping

#### data

<description>**required** _array object_</description>

设置图表数据源。数据源为对象集合，例如：`[{ source: '支付宝首页', target: '花呗', value: 20 }, ...]`。

#### sourceField

<description>**required** _string_</description>

设置桑基图的来源节点数据字段。比如针对上述数据，就是： `source`。

#### targetField

<description>**required** _string_</description>

设置桑基图的目标节点数据字段。比如针对上述数据，就是： `target`。

#### weightField

<description>**required** _string_</description>

设置节点之间关系的权重字段信息，数据越大，边越大。比如针对上述数据，就是： `value`。

#### rawFields

<description>**optional** _string[_</description>

其他原始字段，便于在节点、边定义 tooltip 或者 label 时取用。

<playground path="relation-plots/sankey/demo/draggable.ts" rid="sankey-raw-fields"></playground>

### Geometry Style

#### nodeStyle

<description>**optional** _StyleAttr | Function_</description>

桑基图节点样式的配置。

#### nodeState

<description>**optional** _StyleAttr | Function_</description>

桑基图节点状态样式的配置。

`markdown:docs/common/state-style.zh.md`

#### edgeStyle

<description>**optional** _StyleAttr | Function_</description>

桑基图变样式的配置。

`markdown:docs/common/color.en.md`

#### edgeState

<description>**optional** _StyleAttr | Function_</description>

桑基图边状态样式的配置。

`markdown:docs/common/state-style.zh.md`

#### nodeWidthRatio

<description>**optional** _number_</description>

桑基图节点的宽度配置，0 ~ 1，参考画布的宽度，默认为 `0.008`。

#### nodeWidthPadding

<description>**optional** _number_</description>

桑基图节点的之间垂直方向的间距，0 ~ 1，参考画布的高度，默认为 `0.01`。

#### nodeAlign

<description>**optional** _string_</description>

桑基图节点的布局方向，默认为 `justify`，可以选择 'left' | 'right' | 'center' | 'justify' 四种方式。

#### nodeDepth

<description>**optional** _Function_</description>

桑基图节点的深度配置，使用回调进行自定义，返回 depth 数值，从 0 开始，并且返回值需要保证所有的层级都有节点。

```ts
{
  nodeDepth: (datum, maxDepth) => {
    const { name } = datum;
    if (name === 'node1') {
      return 0;
    }
    return 1;
  }
}
```

#### nodeDraggable

<description>**optional** _boolean_</description>

决定桑基图中的节点是否可以拖拽位置，默认为 `false`。

```ts
{
  nodeDraggable: true,
}
```

### Plot Event

`markdown:docs/common/events.en.md`

### Plot Method

`markdown:docs/common/chart-methods.en.md`

### Plot Theme

`markdown:docs/common/theme.en.md`
