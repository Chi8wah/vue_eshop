<template>
  <el-container class="homeContainer">
<!--    头部区域-->
    <el-header>
      <div>
        <img src="../assets/mallLogo.jpg" alt="" id="mallLogo">
        <span>电商后台管理系统</span>
      </div>
      <el-button type="info" @click="logout">退出</el-button>
    </el-header>
<!--    主题区域-->
    <el-container>
<!--      左侧边栏-->
      <el-aside width="200px">
<!--        侧边栏菜单区域-->
        <el-menu
          background-color="#333744"
          text-color="#fff"
          active-text-color="#ffd04b">
<!--          一级菜单-->
          <el-submenu index="1">
<!--            菜单模板区-->
            <template slot="title">
<!--              图标-->
              <i class="el-icon-location"></i>
<!--              文本-->
              <span>导航一</span>
            </template>
<!--            二级菜单-->
            <el-menu-item index="1-4-1">
              <template slot="title">
              <!--              图标-->
              <i class="el-icon-location"></i>
              <!--              文本-->
              <span>导航一</span>
            </template>
            </el-menu-item>
          </el-submenu>
        </el-menu>
      </el-aside>
<!--      右侧内容主题-->
      <el-main>
        Main
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  name: 'Home',
  methods: {
    logout () {
      window.sessionStorage.clear()
      this.$router.push('/login')
    }
  }
}
</script>

<style lang="less" scoped>

  .homeContainer{
    height: 100%;
  }

  .el-header{
    background-color: #373D41;
    display: flex;
    justify-content: space-between;
    padding-left: 0;
    align-items: center;
    color: #FFFFFF;
    font-size: 20px;

    > div{
      height: 100%;
      display: flex;
      align-items: center;

      span{
        margin-left: 15px;
      }
    }
  }

  #mallLogo{
    height: 100%;
  }

  .el-aside{
    background-color: #333744;
  }

  .el-main{
    background-color: #EAEDF1;
  }

</style>
