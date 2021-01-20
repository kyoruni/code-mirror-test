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
import 'codemirror/mode/javascript/javascript.js'
// import theme style
import 'codemirror/theme/base16-dark.css'

export default {
  components: {
    codemirror
  },
  data () {
    return {
      code: 'const a = 10',
      cmOptions: {
        tabSize: 4,
        mode: 'text/javascript',
        theme: 'base16-dark',
        lineNumbers: true,
        line: true
      }
    }
  }
}
</script>
