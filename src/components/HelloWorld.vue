<template>
  <div class="hello">
    <div class="main" :style="{width: '65em', height: '40em',margin:'auto'}"></div>
    <div></div>
  </div>
</template>

<script>
// 引入 ECharts 主模块
// var echarts = require('echarts/lib/echarts');
var echarts = require('echarts');
// 引入柱状图
require('echarts/lib/chart/bar');
// 引入提示框和标题组件
require('echarts/lib/component/tooltip');
require('echarts/lib/component/title');
export default {
  name: "hello",
  data() {
    return {
      msg: "Welcome to Your Vue.js App"
    };
  },
  mounted(){
    this.echa();
  },
  methods: {
    echa(){
      var myChart = echarts.init(document.querySelector('.main'));  //这里获取要显示视图地方的id('main')
      myChart.setOption({
          title: {
              text: 'ECharts--柱形图'
          },
          tooltip: {},
          xAxis: {
              data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
          },
          yAxis: {},
          series: [{
              name: '销量',
              type: 'bar',
              data: [5, 20, 36, 10, 10, 20]
          }]
      });
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
