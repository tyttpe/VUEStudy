<template>
  <div id="app">
    <div class="header">
      <div class="myclass">
      <router-link to="/" class="logo"><img src="https://static.cdn.oss.mosoteach.cn/mosoteach2/common/images/logo.png"></router-link>
      </div>
      <router-link to="/task" class="nav-item">任务中心</router-link>
      <router-link to="/lib" class="nav-item">库管理</router-link>
      <router-link to="/ucenter" class="nav-item">tyttpe</router-link>
    </div>
    <div class="container">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
export default {
  name: "App"
};
</script>

<style>
#app {
	background-color: rgb(244, 244, 244);
}
.header {
	display: flex;
	height: 45px;
	background-color: #fff;
	font-size: 20px;
	padding-left: 280px;
	align-items: center;
}
.nav-item {
	width: 100px;
	margin-right: 20px;
}
.logo{
	widows: 100px;
	height: 35px;
	margin-right: 200px;
}
.logo img{
  height: 33px;
}
.container {
	width: 85%;
	margin: 0 auto;
	padding-bottom: 40px;
}
a {
	text-decoration: none;
	color: #aaa;
}
a:hover {
	color: rgb(2,165,218);
}
</style>
