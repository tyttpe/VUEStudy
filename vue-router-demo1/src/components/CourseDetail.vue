<template>
  <div class="container">
    <h2>班课{{ id }}详情页面</h2>
    <div class="pho">
      <img :src="course.cover">
    </div>
    <p>课程名：{{course.courseName}}</p>
    <p>班级号：{{course.courseClass}}</p>
    <button @click="updateCourse(course)" v-if="result === course.userId && result != course.finished" >结束</button>
    <button @click="deleteCourse(course.courseId,index)" class="btn">删除</button>
  </div>
</template>

<script>
export default {
  name: "CourseDetail",
  data() {
    return {
      id: this.$route.params.id,
      result: 1,
      course: {}
    };
  },
  created() {
    var _this = this;
    this.$http
      .get("http://localhost:8080/api/course/" + this.id)
      .then(function(response) {
        _this.course = response.data;
      });
  },
  methods: {
    deleteCourse: function(courseId, index) {
      var _this = this;
      this.$http({
        method: "delete",
        url: "http://localhost:8080/api/course/" + this.id
      }).then(function() {
        alert("班课删除成功");
        _this.$router.push("/");
        _this.courses.splice(index, 1);
      });
    },
    updateCourse: function(course) {
      var _this = this;
      this.$http({
        method: "put",
        url: "http://localhost:8080/api/course",
        data: {
          courseId: course.courseId,
          courseName: course.courseName,
          userId: this.id,
          courseClass: course.courseClass,
          cover: course.cover,
          courseCode: course.courseCode,
          finished: 1
        }
      }).then(function() {
        alert("班课结束");
        _this.$router.push("/");
      });
    }
  }
};
</script>
<style>
.container img{
  width: 100%;
  height: 100%;
}
.pho{
  width: 200px;
  height: 200px;
}
</style>
