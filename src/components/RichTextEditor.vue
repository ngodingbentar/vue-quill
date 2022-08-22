<template>
  <div>
    <QuillEditor v-model:content="content" contentType="html" theme="snow" toolbar="full" />
    <div>
      <button @click="saveData">save</button>
    </div>
    <div>
      <div v-for="item in data" :key="item.id">
        <h3>{{item.title}}</h3>
        <div v-html="item.body"></div>
      </div>
    </div>
  </div>
</template>
<script>
import { QuillEditor } from '@vueup/vue-quill'
import '@vueup/vue-quill/dist/vue-quill.snow.css';
import '@vueup/vue-quill/dist/vue-quill.bubble.css';

export default {
  components: {
    QuillEditor
  },
  data() {
    return {
      content: 'Test',
      data: [
        {
          id: 1,
          title: 'title 1',
          body: 'body 1'
        },
        {
          id: 2,
          title: 'title 2',
          body: 'body 2'
        }
      ]
    }
  },
  methods: {
    saveData() {
      this.data.push({
        id: this.data.length + 1,
        title: 'Title ' + this.data.length,
        body: this.content
      })
    }
  }
}
</script>
