<template>
  <div id="app">
   {{ message }}
    <filestack
      :apikey="apiKey"
      @success="onSuccess"
      @error="onError"
    >
      <div>
        <strong>Find an avatar</strong>
        <button>Pick</button>
      </div>
    </filestack>
  </div>
</template>

<script>
import Filestack from './components/Filestack.vue';

export default {
  name: 'app',
  data: {
    message: 'hello',
    apiKey: 'AB7ajh1uiSdvYW4cQPX7Iz'
  },
  methods: {
    onSuccess(event) {
      console.log('Success: ',event);
    },
    onError(event) {
      console.log('Error: ', event)
    }
  },
  components: {
    filestack: Filestack.default
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
