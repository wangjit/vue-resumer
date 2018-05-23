<template>
  <div>
    
    <button class="sap button" @click="saveAsImage">存为图片</button>
    <ResumePreview />
    <router-link class="back button" to="/" >back</router-link>
    
  </div>
</template>

<script>
import ResumePreview from './ResumePreview'
import FileSaver from 'file-saver'
export default {
  name: 'Preview',
  components: {
    ResumePreview
  },
  methods: {
    saveAsImage: function () {
      let resumePreview = document.querySelector('#resumePreview')
      html2canvas(resumePreview).then(function (canvas) {
        canvas.toBlob(function (blob) {
          FileSaver.saveAs(blob, 'Resume.png')
        })
      })
    }
  }
}
</script>
<style lang="scss">
.back {
  position: fixed;
  right: 0;
  top: 0;
}
</style>
