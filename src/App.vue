<template>
  <div id="app">
    <textarea :value="input" @input="update"></textarea>
    <div v-html="compiledMarkdown"></div>
  </div>
</template>

<script>
import _ from 'lodash';
import marked from 'marked';

export default {
  name: 'app',
  data() {
    return {
      input: '# hello'
    }
  },
  computed: {
    //chuyen các ký tự đạt biết về -
    compiledMarkdown () {
      return marked(this.input, { sanitize: true })
    }
  },
  methods: {
    //set deplay test view
    update: _.debounce(function (e) {
      this.input = e.target.value
    }, 1000)
  }
}
</script>

<style>
  html, body, #map {
    margin: 0;
    height: 100%;
    font-family: 'Helvetica Neue', Arial, sans-serif;
    color: #333;
  }

  textarea, #map div {
    display: inline-block;
    width: 49%;
    height: 100%;
    vertical-align: top;
    box-sizing: border-box;
    padding: 0 20px;
  }

  textarea {
    border: none;
    border-right: 1px solid #ccc;
    resize: none;
    outline: none;
    background-color: #f6f6f6;
    font-size: 14px;
    font-family: 'Monaco', courier, monospace;
    padding: 20px;
  }

  code {
    color: #f66;
  }
</style>
