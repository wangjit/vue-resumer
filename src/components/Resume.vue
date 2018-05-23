<template>
  <div>
    <div class=page>
      <header>
        <Topbar/>
        
        <router-link class="button preview"  to="/preview" ><button type="button" class="btn btn-default"> preview</button></router-link>
      </header>
      <main>
        <ResumeEditor/>
        <ResumePreview/>
      </main>
    </div>
  </div>
</template>

<script>

import Topbar from './Topbar'
import ResumeEditor from './ResumeEditor'
import ResumePreview from './ResumePreview'

export default {
  name: 'Resume',
  components: { Topbar, ResumeEditor, ResumePreview },
  created() {
  }
}
</script>

<style lang="scss" scoped>
header {
  .preview {
    position: fixed;
    right: 50px;
    top: 108px;
  }
}
#resumeEditor {
  min-width: 35%;
  background: #444;
}

#resumePreview {
  flex-grow: 1;
  margin-left: 16px;
}
</style>
