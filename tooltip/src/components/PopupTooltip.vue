<template lang="pug">
.tooltip Hello
    slot
    .tooltiptext(v-if="tooltipText" :class="side" :style="{backgroundColor: backgroundColor, color: color}") {{ tooltipText }}
</template>

<script>
export default {
  name: 'PopupTooltip',
  props: {
    tooltipText: {
      type: String,
      default: 'Hi there'
    },
    side: {
      type: String,
      default: 'top'
    },
    isDisabled: {
      type: Boolean,
      default: false
    },
    backgroundColor: {
      type: String,
      default: '#fff'
    },
    color: {
      type: String,
      default: '#333'
    },

  }

}
</script>

<style lang="scss" scoped>

.tooltip {
  position: relative;
  display: inline-block;
  width: fit-content;

  &:hover .tooltiptext {
    visibility: visible;
  }
}
.tooltip .tooltiptext {
  visibility: hidden;
  width: fit-content;
  background-color: white;
  text-align: center;
  padding: 7px 15px;
  border: 1px solid gray;
  word-break: break-word;
  white-space: nowrap;
  border-radius: 2px;
  //inset: auto auto 0px 0px;


  position: absolute;
  z-index: 1;
}
.top {
  bottom: 100%;
  right: 50%;
  transform: translateX(50%);
  margin-bottom: 10px;
}
.right {
  top: -2px;
  left: 130%;
}
.left {
  top: -2px;
  right: 130%;
}
.bottom {
  top: 100%;
  right: 50%;
  transform: translateX(50%);
  margin-top: 10px;
}
</style>
