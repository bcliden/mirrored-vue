<template>
  <div
    class="mirror"
    :style="{transform: `rotate${rotate}(0.5turn)`}"
  >
    <slot />
  </div>
</template>

<script>
export default {
  props: {
    rotate: {
      type: String,
      default: 'X',
    },
  },
};
</script>

<style scoped>
.mirror {
  flex: 3 1 auto;
  max-height: 42.5%;

  margin: 0;
  font-size: 5rem;
  text-align: justify;
  overflow-y: auto;
  width: 100%;

  /* overflow & word-break section */
  overflow-wrap: break-word;
  word-wrap: break-word;
  word-break: break-word;
  -ms-hyphens: auto;
  -moz-hyphens: auto;
  -webkit-hyphens: auto;
  hyphens: auto;
}
</style>
