<a name="kdRnf"></a>

## 开发工具

VS Code
<a name="zzWOF"></a>

## 脚手架工具

pnpm
<a name="liO2M"></a>

## UI 相关框架

- vue3
- vite
- @antv/s2
- ant-design-vue
- @ant-design/icons-vue
- [@antv/s2-vue](https://github.com/antvis/S2/tree/master/packages/s2-vue)
  <a name="aEWuM"></a>

## 创建项目

```bash
pnpm create vite
```

中间过程按步骤选择
<a name="CiVYu"></a>

## 安装依赖包

使用 VS Code 打开项目文件夹后，打开一个终端，如下图

```bash
pnpm install
```

```bash
 pnpm install @antv/s2
```

```bash
pnpm i --save ant-design-vue
```

```bash
pnpm i --save @ant-design/icons-vue
```

```bash
pnpm install @antv/s2-vue
```

:::warning
注意:在 vite4+vue3 创建的项目里,还需要添加以下的包才能正常运行

- @antv/s2
- ant-design-vue
- @ant-design/icons-vue
  :::
  <a name="zM2dl"></a>

## 使用

<a name="Li10E"></a>

### 组件配置

```vue
<script lang="ts">
import type { S2DataConfig, S2Options } from "@antv/s2";
import { SheetComponent } from "@antv/s2-vue";
import { defineComponent, onMounted, reactive, shallowRef } from "vue";
import "@antv/s2-vue/dist/style.min.css";

const s2DataConfig = {
  fields: {
    rows: ["province", "city"],
    columns: ["type", "sub_type"],
    values: ["number"],
  },
  meta: [
    {
      field: "number",
      name: "数量",
    },
    {
      field: "province",
      name: "省份",
    },
    {
      field: "city",
      name: "城市",
    },
    {
      field: "type",
      name: "类别",
    },
    {
      field: "sub_type",
      name: "子类别",
    },
  ],
  data: [
    {
      number: 7789,
      province: "浙江省",
      city: "杭州市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 2367,
      province: "浙江省",
      city: "绍兴市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 3877,
      province: "浙江省",
      city: "宁波市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 4342,
      province: "浙江省",
      city: "舟山市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 5343,
      province: "浙江省",
      city: "杭州市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 632,
      province: "浙江省",
      city: "绍兴市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 7234,
      province: "浙江省",
      city: "宁波市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 834,
      province: "浙江省",
      city: "舟山市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 945,
      province: "浙江省",
      city: "杭州市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 1304,
      province: "浙江省",
      city: "绍兴市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 1145,
      province: "浙江省",
      city: "宁波市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 1432,
      province: "浙江省",
      city: "舟山市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 1343,
      province: "浙江省",
      city: "杭州市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 1354,
      province: "浙江省",
      city: "绍兴市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 1523,
      province: "浙江省",
      city: "宁波市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 1634,
      province: "浙江省",
      city: "舟山市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 1723,
      province: "四川省",
      city: "成都市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 1822,
      province: "四川省",
      city: "绵阳市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 1943,
      province: "四川省",
      city: "南充市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 2330,
      province: "四川省",
      city: "乐山市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 2451,
      province: "四川省",
      city: "成都市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 2244,
      province: "四川省",
      city: "绵阳市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 2333,
      province: "四川省",
      city: "南充市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 2445,
      province: "四川省",
      city: "乐山市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 2335,
      province: "四川省",
      city: "成都市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 245,
      province: "四川省",
      city: "绵阳市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 2457,
      province: "四川省",
      city: "南充市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 2458,
      province: "四川省",
      city: "乐山市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 4004,
      province: "四川省",
      city: "成都市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 3077,
      province: "四川省",
      city: "绵阳市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 3551,
      province: "四川省",
      city: "南充市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 352,
      province: "四川省",
      city: "乐山市",
      type: "办公用品",
      sub_type: "纸张",
    },
  ],
};

const rawOptions: S2Options = {
  width: 980,
  height: 680,
};

export default defineComponent({
  setup() {
    const s2 = shallowRef();
    // dataCfg 数据字段较多，建议使用 shallow, 如果有数据更改直接替换整个对象
    const dataCfg = shallowRef(s2DataConfig);
    const options: S2Options = reactive(rawOptions);

    onMounted(() => {
      console.log("s2 instance:", s2.value?.instance);
    });
    return {
      s2,
      dataCfg,
      options,
    };
  },

  components: {
    SheetComponent,
  },
});
</script>

<template>
  <SheetComponent ref="s2" :dataCfg="dataCfg" :options="options" />
</template>
```

<a name="fx4VH"></a>

### 测试数据

```typescript
const s2DataConfig = {
  fields: {
    rows: ["province", "city"],
    columns: ["type", "sub_type"],
    values: ["number"],
  },
  meta: [
    {
      field: "number",
      name: "数量",
    },
    {
      field: "province",
      name: "省份",
    },
    {
      field: "city",
      name: "城市",
    },
    {
      field: "type",
      name: "类别",
    },
    {
      field: "sub_type",
      name: "子类别",
    },
  ],
  data: [
    {
      number: 7789,
      province: "浙江省",
      city: "杭州市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 2367,
      province: "浙江省",
      city: "绍兴市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 3877,
      province: "浙江省",
      city: "宁波市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 4342,
      province: "浙江省",
      city: "舟山市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 5343,
      province: "浙江省",
      city: "杭州市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 632,
      province: "浙江省",
      city: "绍兴市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 7234,
      province: "浙江省",
      city: "宁波市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 834,
      province: "浙江省",
      city: "舟山市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 945,
      province: "浙江省",
      city: "杭州市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 1304,
      province: "浙江省",
      city: "绍兴市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 1145,
      province: "浙江省",
      city: "宁波市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 1432,
      province: "浙江省",
      city: "舟山市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 1343,
      province: "浙江省",
      city: "杭州市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 1354,
      province: "浙江省",
      city: "绍兴市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 1523,
      province: "浙江省",
      city: "宁波市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 1634,
      province: "浙江省",
      city: "舟山市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 1723,
      province: "四川省",
      city: "成都市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 1822,
      province: "四川省",
      city: "绵阳市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 1943,
      province: "四川省",
      city: "南充市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 2330,
      province: "四川省",
      city: "乐山市",
      type: "家具",
      sub_type: "桌子",
    },
    {
      number: 2451,
      province: "四川省",
      city: "成都市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 2244,
      province: "四川省",
      city: "绵阳市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 2333,
      province: "四川省",
      city: "南充市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 2445,
      province: "四川省",
      city: "乐山市",
      type: "家具",
      sub_type: "沙发",
    },
    {
      number: 2335,
      province: "四川省",
      city: "成都市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 245,
      province: "四川省",
      city: "绵阳市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 2457,
      province: "四川省",
      city: "南充市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 2458,
      province: "四川省",
      city: "乐山市",
      type: "办公用品",
      sub_type: "笔",
    },
    {
      number: 4004,
      province: "四川省",
      city: "成都市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 3077,
      province: "四川省",
      city: "绵阳市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 3551,
      province: "四川省",
      city: "南充市",
      type: "办公用品",
      sub_type: "纸张",
    },
    {
      number: 352,
      province: "四川省",
      city: "乐山市",
      type: "办公用品",
      sub_type: "纸张",
    },
  ],
};
```

<a name="kr1pJ"></a>

### 渲染

```vue
<script setup lang="ts">
//import HelloWorld from './components/HelloWorld.vue';

import TestS2Demo from "./components/TestS2Demo.vue";
</script>

<template>
  <TestS2Demo />
</template>

<style scoped></style>
```

<a name="rlNOE"></a>

### 运行

![1676256883792.png](https://cdn.nlark.com/yuque/0/2023/png/12561771/1676256899630-19cfec3a-51fa-445a-a356-31e1df8fb598.png#averageHue=%23f4f7fc&clientId=u754c564f-b84b-4&from=paste&height=474&id=ueb81cf15&name=1676256883792.png&originHeight=474&originWidth=1189&originalType=binary&ratio=1&rotation=0&showTitle=false&size=24821&status=done&style=none&taskId=ue4429053-1fd7-475f-b502-d1f5169e570&title=&width=1189)
