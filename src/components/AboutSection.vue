<template>
    <section id="About" class="w-100 h-100 row g-0">
        <div class="col-lg-8 col-12 areaPrincipal">
            <div class="PrincConteudo w-100 h-100 d-flex align-items-center justify-content-center">
                
            </div>
        </div>

        <div class="col-lg-4 col-12 areaLateral d-flex align-items-center justify-content-center">
            <section>
                
            </section>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AboutSection'
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

    #About {
        background-color: $color1;
        color: $color5;
    }

    .areaPrincipal {
        background-image: url(~@/assets/img/bg-about.webp);
        background-position: top center;
        background-size: cover;
        min-height: 200px;
        .PrincConteudo {
            background-color: rgba($color1, 0.83);
        }
    }

    .areaLateral {
        background-color: $color2;
        min-height: 400px;
        position: relative;
    }
</style>