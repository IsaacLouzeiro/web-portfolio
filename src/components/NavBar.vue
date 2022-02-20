<template>
    <nav class="d-flex flex-column justify-content-between fixed-top" id="navbar">
        <div class="dropdown">
            <button class="" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
                <!-- <font-awesome-icon :icon="['fas', 'language']" class="icon-lang" /> -->

                <div id="hamburguerAnimation" @click="animateHamburger()">
                    <div>
                        <div class="t1 boxHamburguer"></div>
                        <div class="t2 boxHamburguer"></div>
                        <div class="t3 boxHamburguer"></div>
                    </div>
                </div>

            </button>
        </div>

        <ul class="nav flex-column foiClicado" id="navList">
            <li class="nav-item">
                <a class="nav-link" href="#Home">
                    <span>{{ listNav[0] }}</span>
                    <font-awesome-icon :icon="['fas', 'home']" />
                </a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#About">
                    <span>{{ listNav[1] }}</span>
                    <font-awesome-icon :icon="['fas', 'book-reader']" />
                </a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#Work">
                    <span>{{ listNav[2] }}</span>
                    <font-awesome-icon :icon="['fas', 'code']" />
                </a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#Contact">
                    <span>{{ listNav[3] }}</span>
                    <font-awesome-icon :icon="['fas', 'envelope']" />
                </a>
            </li>
        </ul>

        <div class="d-flex flex-column justify-content-between socialName" id="social-network">
            <a :href="github" target="_blank">
                <span>{{ listNav[4] }}</span>
                <font-awesome-icon :icon="['fab', 'github-square']" />
            </a>
            <a :href="linkedin" target="_blank">
                <span>{{ listNav[5] }}</span>
                <font-awesome-icon :icon="['fab', 'linkedin']" />
            </a>
        </div>
    </nav>
</template>

<script>
export default {
    name: 'NavBar',
    props: {
        linkedin: String,
        github: String,
        listNav: Array
    },

    methods: {
        animateHamburger() {
            document.getElementById("hamburguerAnimation").classList.toggle("hamburguerAnimated");
            document.getElementById("navList").classList.toggle("foiClicado");
            document.getElementById("social-network").classList.toggle("socialName");
            document.getElementById("navbar").classList.toggle("expandNav");
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

    nav {
        max-width: 70px;
        width: 100%;
        min-height: 100%;
        height: 100%;
        background-color: $color3;

        .dropdown {
            button {
                border: 0;
                width: 100%;
                height: 55px;
                color: $color4;
                background-color: $color2;
                font-size: 1.2em;

                .icon-lang {
                    font-size: 1.35em;
                }

                &::after {
                    color: $color5;
                }


                // hamburguer animation
                #hamburguerAnimation {
                    display: flex;
                    width: 100%;
                    height: 100%;
                    justify-content: center;
                    align-items: center;
                    transition: all .5s;

                    .boxHamburguer {
                        border: 2px solid;
                        margin: 4px auto;
                        width: 30px;
                        position: relative;
                    }
                    &.hamburguerAnimated {
                        .t1 {
                            transform: rotate(-45deg);
                            top: 8px;
                        }
                        .t2 {
                            transform: rotate(45deg);
                        }
                        .t3 {
                            transform: rotate(-45deg);
                            bottom: 8px;
                        }
                    }

                    &:hover {
                        color: $color3;
                    }
                }

                
            }
        }

        #navList {
            li {
                a {
                    font-size: 1.2em;
                    width: 80%;
                    margin: 1px auto;
                    padding: 10px;
                    border-radius: 4px;
                    color: $color1;
                    display: flex;
                    align-items: center;
                    justify-content: space-between;

                    span {
                        position: relative;
                        transition: all 0s;
                    }
                    
                    &:hover, &:active {
                        background-color: $color5;
                        color: $color2;
                    }
                }

                .active {
                    background-color: $color5;
                    color: $color2;
                }
            }

            &.foiClicado {
                li {
                    a {
                        justify-content: center;

                        span {
                            position: absolute;
                            z-index: -999999;
                            color: $color3;
                        }
                    }
                }
            }
        }

        #social-network {
            margin-bottom: 10px;
            a {
                font-size: 1.6em;
                color: $color1;
                margin: 2px auto;
                display: flex;
                text-decoration: none;
                justify-content: space-between;
                width: 100%;
                max-width: 150px;
                
                span {
                    font-size: .7em;
                    padding: 0 5px;
                }

                &:hover {
                    color: $color2;
                }

                @media only screen and (max-width: 768px) {
                    font-size: 1.6em;
                }
            }

            &.socialName {
                a {
                    justify-content: center;
                    span {
                        display: none;
                    }
                }
            }
        }

        @media only screen and (max-width: 768px) {
            max-width: 65px;

            &#navbar.expandNav {
                max-width: 300px;
            }
        }

        &#navbar.expandNav {
            max-width: 300px;
        }
    }
</style>