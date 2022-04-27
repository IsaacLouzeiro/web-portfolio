<template>
    <div id="worktree">
        <div id="navbar">
            <div id="language" @click="changeLang()">
                <span id="enus" class="selection">EN-US</span>
                <span id="ptbr">PT-BR</span>
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

        
    </div>
</template>

<script>
export default {
    name: "worktree",
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
                }
            ],
            
        }
    },

    methods: {
        changeLang() {
            document.getElementById("enus").classList.toggle("selection");
            document.getElementById("ptbr").classList.toggle("selection");
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
        cursor: default !important;
        -webkit-touch-callout: none; /* iOS Safari */
        -webkit-user-select: none; /* Safari */
        -khtml-user-select: none; /* Konqueror HTML */
        -moz-user-select: none; /* Old versions of Firefox */
        -ms-user-select: none; /* Internet Explorer/Edge */
        user-select: none;
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
            }

            #enus.selection, #ptbr.selection {
                cursor: pointer !important;
                display: flex;
                z-index: 1;
                background-color: $color1;
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
</style>