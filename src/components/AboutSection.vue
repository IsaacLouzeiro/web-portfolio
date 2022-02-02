<template>
    <section id="About" class="w-100 row g-0">
        <div class="col-lg-8 col-12 areaPrincipal">
            <div class="PrincConteudo w-100 h-100 d-flex align-items-center justify-content-center">
                <section class="w-100">
                    <h2 class="mt-4">{{ titleSection }}</h2>

                    <p v-for="text in aboutText" :key="text.aboutText" class="my-2">{{ text }}</p>

                    <span class="mt-3 d-inline-block">{{ moreDetails }}</span><br>

                    <a href="https://isaac-resume.firebaseapp.com/" target="_blank" class="btn mt-2 mb-4"><font-awesome-icon :icon="['fas', 'window-maximize']" /> {{ btnWebResume }}</a>
                </section>
            </div>
        </div>

        <div class="col-lg-4 col-12 areaLateral d-flex align-items-center justify-content-center">
            <section class="w-100 py-4">
                <h2 class="mb-3">{{ titleSkills }}</h2>

                <div class="subSkills">
                    <h3>{{ hardSkill }}</h3>
                    
                    <span class="boxSkills" v-for="item in boxSkill" :key="item.boxSkill"><img :src="item.linkImg" :alt="item.name"> {{ item.name }}</span>
                </div>

                <div class="subSkills">
                    <h3>{{ softSkill }}</h3>
                    <span class="boxSoftSkill my-1 d-block" v-for="item in boxSoftSkill" :key="item.boxSoftSkill"><div class="circleSkill"></div> {{ item }}</span>
                </div>
            </section>
        </div>
    </section>
</template>

<script>
export default {
    name: 'AboutSection',
    props: {
        titleSection: String,
        aboutText: Array,
        moreDetails: String,
        btnWebResume: String,
        titleSkills: String,
        hardSkill: String,
        softSkill: String,
        boxSkill: Array,
        boxSoftSkill: Array
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

    #About {
        background-color: $color1;
        color: $color5;
        min-height: 100%;
    }

    .areaPrincipal {
        background-image: url(~@/assets/img/bg-about.webp);
        background-position: top center;
        background-size: cover;
        min-height: 200px;
        .PrincConteudo {
            background-color: rgba($color1, 0.83);

            section {
                text-align: left;
                max-width: 80%;

                h2 {
                    color: $color4;
                    font-size: 1.7em;
                }

                p {
                    font-size: 1.05em;
                }

                span {
                    font-size: 1.2em;
                }

                .btn {
                    background-color: $color3;
                    color: $color5;

                    &:hover {
                        background-color: $color4;
                    }
                }

                @media only screen and (max-width: 768px) {
                    max-width: 100%;
                    padding: 0 15px;
                }

                @media only screen and (max-width: 375px) {
                    padding: 0 8px;
                }
            }
        }
    }

    .areaLateral {
        background-color: $color2;
        position: relative;

        section {
            h2 {
                font-size: 1.7em;
            }

            .subSkills {
                max-width: 83%;
                margin: auto;
                text-align: left;
                padding: 15px 0;

                h3 {
                    font-size: 1.4em;
                    padding: 10px 0;
                }

                .boxSkills {
                    background-color: $color4;
                    padding: 4px 7px;
                    margin: 0 7px 7px 0;
                    display: inline-block;
                    font-size: .9em;

                    img {
                        width: 20px;
                        height: 20px;
                    }
                }

                .boxSoftSkill {
                    padding-bottom: 7px;
                    display: inline-block;
                    .circleSkill {
                        width: 15px;
                        height: 15px;
                        border-radius: 10px;
                        background-color: $color4;
                        display: inline-block;
                    }
                }

                @media only screen and (max-width: 768px) {
                    max-width: 100%;
                    padding: 0 15px;

                    h3 {
                        padding-top: 30px;
                    }
                }

                @media only screen and (max-width: 375px) {
                    padding: 0 8px;
                }
            }
        }
    }
</style>