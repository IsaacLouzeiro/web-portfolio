<template>
    <section id="Home" class="w-100 h-100 row g-0">
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
            <section>
                <img src="../assets/img/img-isaac.jpeg" alt="My Image" class="imgIsaac">
                <h2 class="mt-3 mb-2">{{ myName }}</h2>
                <span class="mb-5">{{ profession }}</span><br>

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
    data() {
        return {
            welcome: "Welcome to my website.",
            subtitleSection: "Recently my passion is creating websites. I'm very curious and constantly searching for new things to learn.",
            btnWhoIam: "Who I'am?",
            btnProjects: "Projects",
            btnContact: "Contact",
            myName: "Isaac Louzeiro",
            profession: "Front-end Developer",
            textWebResume: "My Website Resume is on the link below",
            btnWebResume: "Web Resume",
            scrollDown: "scroll down"
        }
    },
    created() {
        var windowWidth = window.innerWidth;
        if(windowWidth < 768) {
            this.scrollDown = "swipe up"
        }else {
            this.scrollDown = "scroll down"
        }
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
    }

    .areaPrincipal {
        background-image: url(~@/assets/img/bg-home.webp);
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
                    padding: 0 8px;

                    p {
                    font-size: 1.05em;
                }
                }
            }

        }
    }

    .areaLateral {
        background-color: $color2;
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

        .scrollDown {
                position: absolute;
                bottom: 50px;
                right: -25px;
                text-decoration: none;
                color: $color5;
                display: flex;
                align-items: center;

            .arrow {
                margin-left: 5px;
            }
        }
    }
</style>