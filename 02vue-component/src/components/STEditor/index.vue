<template>
  <div class="editorContainer" ref="editor"></div>
</template>

<script>
import E from 'wangeditor'
export default {
  name: 'STEditor',
  props: {
    value: {
      type: String
    }
  },
  methods: {
    initEditor(){
      const editor = new E(this.$refs.editor)
      editor.config.onchange = (newHtml) => {
        console.log('改变数据：', newHtml)
        this.$emit('input', newHtml)
      }
      editor.create()
      editor.txt.html(this.value)
      this.$watch('value', () => {
        editor.txt.html(this.value)
      })
    }
  },
  mounted(){
    console.log('原数据：', this.value)
    this.initEditor()
  }
}
</script>