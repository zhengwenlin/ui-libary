<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="120px">
      <el-form-item label="输入框">
        <el-input v-model="form.name" />
      </el-form-item>
      <el-form-item label="下拉框">
        <el-select v-model="form.region" placeholder="请选择">
          <el-option label="Zone one" value="shanghai" />
          <el-option label="Zone two" value="beijing" />
        </el-select>
      </el-form-item>
      <el-form-item label="时间选择">
        <el-col :span="11">
          <el-date-picker v-model="form.date1" type="date" placeholder="请选择日期" style="width: 100%;" />
        </el-col>
        <el-col :span="2" class="line">-</el-col>
        <el-col :span="11">
          <el-time-picker v-model="form.date2" type="fixed-time" placeholder="请选择时间" style="width: 100%;" />
        </el-col>
      </el-form-item>
      <el-form-item label="开关">
        <el-switch v-model="form.delivery" />
      </el-form-item>
      <el-form-item label="复选框">
        <el-checkbox-group v-model="form.type">
          <el-checkbox label="选项一" name="type" />
          <el-checkbox label="选项二" name="type" />
          <el-checkbox label="选项三" name="type" />
          <el-checkbox label="选项四" name="type" />
        </el-checkbox-group>
      </el-form-item>
      <el-form-item label="单选框">
        <el-radio-group v-model="form.resource">
          <el-radio label="A" />
          <el-radio label="B" />
        </el-radio-group>
      </el-form-item>
      <el-form-item label="文本域">
        <el-input v-model="form.desc" type="textarea" />
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">提交</el-button>
        <el-button @click="onCancel">取消</el-button>
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
      this.$message('submit!')
    },
    onCancel() {
      this.$message({
        message: 'cancel!',
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

