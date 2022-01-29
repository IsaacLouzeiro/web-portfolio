<template>
    <div class="bg-warning w-100 h-100" v-show="criado == 0">
        {{ texto }}
    </div>
    <router-view/>
</template>

<script>
    export default {
        data() {
            return {
                texto: 'nao criado',
                criado: 1
            }
        },
        beforeMount() {
            this.criado = 0
        },
        mounted() {
            this.criado = 1
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
</style>
