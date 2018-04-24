<template>
  <button @click="disableMe" :disabled="isDisabled">Click me</button>
</template>

<script>
export default {
  data() {
      return {
          isDisabled: false
      }
  },
  methods: {
      disableMe() {
          this.isDisabled = true;
          setTimeout(() => {
              this.isDisabled = false
          }, 10000);
      }
  }
}
</script>

