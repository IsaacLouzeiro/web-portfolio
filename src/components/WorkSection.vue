<template>
    <section id="Work" class="w-100 row g-0">
        <div class="col-12 areaPrincipal row g-0">
            <div class="areaCentral col-lg-8 col-12"></div>
            <div class="col-lg-4 col-12 d-none d-lg-block areaLateral"></div>

            <div class="PrincConteudo h-100 container py-4 d-flex flex-wrap">
                    <h2 class="mt-3 w-100">{{ titleSection }}</h2>

                    <div class="mt-3 mb-4 w-100 align-self-start">
                        <a href="#" @click="projFreelancer" id="projFreelancer" class="btn my-1">
                            <font-awesome-icon v-if="this.freelancer == 'closed'" :icon="['far', 'dot-circle']"/> 
                            <font-awesome-icon v-else :icon="['fas', 'dot-circle']"/> 
                            {{ btnFreela }}
                        </a>
                        <a href="#" @click="projPessoal" id="projPersonal" class="btn my-1 ativo">
                            <font-awesome-icon v-if="this.pessoal == 'closed'" :icon="['far', 'dot-circle']"/> 
                            <font-awesome-icon v-else :icon="['fas', 'dot-circle']"/>
                            {{ btnPersonal }}
                        </a>
                    </div>


                    <ul class="box-projetos w-100">
                        <li v-for="item in projFreela" :key="item.projFreela" v-show="this.freelancer == 'open'">
                            <a :href="'#'+item.id" @click="arrayFreela(item.id, 'boxOpen')">
                                <div class="bg-proj">
                                    <img :src="item.img" :alt="item.alt">
                                </div>
                                <div class="bottom-proj">
                                    <span>{{ item.nome }}</span>
                                </div>
                            </a>

                            <div :id="item.id" class="another-box">
                                <section>
                                    <div class="box-header">
                                        <span class="box-title">{{ item.nome }}</span>
                                        <span @click="arrayFreela(item.id, 'boxClose')" class="btn-close"></span>
                                    </div>

                                    <div class="box-main">
                                        <img :src="item.img" :alt="item.alt">

                                        <h4 class="mt-3">{{ about }}</h4>
                                        <p class="Itemdesc">{{ item.description }}</p>

                                        <h4 class="mt-3">{{ technology }}</h4>
                                        <p>{{ item.technologies }}</p>
                                    </div>

                                    <div class="box-footer">
                                        <a v-show="item.link != ''" :href="item.link" class="btn btn-website my-3 align-self-end" target="_blank"><font-awesome-icon :icon="['fas', 'window-maximize']" class="window-maximize" /> {{ linkWebsite }}</a>
                                        <a v-show="item.repo != ''" :href="item.repo" class="btn btn-repo my-3 align-self-end" target="_blank"><font-awesome-icon :icon="['fab', 'github']" class="repoGithub" /></a>
                                    </div>
                                </section>
                            </div>
                        </li>

                        <li v-for="item in projPersonal" :key="item.projPersonal" v-show="this.pessoal == 'open'">
                            <a :href="'#'+item.id" @click="arrayFreela(item.id, 'boxOpen')">
                                <div class="bg-proj">
                                    <img :src="item.img" :alt="item.alt">
                                </div>
                                <div class="bottom-proj">
                                    <span>{{ item.nome }}</span>
                                </div>
                            </a>

                            <div :id="item.id" class="another-box">
                                <section>
                                    <div class="box-header">
                                        <span class="box-title">{{ item.nome }}</span>
                                        <span @click="arrayFreela(item.id, 'boxClose')" class="btn-close"></span>
                                    </div>

                                    <div class="box-main">
                                        <img :src="item.img" :alt="item.alt">

                                        <h4 class="mt-3">{{ about }}</h4>
                                        <p class="Itemdesc">{{ item.description }}</p>

                                        <h4 class="mt-3">{{ technology }}</h4>
                                        <p>{{ item.technologies }}</p>
                                    </div>

                                    <div class="box-footer">
                                        <a v-show="item.link != ''" :href="item.link" class="btn btn-website my-3 align-self-end" target="_blank"><font-awesome-icon :icon="['fas', 'window-maximize']" class="window-maximize" /> {{ linkWebsite }}</a>
                                        <a v-show="item.repo != ''" :href="item.repo" class="btn btn-repo my-3 align-self-end" target="_blank"><font-awesome-icon :icon="['fab', 'github']" class="repoGithub" /></a>
                                    </div>
                                </section>
                            </div>
                        </li>
                    </ul>

                    <a href="https://github.com/IsaacLouzeiro" class="btn btn-github my-3 align-self-end" target="_blank"><font-awesome-icon :icon="['fab', 'github-alt']" class="github-icon" /> {{ seeMore }}</a>
            </div>
        </div>

    </section>
</template>

<script>
export default {
    name: 'WorkSection',
    data() {
        return {
            freelancer: 'closed',
            pessoal: 'open',
        }
    },
    props: {
        titleSection: String,
        btnFreela: String,
        btnPersonal: String,
        seeMore: String,
        projFreela: Array,
        projPersonal: Array,
        linkWebsite: String,
        about: String,
        technology: String
    },
    methods: {
        projFreelancer() {
            document.getElementById('projPersonal').classList.remove('ativo')
            document.getElementById('projFreelancer').classList.add('ativo')

            this.freelancer = "open"
            this.pessoal = "closed"
        },

        projPessoal() {
            document.getElementById('projFreelancer').classList.remove('ativo')
            document.getElementById('projPersonal').classList.add('ativo')
        
            this.freelancer = "closed"
            this.pessoal = "open"
        },

        arrayFreela(id, who) {
            if(who === "boxOpen") {
                document.getElementById(id).setAttribute('style', 'z-index: 10000000 !important; padding-top: 0 !important');
                // alert(who)
            }else {
                document.getElementById(id).setAttribute('style', 'z-index: -100000000 !important; padding-top: 500px !important');
                // alert(who)
            }

        },
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

    * {
        overflow-x: hidden;
    }

    #Work {
        background-color: $color1;
        color: $color5;
        min-height: 100%;
    }

    .areaPrincipal {
        min-height: 550px;
        background-image: url(~@/assets/img/bg.jpg);
        background-position: center;
        background-size: cover;
        background-repeat: no-repeat;
        position: relative;

        .areaCentral {
            position: absolute;
            top: 0;
            bottom: 0;
            background-color: rgba($color1, 0.83);
        }

        .areaLateral {
            position: absolute;
            top: 0;
            bottom: 0;
            right: 0;
            background-color: rgba($color2, 1);
            box-shadow: inset 0 -3px 5px rgba($color3, .2);
        }

        .PrincConteudo {
            // position: absolute;
            position: relative;

            h2 {
                color: $color5;
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
                margin: auto 5px;

                &.ativo {
                    background-color: $color4;
                }

                &:hover {
                    background-color: $color4;
                }

                @media only screen and (max-width: 425px) {
                    padding: 5px 6px;
                    margin: auto 3.5px;
                    font-size: 1em;
                }

                @media only screen and (max-width: 375px) {
                    padding: 5px 6px;
                    margin: auto 4px;
                    font-size: .85em;
                }
            }



            .box-projetos {
                list-style-type: none;
                padding: 0;

                li {
                    margin: 3px;
                    display: inline-block;
                    border: 3px solid $color4;

                    a {
                        text-decoration: none;
                        color: $color5;
                    }

                    .bg-proj {
                        // border: 3px solid $color4;

                        img {
                            width: 100%;
                            max-width: 300px;
                            max-height: 169px;
                        }
                    }

                    .bottom-proj {
                        border-top: 2px solid $color4;
                        background-color: $color2;
                        text-align: left;
                        display: flex;
                        align-items: center;
                        padding: 2px;

                        span {
                            font-size: 1em;
                            display: inline-block;
                            margin: 3px 8px;
                        }
                    }

                    .another-box {
                        position: absolute;
                        top: 0;
                        bottom: 0;
                        left: 0;
                        right: 0;
                        margin: auto;
                        z-index: -1000;
                        display: flex;
                        justify-content: center;
                        align-items: flex-start;
                        background-color: rgba($color2, .2);
                        transition: z-index .3s, padding .7s;
                        padding-top: 500px;
                        overflow: hidden;

                        section {
                            background-color: $color2;
                            width: 100%;
                            max-width: 500px;
                            // height: 500px;
                            display: flex;
                            flex-direction: column;
                            justify-content: space-between;
                            margin-top: 40px;

                            .box-header {
                                display: flex;
                                justify-content: space-between;
                                align-items: center;
                                padding: 15px;
                                margin-bottom: 10px;
                                border-bottom: 1px solid $color3;

                                .box-title {
                                    font-size: 1.4em;
                                    font-weight: bold;
                                }

                                .btn-close {
                                    background-color: $color4;
                                    font-size: 1em;
                                    padding: 5px 10px;
                                }
                            }

                            .box-main {
                                padding: 0 5px;
                                
                                .Itemdesc {
                                    text-align: left;
                                    padding: 0 5px;
                                    display: inline-block;
                                }

                                img {
                                    border: 3px solid $color4;
                                    max-width: 300px;
                                    max-height: 169px;
                                }

                                h4 {
                                    font-size: 1.4em;
                                    font-weight: bold;
                                }
                            }

                            .box-footer {
                                display: flex;
                                justify-content: center;
                                align-items: center;
                                border-top: 1px solid $color3;

                                .btn-website,
                                .btn-repo {
                                    background-color: $color4;
                                    font-size: 1.1em;

                                    &:hover {
                                        background-color: $color3;
                                    }
                                }

                                .btn-repo {
                                    text-decoration: none;
                                    color: $color5;
                                    padding: 5px 15px;
                                }
                            }
                        }
                    }
                }
            }



            .pagination {
                .page-item {
                    margin: 5px;

                    .page-link {
                        border-radius: 3px;
                        background-color: $color3;
                        color: $color5;
                        border: none;
                        padding: 2px 10px;

                        &.link-arrow {
                            overflow: hidden;
                            border-radius: 20px;
                            width: 20px;
                            height: 20px;
                            padding: 0;
                            background-color: $color5;
                            color: $color1;
                            font-weight: bold;
                            font-size: 1.2em;
                            display: flex;
                            justify-content: center;
                            align-items: center;
                        }

                    }
                    :hover {
                        background-color: $color4;

                        &.link-arrow {
                            background-color: $color4;
                            color: $color5;
                        }
                    }
                }

                @media only screen and (max-width: 375px) {
                    font-size: .9em;
                }
            }

            .btn-github {
                width: 140px;
                display: flex;
                justify-content: space-evenly;
                align-content: center;
                font-size: 1.1em;
                margin: auto;
                .github-icon {
                    font-size: 1.5em;
                }

                @media only screen and (max-width: 375px) {
                    font-size: 1em;
                }
            }
        }
    }

</style>