<template>
  <div class="home">
    <div v-show="this.manut == 1" class="manutencao">
        <EmManutencao />
    </div>

    <!-- site funcional -->
    <section v-show="this.manut == 0" class="principal d-flex">
        <!-- menu navegação -->
        <NavBar />

        <!-- conteudo principal -->
        <main class="w-100">
            <HomeSection />    
        </main>
        <!-- // conteudo principal -->
    </section>
    <!-- // site funcional -->
  </div>
</template>

<script>
// @ is an alias to /src
import EmManutencao from '@/components/EmManutencao.vue'
import NavBar from '@/components/NavBar.vue'
import HomeSection from '@/components/HomeSection.vue'

export default {
  name: 'Home',
  data() {
      return {
        // manutencao
          manut: 0
      }
  },
  components: {
    EmManutencao,
    NavBar,
    HomeSection
  }
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

    .home, .principal, body {
        height: 100%;
        background-color: $color3;
    }

    .manutencao {
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: $color5;
    }

    main {
        margin-left: 70px;

        @media only screen and (max-width: 768px) {
            margin-left: 65px;
        }
    }

</style>
