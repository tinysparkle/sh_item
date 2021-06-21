<template>
  <div class="shopping_page">
     <el-table
      @selection-change="handleSelectionChange"
      :data="tableData"
      style="width: 100%">
      <el-table-column
        label="全选"
        width="180"
        type="selection">
      </el-table-column>
      <el-table-column
        prop="goodsInfo"
        label="商品信息"
        width="300">
      </el-table-column>
      <el-table-column
        prop="price"
        label="单价">
      </el-table-column>
      <el-table-column
        prop="count"
        label="数量">
        <template slot-scope="scope">
          <el-input-number v-model="scope.row.count"  :min="1" :max="10"></el-input-number>
        </template>
      </el-table-column>
      <el-table-column
        label="操作">
        <template slot-scope="scope">
          <el-button type="danger" plain @click="deleBtn(scope.row.id)">删除</el-button>
        </template>
      </el-table-column>
    </el-table>
    <el-row type="flex" justify="end" style="marginTop: 20px">
      <el-col :span="4">
        <el-button type="primary" :disabled="!multipleSelection.length" @click="toDeal">去付款</el-button>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name:'Shopping',
  data() {
    return {
      tableData: [
        {
          id: 1,
          goodsInfo: '2021新款高腰中长款大码大摆裙子女夏系带褶皱胖MM连衣裙潮',
          color: '白色',
          size: 'S',
          price: '89.9',
          count: 1
        },
        {
          id: 2,
          goodsInfo: '大码春季新款裙子仙女超仙森系学生气质女神范连衣裙宽松显瘦显高',
          color: '白色',
          size: 'M',
          price: '102.8',
          count: 2
        },
        {
          id: 3,
          goodsInfo: '夏季新款韩版小个子显瘦气质A字裙Polo领单排扣连衣裙短裙子',
          color: '白色',
          size: 'L',
          price: '83.6',
          count: 1
        },
        {
          id: 4,
          goodsInfo: '小清新温柔甜美丝带蝴蝶结荷叶边露肩高腰雪纺碎花长裙连衣裙仙夏',
          color: '白色',
          size: 'S',
          price: '59.6',
          count: 3
        },
        {
          id: 5,
          goodsInfo: '港风衬衫女宽松露肩上衣收腰2021新款连衣裙蝴蝶结衬衫裙女夏',
          color: '白色',
          size: 'XL',
          price: '99.5',
          count: 1
        },
        
      ],
      multipleSelection: []
    }
  },
  methods: {
    deleBtn(id) {
      for(let i in this.tableData) {
        if(this.tableData[i].id == id) {
          this.tableData.splice(i, 1)
        }
      }
    },
    handleSelectionChange(val) {
      this.multipleSelection = val;
    },
    toDeal() {
       window.location.href = 'https://www.alipay.com/';
    }
  }
}
</script>

<style lang="scss" scoped>
.shopping_page {
  width: 100%;
  height: 100%;
  .el-table {
    width: 80% !important;
    margin: 0 auto;
    /deep/ .el-input-number {
      width: 120px;
    }
  }
}
</style>