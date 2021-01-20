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

export default {
  components: {
    codemirror
  },
  data () {
    return {
      code: '<div>ほげ</div>',
      cmOptions: {
        tabSize: 4,
        indentUnit: 4,
        indentWithTabs: true, // インデントするとき、スペースをtabに置き換える
        mode: 'text/html',
        theme: 'default',
        lineNumbers: true,
        line: true,
        dragDrop: false // ドラッグ&ドロップでファイル追加できないようにする
      }
    }
  }
}
</script>
