<template>
  <div>
    <RichTextEditorVue />
  </div>
</template>

<script>
import RichTextEditorVue from './components/RichTextEditor.vue';
export default {
  name: 'App',
  components: {
    RichTextEditorVue,
  }
}
</script>

<style>
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
