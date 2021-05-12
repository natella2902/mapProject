<template>
  <div class="map">
    <svg viewBox="0 0 1226 656">
      <path
          v-for="(reg, idx) in regs"
          :d="reg.temp"
          class="part"
          @click="$emit('currentReg', idx)"
      />
    </svg>
    <img src="../svg/map_russia2.svg" alt="Карта России">
  </div>
</template>

<script>

export default {
  emits: ['currentReg'],
  props: {
    regs: {
      type: Array
    }
  }
}
</script>

<style scoped>


</style>