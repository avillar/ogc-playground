<template>
  <div
    class="process-pill d-inline-block"
    :class="{ active, startMarker, endMarker }"
  >
    <div class="content" :style="{ backgroundColor: bgColor, color: textColor, opacity }">
      <slot></slot>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    startMarker: {
      type: Boolean,
      default: true,
    },
    endMarker: {
      type: Boolean,
      default: true,
    },
    bgColor: {
      type: String,
      default: '#00b1ff',
    },
    textColor: {
      type: String,
      default: 'white',
    },
    active: {
      type: Boolean,
      default: false,
    },
    opacity: {
      type: Number,
      default: 1.0,
    },
  },
}
</script>
<style>
.process-pill .content {
  padding: 0.3em 0.5em;
}
.process-pill {
  cursor: pointer;
}
.process-pill:hover {
  opacity: 0.8;
}
.process-pill.startMarker .content {
  padding-left: 1em;
  margin-left: -0.25em;
  clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 0% 100%, 1em 50%);
}
.process-pill.endMarker .content {
  padding-right: 1em;
  margin-right: -0.25em;
  clip-path: polygon(0% 0%, calc(100% - 1em) 0%, 100% 50%, calc(100% - 1em) 100%, 0% 100%);
}
.process-pill.startMarker.endMarker .content {
  clip-path: polygon(0% 0%, calc(100% - 1em) 0%, 100% 50%, calc(100% - 1em) 100%, 0% 100%, 1em 50%);
}
</style>