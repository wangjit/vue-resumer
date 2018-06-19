<template>
  <div class="dialogWrapper" v-show="visible">
    <div class="dialog">
      <header>{{title}}
        <span class="close" @click="close">❌</span>
      </header>
      <main>
        <slot></slot>
      </main>
    </div>
  </div>

</template>

<script>
  export default {
    name: 'MyDialog',
    props: ['title', 'visible'],
    methods: {
      close(){
        this.$emit('close')
      }
    }
  }
</script>

<style scoped lang="scss">
  .dialogWrapper{
    position: fixed;
    background: hsla(0, 0%,0%,0.25);
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    margin: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    z-index: 1;
    span {
      cursor: pointer;
    }
    header {
      border-top-left-radius: 5px;
      border-top-right-radius: 5px;
      color: white;
      background-color: #3a3d44;
    }
  }
  .dialog{
    box-shadow: 0 0 15px rgba(0,0,0,.5);
    border-radius: 5px;
    background: white;
    min-height: 4em;
    min-width: 10em;
    > header{
      padding: 16px;
      display: flex;
      justify-content: space-between;
    }
    > main{
      padding: 16px;
    }
  }
</style>
