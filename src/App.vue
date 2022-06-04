<template>
    <CarregadorSite v-show="montado === 0" />
    <router-view/>
</template>

<script>
    import CarregadorSite from './components/CarregadorSite.vue';

    export default {

        data() {
            return {
                montado: null
            }
        },
        components: {
            CarregadorSite
        },
        beforeMount() {
            this.montado = 0

            
        },
        mounted() {
            setTimeout(() => {
                this.montado = 1
            }, 2500);
        }
    }
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Ubuntu:wght@400;500;700&display=swap');

* { margin: 0; padding: 0; box-sizing: border-box; transition: all .1s; }


body {
    overflow: hidden;
}

html, body, #app {
    height: 100%;
}

#app {
  font-family: 'Ubuntu', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#CarregadorSite {
    position: absolute;
    z-index: 10000000000;
    overflow: hidden;
}
</style>
