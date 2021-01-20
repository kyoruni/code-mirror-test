<template>
  <div class="code-mirror">
    <codemirror
      v-model="code"
      :options="cmOptions"
    />
  </div>
</template>

<script>
import { codemirror } from 'vue-codemirror'
import 'codemirror/lib/codemirror.css'
// import language js
import 'codemirror/mode/htmlmixed/htmlmixed.js'
// import theme style
import 'codemirror/theme/base16-light.css'

export default {
  components: {
    codemirror
  },
  data () {
    return {
      code: '<div>ほげ</div>',
      cmOptions: {
        tabSize: 4,
        mode: 'text/html',
        theme: 'base16-light',
        lineNumbers: true,
        line: true
      }
    }
  }
}
</script>
