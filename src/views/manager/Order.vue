<template>
  <div class="order">
    <van-nav-bar title="我的订单" />
    <van-tabs v-model="active" color="#1659a0">
      <van-tab title="全部">
      </van-tab>
      <van-tab title="未开始">
      </van-tab>
      <van-tab title="进行中">
      </van-tab> 
      <van-tab title="已完成">
      </van-tab>
    </van-tabs>
  </div>
</template>
<script>
import { mapActions, mapState ,mapGetters} from 'vuex'
export default {
  data(){
    return {
      active:0
    }
  }
}
</script>
<style scoped>
.order {
  background: #f1f1f1;
}
</style>