<template>
  <div>
    <el-card class="contaner">
      <!-- 为 ECharts 准备一个具备大小（宽高）的 DOM -->
      <div id="main" style="width: 700px;height:400px;"></div>
      <div id="box" style="width: 500px;height:400px;"></div>
    </el-card>
  </div>
</template>

<script>
import * as echarts from 'echarts';
import _ from 'loadsh'
export default {
  data() {
    return {
      // 需要合并的选项
      options1: {
        title: {
          text: '用户来源'
        },
        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'cross',
            label: {
              backgroundColor: '#E9EEF3'
            }
          }
        },
        grid: {
          left: '3%',
          right: '4%',
          bottom: '3%',
          containLabel: true
        },
        xAxis: [
          {
            boundaryGap: false
          }
        ],
        yAxis: [
          {
            type: 'value'
          }
        ]
      },
      option2 : {
        title: {
            text: '地区资源占比',
            subtext: '2017-2018',
            left: 'center'
        },
        tooltip: {
            trigger: 'item',
            formatter: '{a} <br/>{b} : {c} ({d}%)'
        },
        legend: {
            left: 'center',
            top: 'bottom',
            data: ['rose1', 'rose2', 'rose3', 'rose4', 'rose5', 'rose6', 'rose7', 'rose8']
        },
        series: [
            {
                name: '百分比',
                type: 'pie',
                radius: [20, 140],
                center: ['50%', '50%'],
                roseType: 'area',
                itemStyle: {
                    borderRadius: 5
                },
                data: [
                    {value: 30, name: '中国'},
                    {value: 28, name: '美国'},
                    {value: 26, name: '日本'},
                    {value: 24, name: '德国'},
                    {value: 22, name: '法国'},
                    {value: 20, name: '印度'},
                    {value: 18, name: '俄罗斯'},
                    {value: 16, name: '韩国'}
                ]
            }
        ]
    }
    };
  },
  // 页面元素渲染完毕
  async mounted() {
    const data = {"legend":{"data":["华东","华南","华北","西部","其他"]},"yAxis":[{"type":"value"}],"xAxis":[{"data":["2017-12-27","2017-12-28","2017-12-29","2017-12-30","2017-12-31","2018-1-1"]}],"series":[{"name":"华东","type":"line","stack":"总量","areaStyle":{"normal":{}},"data":[2999,3111,4100,3565,3528,6000]},{"name":"华南","type":"line","stack":"总量","areaStyle":{"normal":{}},"data":[5090,2500,3400,6000,6400,7800]},{"name":"华北","type":"line","stack":"总量","areaStyle":{"normal":{}},"data":[6888,4000,8010,12321,13928,12984]},{"name":"西部","type":"line","stack":"总量","areaStyle":{"normal":{}},"data":[9991,4130,7777,12903,13098,14028]},{"name":"其他","type":"line","stack":"总量","areaStyle":{"normal":{}},"data":[15212,5800,10241,14821,15982,14091]}]}

    var myChart = echarts.init(document.getElementById("main"));
    var myChart2 = echarts.init(document.getElementById("box"));
     const reslut =  _.merge(data,this.options1)
    myChart.setOption(reslut);
    myChart2.setOption(this.option2)
  }
};
</script>

<style lang="scss" scoped>
.contaner {
  div {
    display: inline-block;
  }
}
</style>