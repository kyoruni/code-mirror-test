<template>
  <div class="code-mirror">
    <codemirror
      v-model="code"
      :options="cmOptions"
      :closetag="true"
    />
    <h2>プレビュー</h2>
    <div class="preview">
      <div v-html="code"></div>
    </div>
  </div>
</template>

<script>
import { codemirror } from 'vue-codemirror'
import 'codemirror/lib/codemirror.css'
// import language js
import 'codemirror/mode/htmlmixed/htmlmixed.js'

// import addon
import 'codemirror/addon/edit/closetag.js'
import 'codemirror/addon/lint/lint.css'
import 'codemirror/addon/lint/lint.js'
import 'codemirror/addon/lint/html-lint.js'

export default {
  components: {
    codemirror
  },
  data () {
    return {
      // code: '<div>ほげ</div>',
      code: '<!-- コメント -->\n<div class="hoge">\n\tほげ\n</div>\n<ul style="padding: 10px;">\n\t<li>あいう</li>\n\t<li>かきく</li>\n\t<li>さしす</li>\n\t<li>たちつ</li>\n</ul>',
      cmOptions: {
        tabSize: 4,
        indentUnit: 4,
        indentWithTabs: true, // インデントするとき、スペースをtabに置き換える
        mode: 'htmlmixed',
        theme: 'default',
        lineNumbers: true,
        lint: true,
        gutters: [
          'CodeMirror-lint-markers',
          'CodeMirror-linenumbers',
          'CodeMirror-foldgutter'
        ],
        foldGutter: true,
        line: true,
        dragDrop: false, // ドラッグ&ドロップでファイル追加できないようにする
        autoCloseTags: true // addon: closetag を有効にする
      }
    }
  }
}
</script>

<style scoped>
.preview {
  background: #fcfcfc;
  border: 1px solid #666;
  padding: 20px;
  margin-bottom: 10px;
}

h2 {
  color: #666;
  font-size: 0.9rem;
}
</style>
