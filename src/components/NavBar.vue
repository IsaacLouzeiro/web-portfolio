<template>
    <nav class="d-flex flex-column justify-content-between fixed-top" id="navbar">
        <!-- menu button -->
        <div class="dropdown">
            <button class="" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">

                <div id="hamburguerAnimation" @click="animateHamburger()">
                    <div>
                        <div class="t1 boxHamburguer"></div>
                        <div class="t2 boxHamburguer"></div>
                        <div class="t3 boxHamburguer"></div>
                    </div>
                </div>

            </button>
        </div>

        <!-- language -->
        <div class="d-flex justify-content-around" id="lang-box">
            <button class="langBtn selectedLang" id="enUsLang" @click="langBtn(this, 'en')">EN</button>

            <button class="langBtn" id="ptBrLang" @click="langBtn(this, 'pt')">PT</button>
        </div>

        <!-- main list -->
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

        <!-- list social network -->
        <div class="d-flex flex-column justify-content-between socialName" id="social-network">
            <a :href="codepen" target="_blank">
                <span>{{ listNav[6] }}</span>
                <p class="logoCodepen"><font-awesome-icon :icon="['fab', 'codepen']" /></p>
            </a>
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
        codepen: String,
        listNav: Array
    },

    mounted() {
        // SETTING BUTTON LANGUAGE
        const memLangPt = localStorage.getItem('pt');

        const memLangEn = localStorage.getItem('en');

        document.getElementById("enUsLang").classList.add("selectedLang");
        // if has the lang pt on localStorage
        if (memLangPt) {
            document.getElementById("ptBrLang").classList.add("selectedLang");
            document.getElementById("enUsLang").classList.remove("selectedLang");
            // ptBr();
        }

        // if has the lang en on localStorage
        if (memLangEn) {
            document.getElementById("enUsLang").classList.add("selectedLang");
            document.getElementById("ptBrLang").classList.remove("selectedLang");
        }
    },

    methods: {
        animateHamburger() {
            document.getElementById("hamburguerAnimation").classList.toggle("hamburguerAnimated");
            document.getElementById("navList").classList.toggle("foiClicado");
            document.getElementById("social-network").classList.toggle("socialName");
            document.getElementById("navbar").classList.toggle("expandNav");
        },

        // LANGUAGE LOCAL STORAGE
        langBtn(btn, lang) {
            location.reload();
            switch (lang) {
                case 'pt':
                    // remove the lang on localStorage
                    localStorage.removeItem('en');
                    // insert active class
                    document.getElementById('ptBrLang').classList.add("selectedLang");
                    // ptBr();

                    // if has the classe active
                    if (document.getElementById('ptBrLang').classList.contains('selectedLang')) {
                        // add the lang on localStorage
                        localStorage.setItem('pt', true)
                        // ptBr();
                        return
                    }
                    // else remove
                    localStorage.removeItem('pt');
                    break;

                case 'en':
                    // remove the lang on localStorage
                    localStorage.removeItem('pt');
                    // insert active class
                    document.getElementById('enUsLang').classList.add("selectedLang");

                    // if has the classe active
                    if (document.getElementById('enUsLang').classList.contains('selectedLang')) {
                        // add the lang on localStorage
                        localStorage.setItem('en', true)
                        return
                    }
                    // else remove
                    localStorage.removeItem('en');
                    break;
            
                default:
                    break;
            }
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
        z-index: 100000000;

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

        #lang-box {
            width: 100%;
            max-width: 200px;
            margin: 1em auto auto auto;

            .langBtn {
                border: none;
                font-size: .8em;
                width: 46%;
                height: 30px;
                background-color: $color1;
                color: $color3;
                font-weight: bold;
                border-radius: 5px;
                border: 3px solid $color3;
                
                &.selectedLang {
                    border: 3px solid $color5;
                }
            }
        }

        #navList {
            margin-top: auto;
            margin-bottom: auto;
            li {
                a {
                    font-size: 1.2em;
                    width: 80%;
                    margin: 3px auto;
                    padding: 10px;
                    border-radius: 4px;
                    color: $color1;
                    display: flex;
                    align-items: center;
                    justify-content: space-around;
                    background-color: rgba($color5, .3);

                    span {
                        position: relative;
                        transition: all 0s;
                    }
                    
                    &:hover, &:active {
                        background-color: $color1;
                        color: $color5;
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
                            left: -999px;
                            color: $color3;
                        }
                    }
                }
            }
        }

        #social-network {
            margin-top: auto;
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

                .logoCodepen {
                    margin: 0;
                    width: 25px;
                    height: 25px;
                    color: $color3;
                    background-color: $color1;
                    border-radius: 3px;
                    font-size: .7em;
                }

                &:hover {
                    color: $color2;

                    .logoCodepen { background-color: $color2; }
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