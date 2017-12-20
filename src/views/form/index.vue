<template>
  <div class="app-container">
    <el-form ref="form" :model="form" label-width="120px">
      <el-form-item label="SimID">
        <el-input v-model="form.simID"></el-input>
      </el-form-item>
      <!--el-form-item label="Activity zone">
        <el-select v-model="form.region" placeholder="please select your zone">
          <el-option label="Zone one" value="shanghai"></el-option>
          <el-option label="Zone two" value="beijing"></el-option>
        </el-select>
      </el-form-item-->
      <el-form-item label="ReplaySpeed">
        <el-input-number v-model="form.replaySpeed"></el-input-number>
      </el-form-item>
      <el-form-item label="MDEntryDate">
        <el-col :span="11">
          <el-date-picker type="date" placeholder="Pick a date" v-model="form.mDEntryDate" style="width: 100%;"></el-date-picker>
        </el-col>
        <el-col class="line" :span="2">-</el-col>
        <el-col :span="11">
          <el-time-picker type="fixed-time" placeholder="Pick a time" v-model="form.date2" style="width: 100%;"></el-time-picker>
        </el-col>
      </el-form-item>
      <el-form-item label="Start Paused">
        <el-switch v-model="form.startPaused"></el-switch>
      </el-form-item>
      <!--el-form-item label="Activity type">
        <el-checkbox-group v-model="form.type">
          <el-checkbox label="Online activities" name="type"></el-checkbox>
          <el-checkbox label="Promotion activities" name="type"></el-checkbox>
          <el-checkbox label="Offline activities" name="type"></el-checkbox>
          <el-checkbox label="Simple brand exposure" name="type"></el-checkbox>
        </el-checkbox-group>
      </el-form-item-->
      <el-form-item label="MatcherType">
        <el-radio-group v-model="form.matcherType">
          <el-radio label="Full"></el-radio>
          <el-radio label="Half"></el-radio>
        </el-radio-group>
      </el-form-item>
      <el-form-item label="Parameters">
        <el-input type="textarea" v-model="form.parameters"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="onSubmit">Create</el-button>
        <el-button @click="onCancel">Cancel</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        simID: '',
        replaySpeed: 1,
        mDEntryDate: '',
        date2: '',
        startPaused: false,
        type: [],
        matcherType: '',
        parameters: ''
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

