<template>
  <div class="index">
    <div id="myCharts" class="charts">
        
    </div>
  </div>
</template>

<script>
export default {
  name: 'Index',
  data () {
    return {
      certainlyAmount:[],
      uncertainlyAmount:[],
      seriousAmount:[],
      deadAmount:[],
      cureAmount:[]
    }
  },
  mounted(){
    this.getCharts();
  },
  methods:{
    getCharts(){
       let myChart = this.$echarts.init(document.getElementById('myCharts'));
       let option = {
         title:{
              text:'新型冠状病毒肺炎相关数据统计(数据源于央视新闻微信公众号)',
              left:50,
              top:10,
              textStyle:{
                  //文字颜色
                  color:'#ccc',
                  //字体风格,'normal','italic','oblique'
                  fontStyle:'normal',
                  //字体粗细 'normal','bold','bolder','lighter',100 | 200 | 300 | 400...
                  fontWeight:'bold',
                  //字体系列
                  fontFamily:'sans-serif',
                  //字体大小
          　　　　 fontSize:18
              },
              subtext:'Author : Guitar Zou',
          },
          backgroundColor: "#05224d",
          tooltip: {},
          grid: {
              top: '8%',
              left: '1%',
              right: '1%',
              bottom: '8%',
              containLabel: true,
          },
          legend: {
              itemGap: 50,
              top:10,
              left:800,
              data: ['确诊病例' ,'疑似病例','重症病例','死亡','治愈（出院）'],
              textStyle: {
                  color: '#f9f9f9',
                  borderColor: '#fff'
              },
          },
          xAxis: [{
              type: 'category',
              boundaryGap: true,
              axisLine: { //坐标轴轴线相关设置。数学上的x轴
                  show: true,
                  lineStyle: {
                      color: '#f9f9f9'
                  },
              },
              axisLabel: { //坐标轴刻度标签的相关设置
                  textStyle: {
                      color: '#d1e6eb',
                      margin: 15,
                  },
              },
              axisTick: {
                  show: false,
              },
              data: ['1月24日', '1月25日', '1月26日', '1月27日', '1月28日', '1月29日', '1月30日','1月31日','2月1日','2月2日','2月3日','2月4日','2月5日','2月6日','2月7日']
          }],
          yAxis: [{
              type: 'value',
              min: 0,
              // max: 140,
              splitNumber: 7,
              splitLine: {
                  show: true,
                  lineStyle: {
                      color: '#0a3256'
                  }
              },
              axisLine: {
                  show: false,
              },
              axisLabel: {
                  margin: 20,
                  textStyle: {
                      color: '#d1e6eb',

                  },
              },
              axisTick: {
                  show: false,
              },
          }],
          series: [{
              name: '确诊病例',
              type: 'line',
              // smooth: true, //是否平滑曲线显示
              // 			symbol:'circle',  // 默认是空心圆（中间是白色的），改成实心圆
              label: {
                  show: true,
                  position: 'top',
                  textStyle: {
                      color: '#fff',
                  }
              },
              itemStyle: {
                   normal: {
                      color: "#000000",
                  }
              },
              tooltip: {
                  show: false
              },
              data: [1287,1975,2744,4515,5974,7711,9692,11791,14380,17205,20438,24324,28018,31161,31774]
          }, {
              name: '疑似病例',
              type: 'line',
              barWidth: 20,
              tooltip: {
                  show: false
              },
              label: {
                  show: true,
                  position: 'top',
                  textStyle: {
                      color: '#fff',
                  }
              },
              itemStyle: {
                 normal: {
                    color: "#cccccc",
                  }
              },
              data: [1965,2684,5794,6973,9239,12167,15238,17988,19544,21558,23214,23260,24702,26359,27657]
          },
          {
              name: '重症病例',
              type: 'bar',
              // smooth: true, //是否平滑曲线显示
              // 			symbol:'circle',  // 默认是空心圆（中间是白色的），改成实心圆
              label: {
                  show: true,
                  position: 'top',
                  textStyle: {
                      color: '#fff',
                  }
              },
              itemStyle: {
                  normal: {
                      color: "#660066",
                      barBorderRadius: [30, 30, 0, 0],
                      shadowColor: '#660066',
                      shadowBlur: 5,
                  }
              },
              tooltip: {
                  show: false
              },
              data: [237,324,461,976,1239,1370,1527,1795,2110,2296,2788,3219,3859,4821,6101]
          }, 
          {
              name: '死亡',
              type: 'bar',
              // smooth: true, //是否平滑曲线显示
              // 			symbol:'circle',  // 默认是空心圆（中间是白色的），改成实心圆
              label: {
                  show: true,
                  position: 'top',
                  textStyle: {
                      color: '#fff',
                  }
              },
              itemStyle: {
                   normal: {
                      color: "#990000",
                      barBorderRadius: [30, 30, 0, 0],
                      shadowColor: '#990000',
                      shadowBlur: 5,
                  }
              },
              tooltip: {
                  show: false
              },
              data: [41,56,80,106,132,170,213,259,304,361,425,490,563,636,722]
          }, 
          {
              name: '治愈（出院）',
              type: 'bar',
              // smooth: true, //是否平滑曲线显示
              // 			symbol:'circle',  // 默认是空心圆（中间是白色的），改成实心圆
              label: {
                  show: true,
                  position: 'top',
                  textStyle: {
                      color: '#fff',
                  }
              },
              itemStyle: {
                   normal: {
                      color: "#009999",
                      barBorderRadius: [30, 30, 0, 0],
                      shadowColor: '#009999',
                      shadowBlur: 5,
                  }
              },
              tooltip: {
                  show: false
              },
              data: [38,49,51,60,103,124,171,243,328,475,632,892,1153,1540,2050]
          }, ]
      };
      myChart.setOption(option);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#myCharts{
  width: 100%;
  height: 800px;
}
</style>
