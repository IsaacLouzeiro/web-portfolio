<template>
    <section id="CarregadorSite">
        <img src="../assets/img/logo-isaac-louzeiro-tiny.png" alt="my logo">
    </section>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

    #CarregadorSite {
        background-color: $color3;
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        @keyframes loading {
            0% {
                margin-bottom: 0;
            }
            50% {
                margin-bottom: 15px;
            }
            100% {
                margin-bottom: 0;
            }
        }

        img {
            position: relative;
            width: 150px;
            animation: loading 1.5s linear infinite;
        }
    }
</style>