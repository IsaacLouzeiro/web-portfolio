<template>
    <section id="Home" class="w-100 row g-0">
        <div class="col-lg-8 col-12 areaPrincipal">
            <div class="PrincConteudo w-100 h-100 d-flex align-items-center justify-content-center">
                <section>
                    <h2 class="line-1 anim-typewriter">{{ welcome }}</h2>
                    <p>{{ subtitleSection }}</p>

                    <div class="d-none d-md-block">
                        <a href="#About" class="btn">{{ btnWhoIam }}</a>
                        <a href="#Work" class="btn">{{ btnProjects }}</a>
                        <a href="#Contact" class="btn">{{ btnContact }}</a>
                    </div>
                </section>
            </div>
        </div>

        <div class="col-lg-4 col-12 areaLateral d-flex align-items-center justify-content-center">
            <section class="py-3">
                <img src="../assets/img/img-isaac.jpeg" alt="My Image" class="imgIsaac">
                <div class="pt-4">
                    <img :src="linkLogo" alt="My Logo" class="myLogo">
                </div>
                <h2 class="mt-1 mb-1">{{ myName }}</h2>
                <span class="mb-5 fst-italic">{{ profession }}</span><br>


                <span class="webResume">{{ textWebResume }}</span><br>

                <a href="https://isaac-resume.firebaseapp.com/" target="_blank" class="btn mt-3"><font-awesome-icon :icon="['fas', 'window-maximize']" /> {{ btnWebResume }}</a>
            </section>

            <a href="#About" class="scrollDown bounce">{{ scrollDown }} <font-awesome-icon :icon="['fas', 'long-arrow-alt-right']" class="arrow" /></a>
        </div>
    </section>
</template>

<script>
export default {
    name: 'HomeSection',
    props: {
        welcome: String,
        subtitleSection: String,
        btnWhoIam: String,
        btnProjects: String,
        btnContact: String,
        myName: String,
        profession: String,
        textWebResume: String,
        btnWebResume: String,
        linkLogo: String,
        scrollDown: String
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';
    @import '../assets/scss/writingAnimation.scss';
    @import '../assets/scss/arrowAnimation.scss';

    #Home {
        background-color: $color1;
        color: $color5;
        min-height: 100%;
    }

    .areaPrincipal {
        background-image: url(~@/assets/img/bg.gif);
        background-position: top center;
        background-size: cover;
        min-height: 200px;
        .PrincConteudo {
            background-color: rgba($color1, 0.83);

            section {
                text-align: left;
                max-width: 80%;

                p {
                    color: $color4;
                    font-size: 1.18em;
                }

                .btn {
                    background-color: $color3;
                    color: $color5;
                    margin-right: 15px;
                    font-size: 1.18em;

                    &:hover {
                        background-color: $color4;
                    }
                }

                @media only screen and (max-width: 768px) {
                    max-width: 100%;
                    padding: 0 15px;

                    h2 {
                        font-size: 1.55em;
                    }

                    p {
                        font-size: 1.05em;
                    }
                }

                @media only screen and (max-width: 375px) {
                    padding: 0 8px;

                    h2 {
                        font-size: 1.3em;
                    }

                    p {
                        font-size: 1em;
                    }
                }
            }

        }

        @media only screen and (max-width: 992px) {
            background-position: center;
        }
    }

    .areaLateral {
        background-color: $color2;
        box-shadow: inset 0 -3px 5px rgba($color3, .2);
        min-height: 400px;
        position: relative;

        section {
            
            .imgIsaac {
                width: 130px;
                height: 130px;
                border: 4px solid $color4;
                border-radius: 65px;
            }

            h2 {
                font-size: 1.4em;
                font-weight: 600;
            }

            span {
                display: inline-block;
                font-size: 1.07em;
                max-width: 65%;

                &.webResume {
                    font-size: 1.1em;
                }
            }

            @keyframes loading {
                0% {
                    bottom: 0;
                }
                50% {
                    bottom: 5px;
                }
                100% {
                    bottom: 0;
                }
            }

            .myLogo {
                width: 100%;
                max-width: 60px;
                position: relative;
                // filter: drop-shadow(0 0 .6rem rgba($color3, .3));
                animation: loading 1.7s linear infinite;
            }

            a.btn {
                background-color: $color4;
                color: $color5;
                font-size: 1.2em;
                padding: 5px 15px;

                &:hover {
                    background-color: $color3;
                }
            }
        }
    }
</style>