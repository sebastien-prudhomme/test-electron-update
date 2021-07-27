<template>
  <q-page class="flex flex-center">
    {{ version }}
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'PageIndex',
  data () {
    return {
      version: ''
    }
  },
  mounted: function () {
    window.ipcRenderer.send('app_version')

    window.ipcRenderer.on('app_version', (event, arg) => {
      window.ipcRenderer.removeAllListeners('app_version')
      this.version = 'Version ' + arg.version
    })
  }
})
</script>
