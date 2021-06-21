<template>
  <div>
    <div class="side_show">
      <div>
        <span>雨纷纷</span>
        <el-divider direction="vertical"></el-divider>
        <span>旧故里</span>
        <el-divider direction="vertical"></el-divider>
        <span>草木深</span>
        <el-divider></el-divider>
      </div>
      <el-carousel height="500px">
        <el-carousel-item>
          <img src="@/assets/imgs/banner02.jpg"  width="1496px" alt="">
        </el-carousel-item>
        <el-carousel-item>
          <img src="@/assets/imgs/banner03.jpg" width="1496px" alt="">
        </el-carousel-item>
        <el-carousel-item>
          <img src="@/assets/imgs/banner04.jpg" width="1496px" alt="">
        </el-carousel-item>
        <el-carousel-item>
          <img src="@/assets/imgs/banner01.jpg" width="1496px" alt="">
        </el-carousel-item>
      </el-carousel>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
    }
  },
}
</script>

<style lang="scss" scoped>
.side_show {
  width: 100%;
  height: 100%;
  .el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 150px;
    margin: 0;
  }

  .el-carousel__item:nth-child(2n) {
     background-color: #99a9bf;
  }
  
  .el-carousel__item:nth-child(2n+1) {
     background-color: #d3dce6;
  }

  /deep/ .el-carousel__indicator {
    .el-carousel__button {
      background-color: #333;
    }
  }
}
</style>