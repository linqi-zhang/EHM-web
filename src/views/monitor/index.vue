<template>
  <div style="margin:20px">
    <el-row :gutter="20">
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备1</span>
            <el-button style="float: right; padding: 3px 0" type="text">删除</el-button>
          </div>
          <div v-for="o in 4" :key="o" class="text item">
            {{ username }}
          </div>
        </el-card>
      </el-col>
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备2</span>
            <el-button style="float: right; padding: 3px 0" type="text">删除</el-button>
          </div>
          <div v-for="o in 4" :key="o" class="text item">
            {{ username }}
          </div>
        </el-card>
      </el-col>
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备3</span>
            <el-button style="float: right; padding: 3px 0" type="text">删除</el-button>
          </div>
          <div v-for="o in 4" :key="o" class="text item">
            {{ username }}
          </div>
        </el-card>
      </el-col>
    </el-row>
    <el-row :gutter="20">
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备4</span>
            <el-button style="float: right; padding: 3px 0" type="text">删除</el-button>
          </div>
          <div v-for="o in 4" :key="o" class="text item">
            {{ username }}
          </div>
        </el-card>
      </el-col>
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备5</span>
            <el-button style="float: right; padding: 3px 0" type="text">删除</el-button>
          </div>
          <div v-for="o in 4" :key="o" class="text item">
            {{ username }}
          </div>
        </el-card>
      </el-col>
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备6</span>
            <el-button style="float: right; padding: 3px 0" type="text">删除</el-button>
          </div>
          <div v-for="o in 4" :key="o" class="text item">
            {{ username }}
          </div>
        </el-card>
      </el-col>
    </el-row>
    <el-row :gutter="20">
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备7</span>
            <el-button style="float: right; padding: 3px 0" type="text">删除</el-button>
          </div>
          <div v-for="o in 4" :key="o" class="text item">
            {{ username }}
          </div>
        </el-card>
      </el-col>
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备8</span>
            <el-button style="float: right; padding: 3px 0" type="text">删除</el-button>
          </div>
          <div v-for="o in 4" :key="o" class="text item">
            {{ username }}
          </div>
        </el-card>
      </el-col>
      <el-col :span="8">
        <el-card class="box-card">
          <div slot="header" class="clearfix">
            <span>设备9</span>
            <el-button style="float: right; padding: 3px 0" type="text">删除</el-button>
          </div>
          <div v-for="o in 4" :key="o" class="text item">
            {{ username }}
          </div>
        </el-card>
      </el-col>
    </el-row>
  </div>
</template>

<script>
export default {
  name: "showinfo",
  data() {
    return {
      username: "admin",
    }
  }
}
</script>
<style>
.el-row {
  margin-top: 20px;
  margin-bottom: 20px;
/* 
  &:last-child {
    margin-bottom: 0;
  } */
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
  padding: 10px 0;
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