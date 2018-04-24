<template>
  <button @click="confirm">{{ label }}</button>
</template>

<script>
export default {
  data() {
      return {
          label: 'Confirm'
      }    
  }
}
</script>
