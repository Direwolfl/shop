<template>
  <div>
    <el-container class="container">
      <el-header class="header">
        <el-row :gutter="15">
          <el-col :span="10">
            <div class="grid-content bg-purple">
              <img src="../assets/logo.png" alt>
            </div>
          </el-col>
          <el-col :span="10">
            <h3>电商后台管理系统</h3>
          </el-col>
          <el-col :span="1" class="tuichu">
            <a href @click.prevent="handleLogin()">退出</a>
          </el-col>
        </el-row>
      </el-header>
      <el-container>
        <el-aside class="asde" width="200px">
          <el-menu
            router
            default-active="2"
            class="el-menu-vertical-demo"
            @open="handleOpen"
            @close="handleClose"
          >
            <el-submenu index="1">
              <template slot="title">
                <i class="el-icon-location"></i>
                <span>用户管理</span>
              </template>
              <el-menu-item index="1-3">
                <i class="el-icon-location"></i>
                用户列表
              </el-menu-item>
            </el-submenu>

            <el-submenu index="2">
              <template slot="title">
                <i class="el-icon-location"></i>
                <span>权限管理</span>
              </template>
              <el-menu-item index="1-3">
                <i class="el-icon-location"></i>
                角色列表
              </el-menu-item>
              <el-menu-item index="1-3">
                <i class="el-icon-location"></i>
                权限列表
              </el-menu-item>
            </el-submenu>

            <el-submenu index="3">
              <template slot="title">
                <i class="el-icon-location"></i>
                <span>商品管理</span>
              </template>
              <el-menu-item index="1-3">
                <i class="el-icon-location"></i>
                商品列表
              </el-menu-item>
              <el-menu-item index="1-3">
                <i class="el-icon-location"></i>
                分类参数
              </el-menu-item>
              <el-menu-item index="1-3">
                <i class="el-icon-location"></i>
                商品分类
              </el-menu-item>
            </el-submenu>

            <el-submenu index="4">
              <template slot="title">
                <i class="el-icon-location"></i>
                <span>订单管理</span>
              </template>
              <el-menu-item index="1-3">
                <i class="el-icon-location"></i>
                订单列表
              </el-menu-item>
            </el-submenu>

            <el-submenu index="5">
              <template slot="title">
                <i class="el-icon-location"></i>
                <span>数据统计</span>
              </template>
              <el-menu-item index="1-3">
                <i class="el-icon-location"></i>
                数据报表
              </el-menu-item>
            </el-submenu>
          </el-menu>
        </el-aside>
        <el-main class="main">Main</el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
export default {
  beforeCreate() {
    if (!localStorage.getItem("token")) {
      this.$router.push({
        name: "login"
      });
      this.$message.warning("请先登录");
    }
  },

  methods: {
    handleLogin() {
      localStorage.clear();
      this.$router.push({
        name: "login"
      });
    }
  }
};
</script>

<style>
.container {
  background-color: beige;
  height: 100%;
}
.tuichu a {
  line-height: 60px;
  text-decoration: none;
}
</style>
