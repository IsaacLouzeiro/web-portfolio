<template>
    <section id="Work" class="w-100 row g-0">
        <div class="col-12 areaPrincipal row g-0">
            <div class="areaCentral col-lg-8 col-12"></div>
            <div class="col-lg-4 col-12 d-none d-lg-block areaLateral"></div>

            <div class="PrincConteudo h-100 d-flex align-items-center justify-content-center">
                <section class="container py-4">
                    <h2 class="mt-3">{{ titleSection }}</h2>

                    <a href="#" class="btn mt-3 mb-4">{{ btnFreela }}</a>
                    <a href="#" class="btn mt-3 mb-4">{{ btnPersonal }}</a>



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
                </section>
            </div>
        </div>

    </section>
</template>

<script>
export default {
    name: 'WorkSection',
    props: {
        titleSection: String,
        btnFreela: String,
        btnPersonal: String
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

    #Work {
        background-color: $color1;
        color: $color5;
        min-height: 100%;
    }

    .areaPrincipal {
        min-height: 250px;
        background-image: url(~@/assets/img/bg-work.webp);
        background-position: top center;
        background-size: cover;
        position: relative;

        .areaCentral {
            background-color: rgba($color1, 0.83);
        }

        .areaLateral {
            background-color: rgba($color1, 0.83);
            border-left: 5px dashed $color2;
        }

        .PrincConteudo {
            position: absolute;

            section {
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

                    &:hover {
                        background-color: $color4;
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
                }


                @media only screen and (max-width: 768px) {
                    
                }

                @media only screen and (max-width: 375px) {
                    
                }
            }
        }
    }

</style>