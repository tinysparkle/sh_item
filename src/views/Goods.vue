<template>
  <div class="goods">
    <el-row :gutter="20" type="flex" justify="space-between">
      <el-col :span="6">
        <div class="goods_item" @click="toDetail(1)">
          <img src="@/assets/imgs/goods01.webp" alt="">
          <div class="goods_item_desc">
            <div class="goods_item_title">夏季新款韩版小个子显瘦气质A字裙Polo领单排扣连衣裙短裙子</div>
            <div class="goods_item_footer">
              <span>￥89.6</span><span>3459<i class="el-icon-star-off"></i></span>
            </div>
          </div>
        </div>
      </el-col>
      <el-col :span="6">
        <div class="goods_item" @click="toDetail(2)">
          <img src="@/assets/imgs/goods02.webp" alt="">
          <div class="goods_item_desc">
            <div class="goods_item_title">新款宽松裙子仙女超仙森系学生气质长裙夏季女神范连衣裙显瘦显高</div>
            <div class="goods_item_footer">
              <span>￥189.6</span><span>359<i class="el-icon-star-off"></i></span>
            </div>
          </div>
        </div>
      </el-col>
      <el-col :span="6">
        <div class="goods_item" @click="toDetail(3)">
          <img src="@/assets/imgs/goods03.webp" alt="">
          <div class="goods_item_desc">
            <div class="goods_item_title">小个子气质桔梗裙子仙女超仙森系法式长裙收腰显瘦红色连衣裙女夏
        </div>
            <div class="goods_item_footer">
              <span>￥109.0</span><span>2419<i class="el-icon-star-off"></i></span>
            </div>
          </div>
        </div>
      </el-col>
      <el-col :span="6">
        <div class="goods_item" @click="toDetail(4)">
          <img src="@/assets/imgs/goods04.webp" alt="">
          <div class="goods_item_desc">
            <div class="goods_item_title">夏季新款韩版小个子显瘦气质A字裙Polo领单排扣连衣裙短裙子</div>
            <div class="goods_item_footer">
              <span>￥123.6</span><span>1823<i class="el-icon-star-off"></i></span>
            </div>
          </div>
        </div>
      </el-col>
      <el-col :span="6">
        <div class="goods_item" @click="toDetail(5)">
          <img src="@/assets/imgs/goods05.webp" alt="">
          <div class="goods_item_desc">
            <div class="goods_item_title">长款过膝百搭打底小黑裙女2021夏季新款韩版显瘦气质连衣裙女</div>
            <div class="goods_item_footer">
              <span>￥99.0</span><span>3000<i class="el-icon-star-off"></i></span>
            </div>
          </div>
        </div>
      </el-col>
    </el-row>
    <el-row :gutter="20" type="flex" justify="space-between">
        <el-col :span="6">
          <div class="goods_item" @click="toDetail(6)">
            <img src="@/assets/imgs/goods06.webp" alt="">
            <div class="goods_item_desc">
              <div class="goods_item_title">夏季流行赫本风小黑裙女收腰显瘦不规则时尚气质可盐可甜连衣裙女
          </div>
              <div class="goods_item_footer">
                <span>￥88.6</span><span>2399<i class="el-icon-star-off"></i></span>
              </div>
            </div>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="goods_item" @click="toDetail(7)">
            <img src="@/assets/imgs/goods07.webp" alt="">
            <div class="goods_item_desc">
              <div class="goods_item_title">夏季新款复古法式裙子女学生网红小个子显瘦收腰气质连衣裙潮女</div>
              <div class="goods_item_footer">
                <span>￥167.8</span><span>2138<i class="el-icon-star-off"></i></span>
              </div>
            </div>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="goods_item" @click="toDetail(8)">
            <img src="@/assets/imgs/goods08.webp" alt="">
            <div class="goods_item_desc">
              <div class="goods_item_title">egg法式初恋冷淡风A字裙港味小香风收腰显瘦气质碎花连衣裙女
           </div>
              <div class="goods_item_footer">
                <span>￥79.6</span><span>711<i class="el-icon-star-off"></i></span>
              </div>
            </div>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="goods_item" @click="toDetail(9)">
            <img src="@/assets/imgs/goods09.webp" alt="">
            <div class="goods_item_desc">
              <div class="goods_item_title">胖妹妹遮肉显瘦连衣裙女夏季新款小个子仙女裙气法式复古裙子</div>
              <div class="goods_item_footer">
                <span>￥85.8</span><span>275<i class="el-icon-star-off"></i></span>
              </div>
            </div>
          </div>
        </el-col>
        <el-col :span="6">
          <div class="goods_item" @click="toDetail(10)">
            <img src="@/assets/imgs/goods10.webp" alt="">
            <div class="goods_item_desc">
              <div class="goods_item_title">大码春季新款裙子仙女超仙森系学生气质女神范连衣裙宽松显瘦显高</div>
              <div class="goods_item_footer">
                <span>￥89.9</span><span>1.1w<i class="el-icon-star-off"></i></span>
              </div>
            </div>
          </div>
        </el-col>
      </el-row>
    <el-row :gutter="298">
       <el-col :span="4">
        <div class="goods_item" @click="toDetail(11)">
          <img src="@/assets/imgs/goods11.webp" alt="">
          <div class="goods_item_desc">
            <div class="goods_item_title">夏季新款韩版小个子显瘦气质A字裙Polo领单排扣连衣裙短裙子</div>
            <div class="goods_item_footer">
              <span>￥99.5</span><span>1755<i class="el-icon-star-off"></i></span>
            </div>
          </div>
        </div>
      </el-col>
       <el-col :span="4">
        <div class="goods_item" @click="toDetail(12)">
          <img src="@/assets/imgs/goods12.webp" alt="">
          <div class="goods_item_desc">
            <div class="goods_item_title">小清新温柔甜美丝带蝴蝶结荷叶边露肩高腰雪纺碎花长裙连衣裙仙夏</div>
            <div class="goods_item_footer">
              <span>￥59.6</span><span>251<i class="el-icon-star-off"></i></span>
            </div>
          </div>
        </div>
      </el-col>
       <el-col :span="4">
        <div class="goods_item" @click="toDetail(13)">
          <img src="@/assets/imgs/goods13.webp" alt="">
          <div class="goods_item_desc">
            <div class="goods_item_title">港风衬衫女宽松露肩上衣收腰2021新款连衣裙蝴蝶结衬衫裙女夏</div>
            <div class="goods_item_footer">
              <span>￥83.6</span><span>443<i class="el-icon-star-off"></i></span>
            </div>
          </div>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: 'Goods',
  methods: {
    toDetail(id) {
      this.$router.push(`/home/detail/${id}`)
    }
  }
}
</script>

<style lang="scss" scoped>
.goods {
  padding: 0 15px;
  width: 100%;
  height: 100%;
  overflow: hidden;
  .goods_item {
    cursor: pointer;
    margin-bottom: 40px;
    width: 220px;
    height: 370px;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    background-color: #fff;
    img {
      width: 100%;
    }
  .goods_item_desc {
    padding: 0 5px;
    .goods_item_title {
      font-size: 12px;
      color: #666;
      line-height: 18px;
    }
    .goods_item_footer {
      padding-top: 3px;
      display: flex;
      justify-content: space-between;
      span {
        color: #ddd;
        &:first-child {
          color: rgb(255, 147, 163);
        }
      }
    }
  }
  }
}
</style>