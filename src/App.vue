<template>
  <div id="app">
    <h1>Latest Vue.js Commits</h1>
    <div v-for="(branch, index) in branches" :key=index>
      <input type="radio"
        :id="branch"
        :value="branch"
        name="branch"
        v-model="currentBranch"
      >
      <label :for="branch"> {{ branch }} </label>
    </div>
    <input v-model="quanlity">
    <p>vuejs/vue@{{ currentBranch }} </p>
    <ul>
      <li v-for="(record, index) in commits" :key=index>
        <a :href="record.html_url" target="_blank" class="commit">{{ record.sha.slice(0, 7) }}</a>
        - <span class="message">{{ record.commit.message | truncate }}</span><br>
        by <span class="author"><a :href="record.author.html_url" target="_blank">{{ record.commit.author.name }}</a></span>
        at <span class="date">{{ record.commit.author.date | formatDate }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
var apiURL = 'https://api.github.com/repos/vuejs/vue/commits?per_page='
export default {
  name: 'app',
  data() {
    return {
      branches: ['master', 'dev'],
      currentBranch: 'master',
      commits: null,
      quanlity: 3
    }
  },

  created() {
    this.fetchData()
  },

  watch: {
    currentBranch: 'fetchData',
    quanlity: 'fetchData'
  },

  filters: {
    truncate(v) {
      var newline = v.indexOf('\n')
      return newline > 0 ? v.slice(0, newline) : v
    },
    formatDate(v) {
      return v.replace(/TIZ/g, ' ')
    }
  },

  methods: {
    fetchData() {
      var xhr = new XMLHttpRequest()
      var self = this
      if (this.quanlity==0 || this.quanlity > 100) {
        alert("Limit commit >0 AND <=100")
        return
      }
      xhr.open('GET', apiURL + this.quanlity +'&sha='+self.currentBranch)
      xhr.onload = function () {
        self.commits = JSON.parse(xhr.responseText)
        console.log(self.commits.length)
      }
      xhr.send()
    }
  }
}
</script>

<style>
  #app {
    font-family: 'Helvetica', Arial, sans-serif;
  }
  a {
    text-decoration: none;
    color: #f66;
  }
  li {
    line-height: 1.5em;
    margin-bottom: 20px;
  }
  .author, .date {
    font-weight: bold;
  }
</style>
