<template>
  <div class="about">
    <i class="layui-icon layui-icon-face-smile" style="font-size: 30px; color: #1E9FFF;"></i>
    <i class="layui-icon layui-icon-login-weibo" style="font-size: 30px; color: #FCBA1F;"></i>

    <div>
      <div id="main" style="width: 60em;height:40em;margin: auto;"></div>
    </div>
  </div>
</template>
<script>
// 引入 echarts 主模块
var echarts = require('echarts');
// 引入饼图
// require("./lib/chart/pie");
require('echarts/lib/chart/pie');
// 引入提示框和标题组件
require('echarts/lib/component/tooltip');
require('echarts/lib/component/title');
export default {
  data() {
    return {};
  },
  mounted() {
    this.ecm();
  },
  methods: {
    ecm(){
      echarts.init(document.getElementById('main')).setOption({
        title: {
              text: 'ECharts--饼图'
          },
          tooltip: {},
            series: {
                type: 'pie',
                data: [
                    {name: 'A', value: 1212},
                    {name: 'B', value: 2323},
                    {name: 'C', value: 1919}
                ]
            }
        });
    }
  }
};
</script>