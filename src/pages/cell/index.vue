<template>
  <div>
  <demo-block title="基础用法">
  <van-cell-group>
    <van-cell title="单元格" value="内容" />
    <van-cell
      title="单元格"
      value="内容"
      label="描述信息"
      :border="false"
    />
  </van-cell-group>
</demo-block>

<demo-block title="单元格大小">
  <van-cell-group>
    <van-cell
      title="单元格"
      value="内容"
      size="large"
    />
    <van-cell
      title="单元格"
      value="内容"
      label="描述信息"
      size="large"
      :border="false"
    />
  </van-cell-group>
</demo-block>

<demo-block title="展示图标">
  <van-cell
    title="单元格"
    icon="location-o"
    :border="false"
  />
</demo-block>

<demo-block title="展示箭头">
  <van-cell title="单元格" is-link />
  <van-cell
    title="单元格"
    value="内容"
    is-link
  />
  <van-cell
    title="单元格"
    is-link
    arrow-direction="down"
    value="内容"
    :border="false"
    url="/pages/dashboard/main"
  />
</demo-block>

<demo-block title="高级用法">
  <van-cell value="内容" icon="shop-o" is-link>
    <div slot="title">
      <div class="title">单元格</div>
      <van-tag type="danger">标签</van-tag>
    </div>
  </van-cell>
  <van-cell title="单元格" icon="location-o" is-link />
  <van-cell title="单元格" :border="false">
    <van-icon slot="right-icon" name="search" />
  </van-cell>
</demo-block>

</div>
</template>

<script>

export default {
  data () {
    return {

    }
  }
}
</script>

<style scoped>
.title {
  margin-right: 5px;
  display: inline-block;
  vertical-align: middle;
}


</style>
