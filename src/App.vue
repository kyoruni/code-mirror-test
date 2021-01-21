<template>
  <div id="app">
    <h1>テスト</h1>
    <CodeMirror/>
  </div>
</template>

<script>
import CodeMirror from '@/components/CodeMirror'

export default {
  name: 'App',
  components: {
    CodeMirror
  }
}
</script>

<style scoped>
h1 {
  color: #666;
  font-size: 1rem;
}
</style>
