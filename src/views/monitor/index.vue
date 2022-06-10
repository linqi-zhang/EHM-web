<template>
  <div style="margin:20px">
    <!-- gutter属性设置分栏间隔 -->
    <el-row :gutter="20">
      <el-col :span="12">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备1-主轴电机-前轴承</span>
            <el-button style="float: right; padding: 3px 0" type="text">智能诊断</el-button>
          </div>
          <status_1_F_A></status_1_F_A>
          <status_1_F_B></status_1_F_B>
          <status_1_F_C></status_1_F_C>
        </el-card>
      </el-col>
      <el-col :span="12">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备1-主轴电机-后轴承</span>
            <el-button style="float: right; padding: 3px 0" type="text">智能诊断</el-button>
          </div>
          <status_1_E_A></status_1_E_A>
          <status_1_E_B></status_1_E_B>
          <status_1_E_C></status_1_E_C>
        </el-card>
      </el-col>
    </el-row>
    <el-row :gutter="20">
      <el-col :span="12">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备2-主轴电机-前轴承</span>
            <el-button style="float: right; padding: 3px 0" type="text">智能诊断</el-button>
          </div>
          <status_2_F_A></status_2_F_A>
          <status_2_F_B></status_2_F_B>
          <status_2_F_C></status_2_F_C>
        </el-card>
      </el-col>
      <el-col :span="12">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备2-主轴电机-后轴承</span>
            <el-button style="float: right; padding: 3px 0" type="text">智能诊断</el-button>
          </div>
          <status_2_E_A></status_2_E_A>
          <status_2_E_B></status_2_E_B>
          <status_2_E_C></status_2_E_C>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import status_1_F_A from './status_1_F_A.vue'
import status_1_F_B from './status_1_F_B.vue'
import status_1_F_C from './status_1_F_C.vue'
import status_1_E_A from './status_1_E_A.vue'
import status_1_E_B from './status_1_E_B.vue'
import status_1_E_C from './status_1_E_C.vue'
import status_2_F_A from './status_2_F_A.vue'
import status_2_F_B from './status_2_F_B.vue'
import status_2_F_C from './status_2_F_C.vue'
import status_2_E_A from './status_2_E_A.vue'
import status_2_E_B from './status_2_E_B.vue'
import status_2_E_C from './status_2_E_C.vue'
export default {
  name: "showinfo",
  data() {
    return {
      username: "admin",
    };
  },
  components: {
    status_1_F_A,
    status_1_F_B,
    status_1_F_C,
    status_1_E_A,
    status_1_E_B,
    status_1_E_C,
    status_2_F_A,
    status_2_F_B,
    status_2_F_C,
    status_2_E_A,
    status_2_E_B,
    status_2_E_C,
  }
}
</script>
<style>
.el-row {
  margin-top: 20px;
  margin-bottom: 20px;
}

.el-col {
  border-radius: 4px;
}

.bg-purple-dark {
  background: #99a9bf;
}

.bg-purple {
  background: #d3dce6;
}

.bg-purple-light {
  background: #e5e9f2;
}

.grid-content {
  border-radius: 4px;
  min-height: 36px;
}

.row-bg {
  padding: 5px 0;
  background-color: #f9fafc;
}

.text {
  font-size: 14px;
}

.item {
  margin-bottom: 18px;
}

.clearfix:before,
.clearfix:after {
  display: table;
  content: "";
}

.clearfix:after {
  clear: both
}

/* .box-card {
    width: 480px;
  } */
</style>

