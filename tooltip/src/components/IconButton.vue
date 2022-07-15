<template lang="pug">
.button-wrapper
    PopupTooltip(:tooltip-text="popupText" :side="popupSide")
      .button(
          :class="[{'disabled': isDisabled}, {'circular': isCircular}]"
          @click.stop="click"
        )
          .button__icon
            slot

</template>

<script>
import PopupTooltip from "./PopupTooltip.vue";

export default {
  components: {
    PopupTooltip
},
  props: {
    isDisabled: {
      type: Boolean,
      default: false
    },
    isCircular: {
      type: Boolean,
      default: false
    },
    backgroundColor: {
      type: String
    },
    color: {
      type: String
    },
    popupText: {
      type: String
    },
    popupSide: {
      type: String
    },
    hasApprovalModal: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    click() {
       this.$emit("clicked")
    },
    approveAction() {
      this.$emit("clicked")
    }
  }
}
</script>

<style lang="scss" scoped>

.button-wrapper {
  position: relative;
  width: fit-content;
}

.button {
  height: 28px;
  width: 28px;
  box-sizing: border-box;
  border: 1px solid gray;
  border-radius: 2px;
  transition: .2s ease-out;
  display: flex;
  justify-content: center;
  align-items: center;
  background: white;

  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;

  &:not(.disabled):hover {
    .button__icon {
      color: gray;
    }
  }

  &__icon {
    color: black;
    margin-top: 2px;
  }
}

.button:not(.disabled) {
  cursor: pointer;
}

.disabled {
  opacity: 0.44;
}

.circular {
  border-radius: 50%;
}

</style>
