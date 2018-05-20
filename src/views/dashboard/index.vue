<template>
  <div class="dashboard-container">
      <el-row :gutter="15" class="flex">
  <el-col :span="4" style="width: 25%;">
    <!-- 要把 class 放在el-card 上面-->
    <el-card shadow="always" class="card">
      data1
    </el-card>
  </el-col>
    <el-col :span="4" style="width: 25%;">
    <el-card shadow="always" class="card">
      data2
    </el-card>
  </el-col>
    <el-col :span="4" style="width: 25%;">
    <el-card shadow="always" class="card">
      data3
    </el-card>
  </el-col>
    <el-col :span="4" style="width: 25%;">
    <el-card shadow="always" class="card">
      data4
    </el-card>
  </el-col>
    <el-col :span="4" style="width: 25%;">
    <el-card shadow="always" class="card">
      data5
    </el-card>
  </el-col>
</el-row>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
export default {
  name: 'dashboard',
  data() {
    return {
      currentRole: 'adminDashboard'
    }
  },
  computed: {
    ...mapGetters([
      'roles'
    ])
  },
  created() {
    if (!this.roles.includes('admin')) {
      this.currentRole = 'editorDashboard'
    }
  }
}
</script>

<style scoped>
   .dashboard-container{
     padding: .5rem;
     text-align: center;
   }
   .card{
     height: 180px;
   }
   .flex{
     display: flex;
     align-items:center;
   }
</style>
