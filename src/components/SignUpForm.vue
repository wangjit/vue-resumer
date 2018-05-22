<template>
  <div>
    <form @submit.prevent="signUp">
      <div class="form-group">
        <label for="username">用户名</label> 
        <input  class="form-control" id="username" type="text" v-model="formData.username" required>
      </div>
      <div class="form-group">
        <label for="password">密　码</label>
        <input  class="form-control" id="password" type="password" v-model="formData.password" required>
      </div>
        <input class="btn btn-default" type="submit" value="提交">
        <span class="errorMessage">{{errorMessage}}</span>
    </form>
  </div>
</template>

<script>

import AV from '../lib/leancloud'
import getErrorMessage from '../lib/getErrorMessage'
import getAVUser from '../lib/getAVUser'

export default {
  name:'SignUpForm',
  data(){
    return {
      formData: {
        username: '',
        password: ''
      },
      errorMessage: ''
    }
  },
  created(){
  },
  methods:{
    signUp(){
      let {username, password} = this.formData
      var user = new AV.User();
      user.setUsername(username);
      user.setPassword(password);
      user.signUp().then(() =>{
        this.$emit('success', getAVUser())
      }, (error)=> {
        this.errorMessage = getErrorMessage(error)
      });
    }
  }
}
</script>
