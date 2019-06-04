# paji-components

一些自己用的组件:

## button 组件

使用方法:

```VUE
<Template>
  <Button
    type="primary"
    size="default"
    @click="clickFunc"
  >
    按钮
  </Button>
</Template>
<script>
import { Button } from 'paji-components'
export default {
  components: {
    Button
  },
  methods: {
    clickFunc(e) {
      console.log(e);
    }
  }
};
</script>

```

参数:

| 属性名   | 解释              | 属性值                 | 备注          |
| -------- | ----------------- | ---------------------- | ------------- |
| type     | button 按钮的颜色 | primary,submit,default | 默认: primary |
| size     | button 的大小     | large,default,small    | 默认:default  |
| disabled | button 是否可用   | true,false             | 默认:false    |
| 事件     |                   |                        |               |
| click    | 点击事件          | function               |               |
