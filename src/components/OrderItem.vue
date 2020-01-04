<template>
  <div class="order_item">
    <van-row class="header"> 
      <van-col span="12">工单编号: {{data.id}}</van-col>
      <van-col span="12" class="status">{{data.status}}</van-col>
    </van-row>
    <van-row>
      <van-col :span="24" :offset="1">
        <div>工程编号：GC20129</div>
        <div>设备编号：HX21021</div>
        <div>工单类型：装机</div>
        <div>服务时间：{{data.orderTime | datefmt}}</div>
        <div>服务地点：江苏省苏州市工业园区xxx号</div>
      </van-col>
    </van-row>
    <div class="text-right">
      共计 个服务，合计￥ {{data.total}}
    </div>
  </div>
</template>
<script>
export default {
  props:{
    data:{type:Object}
  }
}
</script>
<style scoped>
.order_item {
  margin: .5em 1em;
  padding: .5em;
  border-radius: 5px;
  background: #ffffff;
}
.order_item .header {
  line-height: 2.5em;
  font-size: 14px;
}
.order_item .header .status {
  text-align: right;
  font-size: 12px;
  color: #fd621f;
}
.order_item img {
  width: 100%;
  border-radius: 3px;
}


</style>