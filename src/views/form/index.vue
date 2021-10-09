<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="120px">
      <el-form-item label="表格名称">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="地区">
        <el-select v-model="form.region" placeholder="请选择地区">
          <el-option label="上海" value="shanghai" />
          <el-option label="北京" value="beijing" />
        </el-select>
      </el-form-item>
      <el-form-item label="表格时间">
        <el-col :span="11">
          <el-date-picker v-model="form.date1" type="date" placeholder="开始时间" style="width: 100%;" />
        </el-col>
        <el-col :span="2" class="line">-</el-col>
        <el-col :span="11">
          <el-time-picker v-model="form.date2" type="fixed-time" placeholder="结束时间" style="width: 100%;" />
        </el-col>
      </el-form-item>
      <el-form-item label="开关">
        <el-switch v-model="form.delivery" />
      </el-form-item>
      <el-form-item label="复选框">
        <el-checkbox-group v-model="form.type">
          <el-checkbox label="吃饭" name="type" />
          <el-checkbox label="睡觉" name="type" />
          <el-checkbox label="唱歌" name="type" />
          <el-checkbox label="跳舞" name="type" />
        </el-checkbox-group>
      </el-form-item>
      <el-form-item label="性别">
        <el-radio-group v-model="form.resource">
          <el-radio label="男" />
          <el-radio label="女" />
        </el-radio-group>
      </el-form-item>
      <el-form-item label="自我描述">
        <el-input v-model="form.desc" type="textarea" />
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">保存</el-button>
        <el-button @click="onCancel">放弃</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      }
    }
  },
  methods: {
    onSubmit() {
      this.$message('保存成功！')
    },
    onCancel() {
      this.$message({
        message: '您取消了保存',
        type: 'warning'
      })
    }
  }
}
</script>

<style scoped>
.line{
  text-align: center;
}
</style>

