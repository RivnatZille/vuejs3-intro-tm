<template>
  <button @click="sendData">
    {{ variant }}
    <slot></slot>
    <slot name="icon"></slot>
  </button>
</template>

<script>
export default {
  name: "AppButton",

  props: {
    variant: {
      type: String,
      default: 'success'
    },
  },

  setup(props, { emit }) {
    const sendData = () => {
      emit('update', props.variant);
    };

    return {
      sendData
    }
  }
}
</script>

<style scoped>

</style>