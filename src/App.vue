<template>
  <div id="app">
    <mirror-panel :rotate="'X'">
      {{ text }}
    </mirror-panel>
    <controls
      :text="text"
      @emitText="updateText"
    >
      <load-button @emitText="updateText" />
    </controls>
    <mirror-panel :rotate="'Y'">
      {{ text }}
    </mirror-panel>
  </div>
</template>

<script>
import MirrorPanel from './components/MirrorPanel.vue';
import Controls from './components/Controls.vue';
import LoadButton from './components/LoadButton.vue';

export default {
  name: 'App',
  components: {
    MirrorPanel,
    Controls,
    LoadButton,
  },
  data() {
    return {
      text: '',
    };
  },
  methods: {
    updateText(e) {
      this.text = e;
    },
  },
};
</script>

<style>
:root {
  --vue-green: #41b883;
  --vue-dark-green: #35495e;
}

html,
body,
#app {
  height: 100%;
  width: 100%;
  box-sizing: border-box;
}

#app {
  font-family: "Lora", "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* color: #2c3e50; */
  color: var(--vue-dark-green);
  /* margin-top: 60px; */

  /* legacy css below */
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  background: #fdfdfd;
}

mirror-panel {
  color: red;
}
</style>
