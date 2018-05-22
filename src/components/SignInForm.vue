<template>
  <div>
    <form @submit.prevent="signIn">
      <div class="form-group">
        <label for="username1">用户名</label>
        <input class="form-control" id="username1" type="text" required v-model="formData.username">
      </div>
      <div class="form-group">
        <label for="password1">密　码</label>
        <input class="form-control" id="password1" type="password" required v-model="formData.password">
      </div>
        <input class="btn btn-default" type="submit" value="提交">
        <span>{{errorMessage}}</span>
    </form>
  </div>
</template>

<script>

import AV from '../lib/leancloud'
import getErrorMessage from '../lib/getErrorMessage'
import getAVUser from '../lib/getAVUser'

export default {
  name: 'SignInForm',
  data(){
    return {
      formData: {
        username: '',
        password: ''
      },
      errorMessage: ''
    }
  },
  methods: {
    signIn(){
      let {username, password} = this.formData
      AV.User.logIn(username,password).then(()=> {
        this.$emit('success', getAVUser())
      }, (error)=> {
        this.errorMessage = getErrorMessage(error)
      });
    }
  }
}
</script>
<style scoped lang="scss">

</style>
