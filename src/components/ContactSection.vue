<template>
    <section id="Contact" class="w-100 row g-0">
        <div class="col-lg-8 col-12 areaPrincipal">
            <div class="PrincConteudo w-100 h-100 d-flex align-items-center justify-content-center">
                <section class="w-100">
                    <h2 class="mt-4">{{ titleSection }}</h2>

                    <p> {{ subtitleSection }}</p>

                    <div class="boxLinkContact mb-4">
                        <a class="linkContact">
                            <font-awesome-icon :icon="['fas', 'envelope-square']" class="envelope-square" />

                            <span>{{ email }}</span>
                        </a>

                        <a :href="linkedin" target="_blank" class="linkContact">
                            <font-awesome-icon :icon="['fab', 'linkedin']" class="linkedin" />

                            <span>{{ linkedinLink }}</span>
                        </a>
                    </div>
                </section>
            </div>
        </div>

        <div class="col-lg-4 col-12 areaLateral d-flex align-items-center justify-content-center">
            <div class="PrincConteudoLateral w-100 h-100 d-flex align-items-center justify-content-center">
            <section class="w-100 py-4">
                <h2 class="mb-3">{{ titleMaps }}</h2>

                <span class="localization"><font-awesome-icon :icon="['fas', 'map-marked-alt']" class="map-icon" /> {{ localization }}</span>
                

                <div class="map">
                    <img :src="linkMap" alt="My localization">
                </div>
            </section>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: 'ContactSection',
    props: {
        titleSection: String,
        subtitleSection: String,
        titleMaps: String,
        email: String,
        linkedinLink: String,
        linkedin: String,
        localization: String,
        linkMap: String
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

    #Contact {
        background-color: $color1;
        color: $color5;
        min-height: 100%;
    }

    .areaPrincipal {
        background-image: url(~@/assets/img/bg.jpg);
        background-position: top center;
        background-size: cover;
        min-height: 200px;
        position: relative;
        .PrincConteudo {
            background-color: rgba($color1, 0.83);

            section {
                text-align: center;
                max-width: 80%;

                h2 {
                    color: $color5;
                    font-size: 1.7em;
                }

                p {
                    font-size: 1.05em;
                    color: $color4;
                }

                .boxLinkContact {
                    display: flex;
                    justify-content: space-evenly;
                    align-items: center;

                    .linkContact {
                        color: $color5;
                        text-decoration: none;
                        display: block;
                        width: 100%;
                        margin: 15px 0;
                        transition: all .2s;
    
                        .envelope-square, 
                        .linkedin {
                            color: $color3;
                            font-size: 3.5em;
                            display: inline-block;
                            transition: all .2s;
                        }
    
                        span {
                            font-size: 1.2em;
                            display: block;
                        }
                     
                        &:hover {
                            .envelope-square, 
                            .linkedin {
                                font-size: 3.8em;
                            }

                            color: $color4;
                        }
                    }
                }


                @media only screen and (max-width: 768px) {
                    max-width: 100%;
                    padding: 0 15px;

                    .boxLinkContact {
                        flex-wrap: wrap;
                    }
                }

                @media only screen and (max-width: 375px) {
                    padding: 0 8px;
                }
            }

            @media only screen and (max-width: 991.5px) {
                background-color: $color2;
            }
        }
    }

    .areaLateral {
        background-color: $color2;
        position: relative;

        .PrincConteudoLateral {
            section {
                h2 {
                    font-size: 1.7em;
                }

                .localization {
                    font-size: 1.2em;
                    width: 100%;
                    display: block;
                    .map-icon {
                        color: $color4;
                        font-size: 1.3em;
                        margin-right: 5px;
                    }
                }
                
                .map {
                    background-color: red;
                    border: 2px solid $color4;
                    display: inline-block;
                    border-radius: 10px;
                    max-width: 300px;
                    width: 100%;
                    margin: 20px 5px;

                    img {
                        width: 100%;
                        border-radius: 10px;
                    }
                }
            }
        }


        @media only screen and (max-width: 991.5px) {
            max-width: 100%;
            background-image: url(~@/assets/img/bg.jpg);
            background-position: top center;
            background-size: cover;

            .PrincConteudoLateral {
            background-color: rgba($color1, 0.83);
            padding: 0 15px;
            }
        }
    }
</style>