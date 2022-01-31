<template>
    <div class="home">
        <!-- cursor do mouse -->
        <custom-cursor
            :targets="['img', 'a', 'button', 'your-hover-class']"
            :circleColor="'#FF7A4F'"
            :circleColorHover="'#FF7A4F'"
            :dotColor="'#fff'"
            :dotColorHover="'lightgray'"
            :hoverSize="1.8"
            class="custom-cursor"
        ></custom-cursor>
        <!-- // cursor do mouse -->

        <!-- site em manutenção -->
        <div v-show="this.manut == 1" class="manutencao">
            <EmManutencao />
        </div>
        <!-- // site em manutenção -->

        <!-- site funcional -->
        <section v-show="this.manut == 0" class="principal d-flex">
            <NavBar /><!-- // menu navegação -->

            <!-- conteudo principal -->
            <main class="w-100" id="mainContent">
                <HomeSection :welcome="welcome" :subtitleSection="subtitleSectionHome" :btnWhoIam="btnWhoIam" :btnProjects="btnProjects" :btnContact="btnContact" :myName="myName" :profession="profession" :textWebResume="textWebResume" :btnWebResume="btnWebResume" :scrollDown="scrollDown" />
            
                <AboutSection :scrollDown="scrollDown" :titleSection="titleSectionAbout" :aboutText="aboutText" :moreDetails="moreDetails" :btnWebResume="btnWebResume" :titleSkills="titleSkills" :hardSkill="hardSkill" :softSkill="softSkill" :boxSkill="boxSkill" :boxSoftSkill="boxSoftSkill" />
            
                <WorkSection :titleSection="titleSectionWork" :btnFreela="btnFreela" :btnPersonal="btnPersonal" :seeMore="seeMore" :projFreela="projFreela" />
            </main>
            <!-- // conteudo principal -->
        </section>
        <!-- // site funcional -->
    </div>
</template>

<script>
// @ is an alias to /src
import EmManutencao from '@/components/EmManutencao.vue'
import NavBar from '@/components/NavBar.vue'
import HomeSection from '@/components/HomeSection.vue'
import AboutSection from '@/components/AboutSection.vue'
import WorkSection from '@/components/WorkSection.vue';
import CustomCursor from '@/components/CustomCursor.vue';

export default {
    name: 'Home',
    data() {
        return {
            // manutencao
            manut: 0,

            // HomeSection.vue
            welcome: "Welcome to my website.",
            subtitleSectionHome: "Recently my passion is creating websites. I'm very curious and constantly searching for new things to learn.",
            btnWhoIam: "Who I'am?",
            btnProjects: "Projects",
            btnContact: "Contact",
            myName: "Isaac Louzeiro",
            profession: "Front-end Developer",
            textWebResume: "My Website Resume is on the link below",
            btnWebResume: "Web Resume",
            scrollDown: "scroll down",
            // EM PORTUGUÊS
            // welcome: "Bem vindo ao meu site.",
            // subtitleSectionHome: "Recentemente minha paixão é criar sites. Eu sou uma pessoa curiosa, constantemente procurando coisas novas para aprender.",
            // btnWhoIam: "Quem sou eu?",
            // btnProjects: "Projetos",
            // btnContact: "Contato",
            // myName: "Isaac Louzeiro",
            // profession: "Desenvolvedor Front-end",
            // textWebResume: "Meu Site-Currículo está no link a baixo",
            // btnWebResume: "Currículo Web",
            // scrollDown: "Rolar à baixo"

            // AboutSection.vue
            titleSectionAbout: "About me",
            aboutText: [
                'I started the Systems Development course at ETEC Professor Basilides de Godoy in 2019, and finished it in 2020. I did my final paper project in a PetShop system in Asp.Net MVC, worked with the front-end of the application using HTML, CSS, JavaScript and Bootstrap, and in the backend in Asp.Net MVC.', 
                
                'I joined Instituto Proa in 2021, in the ProProfissão 4.0 course on Java Web programming, and I feel that I have learned a lot in the communicative and technical work part, in addition to it, I have concluded my final paper work project (Demoday) in Economics system for low-income for young people, working mainly on the front-end system with HTML, CSS and JavaScript.', 
                
                'I am a very curious person, who likes to learn and expand my knowledge. Every day I try to improve my skills so that I can grow professionally.'
                ],

            moreDetails: "For more details",
            titleSkills: "Skills",
            hardSkill: "Hard skills",
            softSkill: "Soft skills",
            boxSkill: [
                {
                    linkImg: require('../assets/img/logo-html5.webp'),
                    name: 'HTML'
                },
                {
                    linkImg: require('../assets/img/logo-css3.webp'),
                    name: 'CSS'
                },
                {
                    linkImg: require('../assets/img/logo-sass.webp'),
                    name: 'SASS'
                },
                {
                    linkImg: require('../assets/img/logo-javascript.webp'),
                    name: 'JavaScript'
                },
                {
                    linkImg: require('../assets/img/logo-vue.webp'),
                    name: 'Vue'
                },
                {
                    linkImg: require('../assets/img/logo-bootstrap.webp'),
                    name: 'Bootstrap'
                },
                {
                    linkImg: require('../assets/img/logo-xd.webp'),
                    name: 'Adobe XD'
                },
                {
                    linkImg: require('../assets/img/logo-photoshop.webp'),
                    name: 'Photoshop'
                },
                {
                    linkImg: require('../assets/img/logo-git.webp'),
                    name: 'Git'
                },
                {
                    linkImg: require('../assets/img/logo-github.webp'),
                    name: 'GitHub'
                }
            ],
            boxSoftSkill: ['Self-taught', 'Teamwork', 'Adaptability'],

            // EM PORTUGUÊS
            // titleSectionAbout: "Sobre mim",
            // aboutText: [
            //     'Comecei o curso de Desenvolvimento de Sistemas na ETEC Professor Basilídes de Godoy em 2019, e terminei em 2020. Fiz meu projeto de TCC de um sistema de PetShop em Asp.Net MVC, trabalhei com o front-end da aplicação utilizando HTML, CSS, JavaScript e  Bootstrap, e no back-end em Asp.Net MVC.', 
                
            //     'Entrei no Instituto Proa em 2021, no curso ProProfissão 4.0 de programação Java Web, e sinto que aprendi bastante na parte comunicativa e técnica de trabalho, além de concluir com o TCC (Demoday) de um sistema de Economia para jovens de baixa renda, trabalhando principalmente no front-end do sistema com HTML, CSS e JavaScript.', 
                
            //     'Sou uma pessoa bastante curiosa, que gosta de aprender e expandir meus conhecimentos. A cada dia tento melhorar minhas habilidades para que eu possa crescer profissionalmente.'
            // ],
            // moreDetails: "Para mais informações",
            // titleSkills: "Habilidades",
            // hardSkill: "Habilidades técnicas",
            // softSkill: "Habilidades comportamentais",
            // boxSoftSkill: ['Autodidata', 'Trabalho em equipe', 'Adaptável']

            // WorkSection.vue

            titleSectionWork: "My Work",
            btnFreela: "Job Freelance",
            btnPersonal: "Personal Projects",
            seeMore: "See More",
            projFreela: [
                {
                    id: 1,
                    alt: "Imagem Alivisual",
                    nome: "Alivisual",
                    img: require('../assets/img/alivisual.gif'),

                },
                {
                    id: 2,
                    alt: "Imagem Leandro Louzeiro Portfolio",
                    nome: "Leandro Louzeiro Portfolio",
                    img: require('../assets/img/leandroLouzeiro.gif'),

                }
            ]
        }
    },
    components: {
        EmManutencao,
        CustomCursor,
        NavBar,
        HomeSection,
        AboutSection,
        WorkSection
    },
    created() {
        var windowWidth = window.innerWidth;
        if(windowWidth < 768) {
            this.scrollDown = "swipe up"
        }
    },
    mounted() {
        if( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent) ) {
            document.getElementById('mainContent').style.overflow = "hidden"
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

    .custom-cursor {
        position: absolute;
        z-index: 100000000000000;
    }

    .home, .principal, body {
        height: 100%;
        background-color: $color3;
    }

    .manutencao {
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: $color5;
    }

    main {
        margin-left: 70px;
        overflow-y: auto;
        scroll-behavior: smooth;

        &::-webkit-scrollbar {
            width: 8px;
        }

        &::-webkit-scrollbar-track {
            background: $color2;
        }

        &::-webkit-scrollbar-thumb {
            background-color: $color3;
            border-radius: 20px;
            border: 2px solid $color2;
        }

        @media only screen and (max-width: 768px) {
            margin-left: 65px;

            // &::-webkit-scrollbar {
            //     width: 0px;
            // }
        }
    }

</style>
