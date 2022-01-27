<template>
  <div class="home">
    <div v-show="this.manut == 1">
        <EmManutencao />
    </div>

    <!-- seção principal -->
    <section v-show="this.manut == 0" class="principal">
        oi
    </section>
  </div>
</template>

<script>
// @ is an alias to /src
import EmManutencao from '@/components/EmManutencao.vue'

export default {
  name: 'Home',
  data() {
      return {
        // manutencao
          manut: 0
      }
  },
  components: {
    EmManutencao
  }
}
</script>

<style lang="scss" scoped>
    .home {
        height: 100%;
        
    }
</style>
