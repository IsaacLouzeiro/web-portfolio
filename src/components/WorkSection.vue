<template>
    <section id="Work" class="w-100 row g-0">
        <div class="col-12 areaPrincipal row g-0">
            <div class="areaCentral col-lg-8 col-12"></div>
            <div class="col-lg-4 col-12 d-none d-lg-block areaLateral"></div>

            <div class="PrincConteudo h-100 container py-4">
                    <h2 class="mt-3">{{ titleSection }}</h2>

                    <div class="mt-3 mb-4">
                        <a href="#" @click="projFreelancer" id="projFreelancer" class="btn my-1 active">{{ btnFreela }}</a>
                        <a href="#" @click="projPessoal" id="projPersonal" class="btn my-1">{{ btnPersonal }}</a>
                    </div>


                    <ul class="box-projetos">
                        <li v-for="item in projFreela" :key="item.projFreela" v-show="this.freelancer == 'open'">
                            <div @click="arrayFreela(item.id, 'boxOpen')">
                                <div class="bg-proj">
                                    <img :src="item.img" :alt="item.alt">
                                </div>
                                <div class="bottom-proj">
                                    <span>{{ item.nome }}</span>
                                </div>
                            </div>

                            <div :id="item.id" class="another-box">
                                <section>
                                    <div class="box-header">
                                        <span class="box-title">{{ item.nome }}</span>
                                        <span @click="arrayFreela(item.id, 'boxClose')" class="btn-close"></span>
                                    </div>
                                </section>
                            </div>
                        </li>

                        <li v-for="item in projPersonal" :key="item.projPersonal" v-show="this.pessoal == 'open'">
                            <div @click="arrayFreela(item.id, 'boxOpen')">
                                <div class="bg-proj">
                                    <img :src="item.img" :alt="item.alt">
                                </div>
                                <div class="bottom-proj">
                                    <span>{{ item.nome }}</span>
                                </div>
                            </div>

                            <div :id="item.id" class="another-box">
                                <section>
                                    <div class="box-header">
                                        <span class="box-title">{{ item.nome }}</span>
                                        <span @click="arrayFreela(item.id, 'boxClose')" class="btn-close"></span>
                                    </div>
                                </section>
                            </div>
                        </li>
                    </ul>


                    <nav class="mb-3">
                        <ul class="pagination d-flex align-items-center justify-content-center">
                            <li class="page-item">
                                <a class="page-link link-arrow" href="#" aria-label="Previous">
                                    &lsaquo;
                                </a>
                            </li>
                            <li class="page-item active"><a class="page-link" href="#">1</a></li>
                            <li class="page-item"><a class="page-link" href="#">2</a></li>
                            <li class="page-item"><a class="page-link" href="#">3</a></li>
                            <li class="page-item">
                                <a class="page-link link-arrow" href="#" aria-label="Next">
                                    &rsaquo;
                                </a>
                            </li>
                        </ul>
                    </nav>

                    <a href="https://github.com/IsaacLouzeiro" class="btn btn-github my-3" target="_blank"><font-awesome-icon :icon="['fab', 'github-alt']" class="github-icon" /> {{ seeMore }}</a>
            </div>
        </div>

    </section>
</template>

<script>
export default {
    name: 'WorkSection',
    data() {
        return {
            freelancer: 'open',
            pessoal: 'closed'
        }
    },
    props: {
        titleSection: String,
        btnFreela: String,
        btnPersonal: String,
        seeMore: String,
        projFreela: Array,
        projPersonal: Array
    },
    methods: {
        projFreelancer() {
            document.getElementById('projPersonal').classList.remove('active')
            document.getElementById('projFreelancer').classList.add('active')

            this.freelancer = "open"
            this.pessoal = "closed"
        },

        projPessoal() {
            document.getElementById('projFreelancer').classList.remove('active')
            document.getElementById('projPersonal').classList.add('active')
        
            this.freelancer = "closed"
            this.pessoal = "open"
        },

        arrayFreela(id, who) {
            if(who === "boxOpen") {
                document.getElementById(id).setAttribute('style', 'z-index: 10000000 !important; padding-left: 0 !important');
                // alert(who)
            }else {
                document.getElementById(id).setAttribute('style', 'z-index: -100000000 !important; padding-left: 1000px !important');
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
        background-image: url(~@/assets/img/bg-work.webp);
        background-position: top center;
        background-size: cover;
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
            background-color: rgba($color1, 0.83);
            border-left: 5px dashed $color2;
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
                margin: auto 7px;

                &.active {
                    background-color: $color4;
                }

                &:hover {
                    background-color: $color4;
                }

                @media only screen and (max-width: 375px) {
                    margin: auto 3px;
                    padding: 5px 7px;
                    font-size: .9em;
                }
            }



            .box-projetos {
                list-style-type: none;
                padding: 0;

                li {
                    margin: 3px;
                    display: inline-block;

                    .bg-proj {
                        border: 3px solid $color4;

                        img {
                            width: 100%;
                        }
                    }

                    .bottom-proj {
                        background-color: $color2;
                        text-align: left;

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
                        align-items: center;
                        background-color: rgba($color2, .2);
                        transition: z-index .3s, padding .7s;
                        padding-left: 1000px;

                        section {
                            background-color: $color2;
                            width: 100%;
                            max-width: 500px;
                            height: 500px;

                            .box-header {
                                display: flex;
                                justify-content: space-between;
                                align-items: center;
                                padding: 15px;
                                border-bottom: 1px solid $color3;

                                .box-title {
                                    font-size: 1.2em;
                                }

                                .btn-close {
                                    background-color: $color4;
                                    font-size: 1em;
                                    padding: 5px 10px;
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