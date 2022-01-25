<template>
  <div class="home">
    <EmManutencao />
  </div>
</template>

<script>
// @ is an alias to /src
import EmManutencao from '@/components/EmManutencao.vue'

export default {
  name: 'Home',
  components: {
    EmManutencao
  }
}
</script>

<style lang="scss" scoped>
    .home {
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>
