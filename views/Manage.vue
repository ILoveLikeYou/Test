<template>
    <el-container style="min-height: 100vh;">
<!--      //侧边栏-->
      <el-aside :width="sideWidth+'px'" style="background-color: rgb(238, 241, 246);box-shadow: 2px 0px 6px rgba(0,21,41, 0.35);">
        <Aside :isCollapse="isCollapse" :logoTextShow="logoTextShow"/>
      </el-aside>
<!--      //头部-->
      <el-container>
        <el-header style="border-bottom: 1px solid #cccccc;">
          <Header :collapseBtnClass="collapseBtnClass" :collapse="collapse" />

        </el-header>

<!--        //主体-->
        <el-main>
<!--          表示当前页面的子路由会在router-view 展示-->
          <router-view />
        </el-main>
      </el-container>
    </el-container>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
// import request from "@/utils/request";
import Aside from "@/components/Aside";
import Header from "@/components/Header";

export default {
  name: 'Manage',
  components: {
    // HelloWorld,
    Aside,
    Header
  },
  data() {
    return {

      msg:"Hello Boy",
      collapseBtnClass: 'el-icon-s-fold',
      isCollapse:false,
      sideWidth:200,
      logoTextShow:true,

    }
  },
  methods: {
    collapse() {
      this.isCollapse=!this.isCollapse;
      if(this.isCollapse)
        {
          this.sideWidth=64
          this.collapseBtnClass='el-icon-s-unfold'
          this.logoTextShow=false
        }else{
        this.sideWidth=200
        this.collapseBtnClass='el-icon-s-fold'
        this.logoTextShow=true
      }
    },
  }
}
</script>
