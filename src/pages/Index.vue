<template>
  <q-page class="flex flex-center">
    {{ version }}
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import { ipcRenderer } from 'electron'

export default defineComponent({
  name: 'PageIndex',
  data () {
    return {
      version: ''
    }
  }
  // mounted: function () {
  //   ipcRenderer.send('app_version')

  //   ipcRenderer.on('app_version', (event, arg) => {
  //     ipcRenderer.removeAllListeners('app_version')
  //     this.version = 'Version ' + arg.version
  //   })
  // }
})
</script>
