<template>
  <div id="app" style="max-width: 500px; margin: 40px auto;">
    <el-form :model="form" label-width="120px">
      <el-form-item label="Full Name">
        <el-input v-model="form.name"></el-input>
      </el-form-item>
      <el-form-item label="Email">
        <el-input v-model="form.email"></el-input>
      </el-form-item>
      <el-form-item label="Phone">
        <el-input v-model="form.phone"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="submitForm">Create Resume</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      form: {
        name: '',
        email: '',
        phone: ''
      }
    }
  },
  methods: {
    submitForm() {
      this.$message.success('Resume created! (This is a placeholder)');
    }
  }
}
</script>
