
<template>
  <!-- 根容器 -->
  <div class="container">
    <div class="btn">
      <router-link to="/new_course">
        <img src="https://static.cdn.oss.mosoteach.cn/mosoteach2/common/images/icon-found.png">
      </router-link>
    </div>
    <div class="tip">
      <p class="tip-p1"> 进行中的班课</p>
      <p class="tip-p2">{{ courses.length }}门班课</p>
    </div>
     <div class="blue">
		 </div>
    <div class="course-conainer">
      <div class="course" v-for="(course, index) in courses" :key="index">
        <div class="course-cover">
          <router-link :to="'/course/' + course.courseId">
            <img :src="course.cover">
          </router-link>
        </div>
        <div class="course-class">
          <p class="title1">{{ course.courseClass }}</p>
          <p class="title2">{{ course.courseName }}</p>
        </div>
        <div class="course-bot">
          <div class="user-ava">
            <img :src="course.avatar">
            <p class="title3">{{course.username}}</p>
          </div>
          <div class="course-code" v-if="loginUserId === course.userId">{{ course.courseCode }}</div>
        </div>
      </div>
    </div>

    <div class="top">
      <p>已结束的班课</p>
      <p>{{ coursesend.length }}门班课</p>
    </div>
    <div class="blue">
		 </div>
    <div class="course-conainer">
      <div class="course" v-for="(course, index) in coursesend" :key="index" style="-webkit-filter: grayscale(1);">
        <div class="course-cover">
          <router-link :to="'/course/' + course.courseId">
            <img :src="course.cover">
          </router-link>
        </div>
        <div class="course-class">
          <p class="title1">{{ course.courseClass }}</p>
          <p class="title2">{{ course.courseName }}</p>
        </div>

        <div class="course-bot">
          <div class="user-ava">
            <img :src="course.avatar">
            <p class="title3">{{course.username}}</p>
          </div>
          <div class="course-code" v-if="loginUserId === course.userId">{{ course.courseCode }}</div>
        </div>
      </div>
    </div>
  </div>
</template>


<script>
export default {
  name: "Index",
  data() {
    return {
      loginUserId: 1,
      courses: [],
      coursesend: []
    };
  },
  methods: {},
  created() {
    var _this = this;
    this.$http
      .get("http://localhost:8080/api/coursesvo")
      .then(function(response) {
        _this.courses = response.data;
      });
    this.$http
      .get("http://localhost:8080/api/coursesvot")
      .then(function(response) {
        _this.coursesend = response.data;
      });
  }
};
</script>

<style>
.container {
  padding-top: 20px;
}
.course-conainer {
  display: flex;
  flex-wrap: wrap;
  padding-left: 70px;
	margin-top: 10px;
  margin-bottom: 40px;
}
.course {
  width: 220px;
  height: 350px;
  margin-right: 20px;
  margin-bottom: 30px;
  background-color: #fff;
  display: flex;
  flex-direction: column;
 
}
.course-cover{
  height: 70%;
}
.course-cover img {
  width: 100%;
  height: 100%;
}

.course-code {
  color: rgb(0, 187, 221);
  margin-right: 10px;
  padding-top: 5px;
}
.user-ava {
  display: flex;
  margin-left: 10px;
}
.user-ava img {
  height: 30px;
  border-radius: 50px;
  margin-right: 10px;
}
.btn {
  margin-left: 70px;
}
.tip {
  display: flex;
  justify-content: space-between;
	margin: 0 70px auto;
}
  .blue{
	width: 90px;
    height: 1px;
    background: #00BBDD;
    margin-top: -1px;
		margin-left: 70px;
}  
.cousre-class{
    font-size: 2px;
    height: 35px;

}
.title1{
   font-size: 14px;
   margin-left: 10px;
}
.title2{
   font-size: 10px;
   color: #666;
   margin-left: 10px;
}
.title3{
  font-size: 10px;
  color: #666;
  margin-bottom: 30px;
}
.course-bot{
  height: 35px;
  display: flex;
  justify-content: space-between;
  margin-bottom: 15px;
}
.top{
  display: flex;
  justify-content: space-between;
	margin: 0 70px auto;
  margin-top: 60px;
}
</style>
