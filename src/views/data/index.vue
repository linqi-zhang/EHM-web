<template>
  <div style="margin: 20px">
    <el-table :data="tableData.filter(data => !search || data.name.toLowerCase().includes(search.toLowerCase()))"
      style="width: 100%">
      <el-table-column label="模型" prop="model">
      </el-table-column>
      <el-table-column label="数据集" prop="name">
      </el-table-column>
      <el-table-column label="描述" prop="description">
      </el-table-column>
      <el-table-column align="right">
        <template slot="header" slot-scope="scope">
          <el-input v-model="search" size="mini" placeholder="输入关键字搜索" />
        </template>
        <template slot-scope="scope">
          <el-button size="mini" @click="handleEdit(scope.$index, scope.row)">查看</el-button>
          <el-button size="mini" type="danger" @click="handleDelete(scope.$index, scope.row)">删除</el-button>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableData: [{
        model: 'Model_1',
        name: 'Normal.mat',
        description: '正常情况下的数据集'
      }, {
        model: 'Model_1',
        name: 'Fault_1.mat',
        description: '故障情况1（轴承内圈磨损）下的数据集'
      }, {
        model: 'Model_1',
        name: 'Fault_1.mat',
        description: '故障情况2（轴承滚子磨损）下的数据集'
      }, {
        model: 'Model_2',
        name: 'Normal.mat',
        description: '正常情况下的数据集'
      },],
      search: ''
    }
  },
  methods: {
    handleEdit(index, row) {
      console.log(index, row);
    },
    handleDelete(index, row) {
      console.log(index, row);
    }
  },
}
</script>