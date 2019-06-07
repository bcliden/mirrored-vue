<template>
  <div class="controls">
    <label>words:
      <input
        type="text"
        :value="text"
        placeholder="type some text"
        @input="emitChange"
      >
    </label>
    <slot />
  </div>
</template>

<script>
export default {
  props: {
    text: {
      type: String,
      default: '',
    },
  },
  methods: {
    emitChange(e) {
      // console.log(e);
      this.$emit('emitText', e.target.value);
    },
  },
};
</script>

<style scoped>
.controls {
  background: #efefef;

  height: 10%;
  width: 100%;
  border-top: 1px dashed #2e382e;
  border-bottom: 1px dashed #2e382e;
  padding: 0.5rem 0;

  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}

input[type="text"] {
  padding: 3px;
  margin: 5px 0;
}

load-button {
  margin-left: 2rem;
}
</style>
