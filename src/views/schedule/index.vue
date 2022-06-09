<template>
  <div class="chart-container">
    <el-row>
      <el-col :span="24">
        <!-- <div id="schedule"></div> -->
        <div id="schedule" v-on-echart-resize style="width:100%; height:88vh;"></div>
      </el-col>
    </el-row>
  </div>
</template>
 
<script>
import echarts from 'echarts'
import elementResizeDetectorMaker from "element-resize-detector";
import "@/utils/chart.resize";


export default {
  data() {
    return {
      schedule: null
    }
  },
  methods: {
    drawSchedule() {
      this.schedule = echarts.init(document.getElementById('schedule'));
      const option = {
        backgroundColor: "#fff",
        title: {
          text: "2022年4月检修计划",
          padding: 20,
          textStyle: {
            fontSize: 18,
            fontWeight: "bolder",
            color: "#333"
          },
          subtextStyle: {
            fontSize: 13,
            fontWeight: "bolder"
          }
        },
        legend: {
          data: ["年修", "定修"],
          align: "right",
          right: 50,
          top: 50
        },
        grid: {
          containLabel: true,
          show: false,
          right: 50,
          left: 40,
          bottom: 40,
          top: 90
        },
        xAxis: {
          type: 'time',
          min: new Date("2022-04-01 08:00:00"),
          max: new Date("2022-05-01 08:00:00"),
          interval: 24 * 60 * 60 * 1000,
          axisLabel: {
            show: 'true',
            interval: 0
          }
        },
        yAxis: {
          splitLine: {
            show: true
          },
          axisLabel: {
            show: true,
            interval: 0,
            formatter: function (value, index) {
              var last = ""
              var max = 5;
              var len = value.length;
              var hang = Math.ceil(len / max);
              if (hang > 1) {
                for (var i = 0; i < hang; i++) {
                  var start = i * max;
                  var end = start + max;
                  var temp = value.substring(start, end) + "\n";
                  last += temp; //凭借最终的字符串
                }
                return last;
              } else {
                return value;
              }
            }
          },
          data: ["设备A", "设备B", "设备C", "设备D", "设备E", "设备F", "设备G", "设备H", "设备I"]
        },
        tooltip: {
          trigger: "axis",
          formatter: function (params) {
            var res = "";
            var name = "";
            var start = "";
            var end = "";
            for (var i in params) {
              if (params[i].data != null) {
                var k = i % 2;
                if (!k) { //偶数
                  start = params[i].data.toLocaleString();
                }
                if (k) { //奇数         
                  name = params[i].seriesName;
                  end = params[i].data.toLocaleString();
                  res += name + " : " + end + "~" + start + "</br>";
                }
              }
            }
            return res;
          }
        },
        series: [{
          name: "年修",
          type: "bar",
          stack: "总量0",
          label: {
            normal: {
              show: true,
              color: "#000",
              position: "right",
              formatter: function (params) {
                return params.seriesName
              }
            }
          },
          itemStyle: {
            normal: {
              color: "skyblue",
              borderColor: "#fff",
              borderWidth: 2
            }
          },
          zlevel: -1,
          // 各设备年修结束时间
          data: [
            null,
            new Date("2022-04-15 18:00:00"),
            null,
            null,
            null,
            new Date("2022-04-10 18:00:00"),
            null,
            null,
            null]
        },
        {
          name: "年修",
          type: "bar",
          stack: "总量0",
          itemStyle: {
            normal: {
              color: "white",
            }
          },
          zlevel: -1,
          z: 3,
          // 各设备年修开始时间
          data: [
            null,
            new Date("2022-04-10 08:00:00"),
            null,
            null,
            null,
            new Date("2022-04-05 08:00:00"),
            null,
            null,
            null]
        },
        {
          name: "定修",
          type: "bar",
          stack: "总量2",
          label: {
            normal: {
              show: true,
              color: "#000",
              position: "right",
              formatter: function (params) {
                return params.seriesName
              }
            }
          },
          itemStyle: {
            normal: {
              color: "green",
              borderColor: "#fff",
              borderWidth: 2
            }
          },
          zlevel: -1,
          // 各设备定修结束时间
          data: [
            new Date("2022-04-05 18:00:00"),
            null,
            null,
            new Date("2022-04-09 12:00:00"),
            null,
            null,
            new Date("2022-04-22 18:00:00"),
            null,
            new Date("2022-04-30 18:00:00")]
        },
        {
          name: "定修",
          type: "bar",
          stack: "总量2",
          itemStyle: {
            normal: {
              color: "white",
            }
          },
          zlevel: -1,
          z: 3,
          // 各设备定修开始时间
          data: [
            new Date("2022-04-05 08:00:00"),
            null,
            null,
            new Date("2022-04-08 08:00:00"),
            null,
            null,
            new Date("2022-04-20 14:00:00"),
            null,
            new Date("2022-04-27 08:00:00")]
        }]
      };
      this.schedule.setOption(option);
    }
  },
    mounted() {
    let erd = elementResizeDetectorMaker();
    let that = this;
    erd.listenTo(document.getElementById("schedule"), (element) => {
      let width = element.offsetWidth;
      let height = element.offsetHeight;
      that.$nextTick(() => {
        //使echarts尺寸重置
        echarts.init(document.getElementById("schedule")).resize();
      });
    });
    this.drawSchedule()
  },
  updated: function () {
    this.drawSchedule()
  }
}
</script>
 
<style scoped>
.chart-container {
  background-color: white;
  height: 100%;
  width: 100%;
}

.el-col {
  padding: 5px;
}
</style>