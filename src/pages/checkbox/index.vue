<template>
  <div>
<demo-block title="基本用法">
  <van-checkbox
    :value="checkbox1"
    data-key="checkbox1"
    custom-class="demo-checkbox"
    @change="onChange"
  >
    复选框
  </van-checkbox>
</demo-block>

<demo-block title="禁用状态">
  <van-checkbox
    disabled
    :value="false"
    custom-class="demo-checkbox"
  >
    复选框
  </van-checkbox>
  <van-checkbox
    disabled
    :value="true"
    custom-class="demo-checkbox"
  >
    复选框
  </van-checkbox>
</demo-block>

<demo-block title="自定义颜色">
  <van-checkbox
    :value="checkbox2"
    checked-color="#4b0"
    custom-class="demo-checkbox"
    data-key="checkbox2"
    @change="onChange"
  >
    复选框
  </van-checkbox>
</demo-block>

<demo-block title="自定义图标">
  <van-checkbox
    use-icon-slot
    :value="checkbox3"
    custom-class="demo-checkbox"
    data-key="checkbox3"
    @change="onChange"
  >
    自定义图标
    <image mode="widthFix" slot="icon" :src="checkbox3 ? icon.active : icon.normal" class="icon" />
  </van-checkbox>
</demo-block>

<demo-block title="复选框组">
  <van-checkbox-group :value="result" data-key="result" @change="onChange">
    <van-checkbox
      v-for="(item,index) in list"
      :key="index"
      :name="item"
      custom-class="demo-checkbox"
    >
      复选框 {{ item }}
    </van-checkbox>
  </van-checkbox-group>
</demo-block>

<demo-block title="设置最大可选数">
  <van-checkbox-group :value="result2" data-key="result2" max="2" @change="onChange">
    <van-checkbox
      v-for="(item,index) in list"
      :key="index"
      :name="item"
      custom-class="demo-checkbox"
    >
      复选框 {{ item }}
    </van-checkbox>
  </van-checkbox-group>
</demo-block>

<demo-block title="搭配单元格组件使用">
  <van-checkbox-group :value="result3" data-key="result3" @change="onChange">
    <van-cell-group >
      <van-cell
        v-for="(item,index) in list"
        :key="index"
        :title="'复选框'+item"
        value-class="value-class"
        clickable
        :data-name="item"
        @click="toggle"
      >
        <van-checkbox @click.stop="noop" :class="'checkboxes-'+item" :name="item" />
      </van-cell>
    </van-cell-group>
  </van-checkbox-group>
</demo-block>

</div>
</template>

<script>

export default {
  data () {
    return {
      checkbox1: true,
      checkbox2: true,
      checkbox3: true,
      list: ['a', 'b', 'c'],
      result: ['a', 'b'],
      result2: [],
      result3: [],
      icon: {
        normal:
          'https://img.yzcdn.cn/public_files/2017/10/13/c547715be149dd3faa817e4a948b40c4.png',
        active:
          'https://img.yzcdn.cn/public_files/2017/10/13/793c77793db8641c4c325b7f25bf130d.png'
      }
    }
  },
  methods:{
  onChange(event) {
    console.log(event)
    const { key } = event.currentTarget.dataset;
    this[key]=event.mp.detail;
  },

  onClick(event) {
    const { value } = event.currentTarget.dataset;
    this.radio3=value;
  },

  toggle(event) {
    const { name } = event.currentTarget.dataset;
    const checkbox = this.$mp.page.selectComponent(`.checkboxes-${name}`);
    checkbox.toggle();
  },
  noop() {
    console.log("hh")
  }
  }
}
</script>

<style>
.block {
  top: 50%;
  left: 50%;
  width: 100px;
  height: 100px;
  position: fixed;
  margin: -50px 0 0 -50px;
  background-color: #1989fa;
}



</style>
