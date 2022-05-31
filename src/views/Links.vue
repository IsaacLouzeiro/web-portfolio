<template>
    <div id="worktree">
        <div id="navbar">
            <div id="language" >
                <span id="enus" @click="changeLang('en')">EN-US</span>
                <span id="ptbr" @click="changeLang('pt')">PT-BR</span>
            </div>
            
            <button class="onOff" @click="toggleBtn()">
                <div id="btOn"></div>
            </button>
        </div>

        <p>{{ initialPhrase }}</p>
        
        <img :src="img" alt="Isaac Louzeiro Image">

        <h1>{{ myName }}</h1>

        <small class="myPhrase">{{ myPhrase }}</small>

        <p style="margin: 8px 0;">{{ skill }}</p>

        <ul id="listSkill">
            <li v-for="item in skList" :key="item.skList">{{ item.name }}</li>
        </ul>

        <p style="margin: 8px 0;">{{ myCodes }}</p>

        <ul id="listWork">
            <li v-for="item in myCodesList" :key="item.myCodesList">
                <a :href="item.link" target="_blank">
                    <svg viewBox="0 0 32.002 22.746" v-if="item.name == 'Youtube'">
                        <path :d="item.svg" fill="#f00"></path>
                    </svg>
                    <svg viewBox="0 0 128 128" v-else-if="item.name != 'Youtube'">
                        <path :d="item.svg" fill="#000"></path>
                    </svg>
          
                    <p>{{ item.name }}</p>
                </a>
            </li>
        </ul>

        <p style="margin: 8px 0;">{{ myWorkingLife }}</p>

        <ul id="listWork">
            <li v-for="item in myWorkingLifeList" :key="item.myWorkingLifeList">
                <a :href="item.link" target="_blank">
                    <img :src="item.img" :alt="item.name">
                    
                    <!-- PAREI AQUI -->
          
                    <p>{{ item.name }}</p>
                </a>
            </li>
        </ul>
        
    </div>
</template>

<script>
export default {
    name: "Links",
    data() {
        return {
            img: require('../assets/img/img-isaac.jpeg'),
            myName: "Isaac Louzeiro",
            // initialPhrase: "Você está querendo saber sobre meu trabalho de maneira breve e fácil?",
            initialPhrase: "Are you waiting to know about my work in a quickly way?",
            myPhrase: "''Recently my passion is creating websites. I'm very curious and constantly searching for new things to learn!''",
            skill: "Main Skills",
            skList: [
                {
                    name: "HTML5"
                },
                {
                    name: "CSS3"
                },
                {
                    name: "JavaScript"
                },
                {
                    name: "VueJS"
                },
                {
                    name: "SCSS"
                },
                {
                    name: "Bootstrap"
                },
                {
                    name: "Wordpress"
                },
                {
                    name: "Adobe XD"
                },
                {
                    name: "UX"
                },
                {
                    name: "SEO"
                }
            ],
            myCodes: "Where to know about my codes?",
            myCodesList: [
                {
                    name: "Codepen",
                    link: "https://codepen.io/isaaclouzeiro/",
                    svg: "M125.571 39.926l-58.5-39c-1.997-1.23-4.128-1.24-6.142 0l-58.5 39C.929 40.926 0 42.712 0 44.497v39c0 1.786.929 3.572 2.429 4.571l58.5 39.006c1.996 1.229 4.128 1.24 6.142 0l58.5-39.006c1.5-.999 2.429-2.785 2.429-4.57v-39c0-1.786-.929-3.572-2.429-4.572zm-56.07-24.144l43.07 28.715-19.214 12.858L69.5 41.425V15.784zm-11.001 0v25.644L34.642 57.354 15.428 44.498 58.5 15.782zm-47.5 39l13.786 9.215L11 73.212v-18.43zm47.5 57.43L15.428 83.497 34.642 70.64 58.5 86.569v25.643zM64 76.997l-19.428-13 19.428-13 19.428 13-19.428 13zm5.5 35.215V86.569L93.357 70.64l19.214 12.857-43.07 28.715zm47.5-39l-13.786-9.215L117 54.783v18.429z",
                },
                {
                    name: "Github",
                    link: "https://github.com/IsaacLouzeiro",
                    svg: "M64 5.103c-33.347 0-60.388 27.035-60.388 60.388 0 26.682 17.303 49.317 41.297 57.303 3.017.56 4.125-1.31 4.125-2.905 0-1.44-.056-6.197-.082-11.243-16.8 3.653-20.345-7.125-20.345-7.125-2.747-6.98-6.705-8.836-6.705-8.836-5.48-3.748.413-3.67.413-3.67 6.063.425 9.257 6.223 9.257 6.223 5.386 9.23 14.127 6.562 17.573 5.02.542-3.903 2.107-6.568 3.834-8.076-13.413-1.525-27.514-6.704-27.514-29.843 0-6.593 2.36-11.98 6.223-16.21-.628-1.52-2.695-7.662.584-15.98 0 0 5.07-1.623 16.61 6.19C53.7 35 58.867 34.327 64 34.304c5.13.023 10.3.694 15.127 2.033 11.526-7.813 16.59-6.19 16.59-6.19 3.287 8.317 1.22 14.46.593 15.98 3.872 4.23 6.215 9.617 6.215 16.21 0 23.194-14.127 28.3-27.574 29.796 2.167 1.874 4.097 5.55 4.097 11.183 0 8.08-.07 14.583-.07 16.572 0 1.607 1.088 3.49 4.148 2.897 23.98-7.994 41.263-30.622 41.263-57.294C124.388 32.14 97.35 5.104 64 5.104z"
                },
                {
                    name: "Youtube",
                    link: "https://www.youtube.com/c/isaaclouzeirodev",
                    svg: "M27.671,0.419c-7.286-0.49-15.924-0.624-23.344,0C2.023,0.677,0.445,3.481,0.273,5.611c-0.364,4.474-0.364,7.02,0,11.494c0.174,2.13,1.712,4.95,4.056,5.246c7.508,0.492,16.102,0.56,23.344,0c2.268-0.394,3.882-3.116,4.056-5.246c0.364-4.474,0.364-7.298,0-11.774C31.553,3.201,30.281,0.515,27.671,0.419z M11.999,17.033V5.563l10,5.736L11.999,17.033z"
                }
            ],
            myWorkingLife: "Where to know about my professional side?",
            myWorkingLifeList: [
                {
                    name: "Linkedin",
                    link: "https://www.linkedin.com/in/isaac-louzeiro/"
                },
                {
                    name: "Portfolio",
                    link: "https://isaaclouzeiro.dev.br/"
                },
                {
                    name: "Resume",
                    link: "https://isaac-resume.firebaseapp.com/"
                }
            ]
            
        }
    },

    mounted() {
        // SETTING BUTTON LANGUAGE
        const memLangPt = localStorage.getItem('pt');

        const memLangEn = localStorage.getItem('en');

        document.getElementById("enus").classList.add("selection");
        // if has the lang pt on localStorage
        if (memLangPt) {
            document.getElementById("ptbr").classList.add("selection");
            document.getElementById("enus").classList.remove("selection");
            // ptBr();
        }

        // if has the lang en on localStorage
        if (memLangEn) {
            document.getElementById("enus").classList.add("selection");
            document.getElementById("ptbr").classList.remove("selection");
        }

        // LANGUAGE

        const ptBr = () => {
            this.initialPhrase = "Você quer saber sobre meu trabalho de maneira rápida?",
            this.myPhrase = "''Recentemente minha paixão é criar sites. Eu sou uma pessoa curiosa, constantemente procurando coisas novas para aprender.''",
            this.skill = "Habilidades Principais"
        }
        
        if(document.getElementById('ptbr').classList.contains('selection')) {
            ptBr()
        }else {
            ptBr
        }
    },

    methods: {

        // LANGUAGE LOCAL STORAGE
        changeLang(lang) {
            location.reload();

            switch (lang) {
                case 'pt':
                    // remove the lang on localStorage
                    localStorage.removeItem('en');
                    // insert active class
                    document.getElementById('ptbr').classList.add("selection");
                    // ptBr();

                    // if has the classe active
                    if (document.getElementById('ptbr').classList.contains('selection')) {
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
                    document.getElementById('enus').classList.add("selection");

                    // if has the classe active
                    if (document.getElementById('enus').classList.contains('selection')) {
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
        },
        
        toggleBtn() {
            document.getElementById('worktree').classList.toggle('btOff');
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

    * {
        cursor: default;
    }

    #worktree {
        width: 100%;
        height: 100%;
        padding: 0 10px;
        background-color: $color5;

        color: $color1;

        &.btOff {
            background-color: $color1;
            color: $color5;

            img {
                border-color: $color4;
            }

            .myPhrase {
                color: $color4;
            }

            #language {
                #enus, #ptbr {
                    color: $color1;
                    background-color: $color5;
                }
                #enus.selection, #ptbr.selection {
                    background-color: $color5;
                }
            }
            .onOff {
                background-color: $color5;
                
                #btOn {
                    background-color: $color1;
                    border-color: $color5;
                    left: 0; 
                    right: auto;
                }
            }

            #listSkill {
                li {
                    background-color: $color5;
                    color: $color1;
                }
            }

            #listWork {
                li {
                    a {
                        color: $color5;
                    }
                }
            }
        }
    }

    img {
        width: 120px;
        height: 120px;
        border-radius: 60px;
        border: 5px solid $color3;
    }

    h1 {
        font-size: 1.5em;
        margin-top: 10px;
        margin-bottom: 0;
    }

    .myPhrase {
        display: block;
        font-style: italic;
        padding-top: 5px;
        color: $color3;
    }

    #navbar {
        max-width: 800px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 60px;
        padding: 0 5px;
        margin: auto;
        margin-bottom: 10px;

        #language {
            display: inline-block;
            padding: 5px 8px;
            border-radius: 5px;
            cursor: pointer !important;
            position: relative;
            width: 75px;
            height: 35px;


            #enus, #ptbr {
                border-radius: 5px;
                cursor: pointer !important;
                position: absolute;
                left: 0;
                right: 0;
                top: 0;
                bottom: 0;
                display: flex;
                align-items: center;
                justify-content: center;
                z-index: 0;
                font-weight: 900;
                transition: .2s all;
                color: $color5;
                background-color: $color1;
            }

            #enus.selection, #ptbr.selection {
                cursor: pointer !important;
                display: none;
                z-index: 1;
            }
        }

        .onOff {
            width: 50px;
            min-height: 20px;
            border-radius: 15px;
            background-color: $color1;
            position: relative;
            cursor: pointer;
            border: none;
            cursor: pointer!important;
            
            #btOn {
                width: 23px;
                height: 23px;
                background-color: $color5;
                border-radius: 15px;
                border: 3px solid $color1;
                position: absolute;
                top: -2px;
                right: 0;
                cursor: pointer!important;
            }
        }
    }

    #listSkill {
        list-style-type: none;
        display: flex;
        flex-wrap: wrap;
        padding: 0;
        justify-content: center;
        li {
            display: inline-block;
            padding: 3px 8px;
            margin: 3px 2px;
            border-radius: 3px;
            border: 1px solid;
            background-color: $color1;
            color: $color5;
        }
    }

    #listWork {
        list-style-type: none;
        display: flex;
        flex-wrap: wrap;
        padding: 0;
        justify-content: center;
        align-items: center;
        
        li {
            display: inline-block;
            padding: 3px 8px;
            margin: 3px 2px;
            border-radius: 3px;
            color: $color5;

            a {
                text-decoration: none;
                color: $color1;
                cursor: pointer!important;

                p {
                    cursor: pointer;
                }
            }
        }
    }
    svg {
        width: 35px;
        height: 35px;
        display: inline-block;
        cursor: pointer!important;

        path {
            cursor: pointer;
        }
    }
</style>