<template>
  <div class="detail_page">
    <div class="box">
      <div class="image">
        <img v-if="curId == 1" src="@/assets/imgs/goods01.webp" alt="">
        <img v-else-if="curId == 2" src="@/assets/imgs/goods02.webp" alt="">
        <img v-else-if="curId == 3" src="@/assets/imgs/goods03.webp" alt="">
        <img v-else-if="curId == 4" src="@/assets/imgs/goods04.webp" alt="">
        <img v-else-if="curId == 5" src="@/assets/imgs/goods05.webp" alt="">
        <img v-else-if="curId == 6" src="@/assets/imgs/goods06.webp" alt="">
        <img v-else-if="curId == 7" src="@/assets/imgs/goods07.webp" alt="">
        <img v-else-if="curId == 8" src="@/assets/imgs/goods08.webp" alt="">
        <img v-else-if="curId == 9" src="@/assets/imgs/goods09.webp" alt="">
        <img v-else-if="curId == 10" src="@/assets/imgs/goods10.webp" alt="">
        <img v-else-if="curId == 11" src="@/assets/imgs/goods11.webp" alt="">
        <img v-else-if="curId == 12" src="@/assets/imgs/goods12.webp" alt="">
        <img v-else-if="curId == 13" src="@/assets/imgs/goods13.webp" alt="">
      </div>
      <div class="right">
        <h1>夏季新款韩版小个子显瘦气质A字裙Polo领单排扣连衣裙短裙子</h1>
        <div class="price_desc">
          <span>价格: <span style="color: rgb(252, 126, 147);fontSize:24px">￥89.60</span></span>
          <span>评价: 91  累计销量: 590</span>
        </div>
        <div class="goods_color">
          <span>颜色： </span>
          <el-radio-group v-model="color">
            <el-radio-button label="灰色"></el-radio-button>
            <el-radio-button label="黑色"></el-radio-button>
          </el-radio-group>
        </div>
        <div class="goods_size">
          <span>尺寸： </span>
          <el-radio-group v-model="size">
            <el-radio-button label="S"></el-radio-button>
            <el-radio-button label="M"></el-radio-button>
            <el-radio-button label="L"></el-radio-button>
          </el-radio-group>
        </div>
        <div class="goods_count">
          <el-button type="primary" @click="addShop">加入购物车</el-button>
          <el-button type="plain" @click="toDeal">去结算</el-button>

        </div>
        <div class="service">
          <span>服务： </span>
          <span class="service_item"><i class="el-icon-check" style="width: 20px; height: 20px; borderRadius: 20px; border: 2px solid red; color: red"></i><span style="fontSize: 12px; marginLeft: 5px">72小时发货</span></span>
          <span class="service_item"><i class="el-icon-check" style="width: 20px; height: 20px; borderRadius: 20px; border: 2px solid red; color: red"></i><span style="fontSize: 12px; marginLeft: 5px">7天无理由退货</span></span>
          <span class="service_item"><i class="el-icon-check" style="width: 20px; height: 20px; borderRadius: 20px; border: 2px solid red; color: red"></i><span style="fontSize: 12px; marginLeft: 5px">延误必赔</span></span>
          <span class="service_item"><i class="el-icon-check" style="width: 20px; height: 20px; borderRadius: 20px; border: 2px solid red; color: red"></i><span style="fontSize: 12px; marginLeft: 5px">退货补运费</span></span>
          <span class="service_item"><i class="el-icon-check" style="width: 20px; height: 20px; borderRadius: 20px; border: 2px solid red; color: red"></i><span style="fontSize: 12px; marginLeft: 5px">全国包邮</span></span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      curId: 1,
      color: '',
      size: ''
    }
  },
  created() {
    this.curId = this.$route.params.id
  },
  methods: {
    addShop() {
      if(!this.color || !this.size) {
        this.$message.warning('请先选择衣服颜色和尺码！')
        return
      }
      this.$notify({
          title: '成功',
          message: '添加购物车成功',
          type: 'success',
          duration: 1000
        });
    },
    toDeal() {
      this.$router.push('/home/shopping')
    }
  }
}
</script>

<style lang="scss" scoped>
.detail_page {
  .box {
    width: 1058px;
    height: 552px;
    margin: 0 auto;
    display: flex;
    img {
        width: 400px;
      }
    .right {
      flex: 1;
      padding: 0 40px;
      h1 {
        font-size: 24px;
      }
      .price_desc {
        background-color: #ddd;
        color: #000;
        display: flex;
        justify-content: space-between;
        line-height: 32px;
        padding: 0 10px;
      }
      .goods_color {
        padding: 20px 10px;
        .el-button {
          border-radius: 0;
        }
      }
      .goods_size {
        padding: 0px 10px;
      }
      .goods_count {
        padding: 20px 60px;
      }
      .service {
        padding: 0 10px;
        .service_item {
          margin-right: 5px;
        }
      }
    }
  }
}
</style>