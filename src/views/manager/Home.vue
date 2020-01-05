<template>
  <div class="home">
    <!-- 头部图片 -->
    <header class="header">
      <img src="../../assets/home.jpg" alt="">
    </header>
    <!-- 内容区域 -->
    <div>
      <!-- 分类 6个-->
      <van-grid :column-num="3">
        <van-grid-item
          v-for="value in categories"
          :key="value.id"
          :icon="value.icon"
          :text="value.name"
        />
      </van-grid>
      <!-- 产品 n个-->
      <van-grid :column-num="1" icon-size="400px">
        <van-grid-item
          v-for="value in products"
          :key="value.id"
          :icon="value.photo"
          :text="value.name"
        />
      </van-grid>
      <!-- /产品 -->
    </div>
   
  </div>
</template>
<script>
import {get,post} from '../../http/axios';
export default {
  data(){
    return {
      categories:[],
      products:[]
    }
  },
  created(){
    // 查询栏目信息
    this.loadCategories();
    // 查询产品
    this.loadProducts();
  },
  methods:{
    // 加载栏目信息
    loadCategories(){
      let url = "/category/findAll";
      get(url).then((response)=>{
        // 将查询结果，数组中的前6个元素获取到
        this.categories = response.data.slice(0,6);
      })
    },
    // 加载产品信息
    loadProducts(){
      let url = "/product/query"
      let params = { page:0, pageSize:10 }
      post(url,params).then((response)=>{
        this.products = response.data.list;
      })
    }
  }
}
</script>
<style scoped>
.home {
  padding-bottom: 50px;
}
.header {
  height: 300px;
  overflow: hidden;
}
.header img {
  width: 100%;
}
</style>