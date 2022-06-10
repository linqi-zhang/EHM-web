<template>
  <div class="chart-container">
    <div id="status_1_F_C" v-on-echart-resize style="width:100%; height:20vh;"></div>
  </div>
</template>
<script>
import echarts from 'echarts'
import elementResizeDetectorMaker from "element-resize-detector";
import "@/utils/chart.resize";


export default {
  data() {
    return {
      status: null,
      data: [[0, 0]]
    }
  },
  methods: {
    drawStatus() {
      this.status = echarts.init(document.getElementById('status_1_F_C'));
      const option = {
        title: {
          left: 'center',
          text: 'C通道时域图',
          padding: [35, 5, 1, 5],
          textStyle: {
            fontSize: 13,
            fontWeight: "bolder",
            color: "#333"
          }
        },
        xAxis: {
          name: '样本序列点',
          nameLocation: 'middle',
          nameTextStyle: {
            fontSize: 12,
            padding: 5
          },
          axisLabel: {
            fontSize: 8
          },
          type: 'value',
        },
        yAxis: {
          name: '频率/Hz',
          nameLocation: 'middle',
          nameTextStyle: {
            fontSize: 12,
            padding: 10
          },
          axisLabel: {
            fontSize: 8
          },
          max: 0.6,
          min: -0.6,
          type: 'value'
        },
        series: [
          {
            data: this.data,
            type: 'line',
            smooth: true,
            symbol: 'none',
            lineStyle: {
              color: 'blue',
              width: 0.3
            }
          }
        ]
      };
      this.status.setOption(option);
    }
  },
  mounted() {
    let erd = elementResizeDetectorMaker();
    let that = this;
    erd.listenTo(document.getElementById("status_1_F_C"), (element) => {
      let width = element.offsetWidth;
      let height = element.offsetHeight;
      that.$nextTick(() => {
        //使echarts尺寸重置
        echarts.init(document.getElementById("status_1_F_C")).resize();
      });
    });
    this.drawStatus()
  },
  updated: function () {
    this.drawStatus()
  },
  created() {
    for (let i = 1; i < 1000; i++) {
      this.data.push([i, (Math.random() - 0.5)]);
    }
  }
}
</script>
 
<style scoped>
.chart-container {
  background-color: white;
  height: 100%;
  width: 100%;
}
</style>