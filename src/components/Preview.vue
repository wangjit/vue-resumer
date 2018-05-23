<template>
  <div>
    
    <button type="button" class="sap btn btn-default" @click="saveAsImage">存为图片</button>
    <ResumePreview />
    <router-link class="back" to="/" ><button type="button" class="btn btn-default">back</button></router-link>
    
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
