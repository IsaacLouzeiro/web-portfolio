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
            <NavBar :linkedin="linkedin" :github="github" :codepen="codepen" :listNav="listNav" /><!-- // menu navegação -->

            <!-- conteudo principal -->
            <main class="w-100" id="mainContent">
                <HomeSection :welcome="welcome" :subtitleSection="subtitleSectionHome" :btnWhoIam="btnWhoIam" :btnProjects="btnProjects" :btnContact="btnContact" :myName="myName" :profession="profession" :textWebResume="textWebResume" :btnWebResume="btnWebResume" :linkLogo="linkLogoWhite" :scrollDown="scrollDown" />
            
                <AboutSection :scrollDown="scrollDown" :titleSection="titleSectionAbout" :aboutText="aboutText" :moreDetails="moreDetails" :btnWebResume="btnWebResume" :titleSkills="titleSkills" :hardSkill="hardSkill" :softSkill="softSkill" :boxSkill="boxSkill" :boxSoftSkill="boxSoftSkill" :github="github" :linkedin="linkedin" :codepen="codepen" :youtube="youtube" />
            
                <WorkSection :titleSection="titleSectionWork" :btnFreela="btnFreela" :btnPersonal="btnPersonal" :seeMore="seeMore" :projFreela="projFreela" :projPersonal="projPersonal" :linkWebsite="linkWebsite" :about="about" :technology="technology" />
            
                <ContactSection :titleSection="titleSectionContact" :subtitleSection="subtitleSectionContact" :titleMaps="titleMaps" :email="email" :linkedinLink="linkedinLink" :linkedin="linkedin" :localization="localization" :linkMap="linkMap" />

                <footer>
                    <span>© 2022 | Isaac Louzeiro</span>
                </footer>
            </main>
            <!-- // conteudo principal -->
        </section>
        <!-- // site funcional -->
    </div>
</template>

<script>
// @ is an alias to /src
import EmManutencao from '@/components/EmManutencao.vue'
import CustomCursor from '@/components/CustomCursor.vue';
import NavBar from '@/components/NavBar.vue'
import HomeSection from '@/components/HomeSection.vue'
import AboutSection from '@/components/AboutSection.vue'
import WorkSection from '@/components/WorkSection.vue';
import ContactSection from '../components/ContactSection.vue';

export default {
    name: 'Home',
    data() {
        return {
            // manutencao
            manut: 0,

            // linkedin e github link
            linkedin: "https://www.linkedin.com/in/isaac-louzeiro/",
            github: "https://github.com/IsaacLouzeiro",

            // NavBar.vue
            listNav: [ 
                "Home", 
                "About", 
                "Work", 
                "Contact", 
                "Github", 
                "Linkedin",
                "Codepen"
            ],

            // HomeSection.vue
            welcome: "Welcome to my website.",
            subtitleSectionHome: "Recently my passion is creating websites. I'm very curious and constantly searching for new things to learn.",
            btnWhoIam: "Who I'am?",
            btnProjects: "Projects",
            btnContact: "Contact",
            myName: "Isaac Louzeiro",
            profession: "Front-End Web Developer",
            textWebResume: "My Website Resume is on the link below",
            btnWebResume: "Web Resume",
            linkLogo: require('../assets/img/logo-isaac-louzeiro-tiny.png'),
            linkLogoWhite: require('../assets/img/logo-isaac-louzeiro-tiny-white.png'),
            scrollDown: "scroll down",

            // AboutSection.vue
            titleSectionAbout: "About me",
            aboutText: [
                "Hi! My name is Isaac, I'm passionate about Web Development, especially the Front-End area.", 
                
                'I like to learn about this subject, and show my skills in this area, putting it on my Github, Codepen, and Web Portfolio.', 
                
                'I am a very curious person, who likes to learn and expand my knowledge. Every day I try to improve my skills so that I can grow professionally.'
                ],

            codepen: 'https://codepen.io/isaaclouzeiro/',
            youtube: 'https://www.youtube.com/c/isaaclouzeirodev',

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
                    name: 'SCSS'
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
                    linkImg: require('../assets/img/logo-mysql.webp'),
                    name: 'MySQL'
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


            // WorkSection.vue
            titleSectionWork: "My Work",
            btnFreela: "Job Freelance",
            btnPersonal: "Relevant Projects",
            seeMore: "See More",
            projFreela: [
                {
                    id: 1,
                    alt: "Image Alivisual",
                    nome: "Alivisual",
                    img: require('../assets/img/alivisual.webp'),
                    description: 'The website was made for "Alivisual", a producer of audiovisual & photography from São Paulo.',
                    link: 'https://www.alivisual.com.br/',
                    repo: '',
                    technologies: '[ HTML5 ] [ SCSS ] [ Bootstrap ] [ JavaScript ] [ PHP ]'
                },
                {
                    id: 2,
                    alt: "Image Leandro Louzeiro Portfolio",
                    nome: "Leandro Louzeiro Portfolio",
                    img: require('../assets/img/leandrolouzeiro.webp'),
                    description: 'Photograpy portfolio developed for the photographer Leandro Louzeiro.',
                    link: 'https://leandrolouzeiro.com.br/',
                    repo: 'https://github.com/IsaacLouzeiro/website-portfolio-fotografia2',
                    technologies: '[ HTML5 ] [ SCSS ] [ Bootstrap ] [ Vue Js ]'

                }
            ],
            projPersonal: [
                {
                    id: 0,
                    alt: "Image Open Spotify Clone",
                    nome: "Open Spotify Clone",
                    img: require('../assets/img/spotifyclone.webp'),
                    description: 'Spotify Web Audio Player in Vue Js, created to practice my abilities.',
                    link: 'https://spotify-copia.netlify.app/',
                    repo: 'https://github.com/IsaacLouzeiro/spotify-vue-clone',
                    technologies: '[ HTML5 ] [ SCSS ] [ Bootstrap ] [ Vue Js ]'
                },
                {
                    id: 0.1,
                    alt: "Image My Website Portfolio Website",
                    nome: "My Website Portfolio",
                    img: require('../assets/img/webportfolio.webp'),
                    description: 'My website portfolio, for the purpose of promote my work as a Front-end Developer. Version 2.0.',
                    link: 'https://isaaclouzeiro.dev.br/',
                    repo: 'https://github.com/IsaacLouzeiro/web-portfolio',
                    technologies: '[ HTML5 ] [ SCSS ] [ Bootstrap ] [ Vue Js ]'
                },
                {
                    id: 1.1,
                    alt: "Image Web Design Gallery Website",
                    nome: "Web Design Art Gallery",
                    img: require('../assets/img/webdesigngallery.webp'),
                    description: 'Showing my projects of web design, UI/UX and CSS arts, mostly of my codepen.',
                    link: 'https://webdesigngallery.netlify.app/',
                    repo: 'https://github.com/IsaacLouzeiro/webdesign-gallery',
                    technologies: '[ HTML5 ] [ SCSS ] [ Vue Js ]'
                },
                {
                    id: 2.1,
                    alt: "Image Website Resume",
                    nome: "My Website Resume",
                    img: require('../assets/img/resumewebsite.webp'),
                    description: 'Web resume, a relaxed way of show my professional side.',
                    link: 'https://isaac-resume.firebaseapp.com/',
                    repo: 'https://github.com/IsaacLouzeiro/resume',
                    technologies: '[ HTML5 ] [ SCSS ] [ Bootstrap ] [ Vue Js ]'
                },
                {
                    id: 3.1,
                    alt: "Economie Demoday website",
                    nome: "Economie Demoday Project",
                    img: require('../assets/img/economie.webp'),
                    description: 'Website focused on helping young and adult people to organize financially, in a friendly way. Demoday work project of the Proa Institute 4.0 in Web Java Programming in 2021.',
                    link: 'https://economie-dinie.github.io/economie/resumo.html',
                    repo: 'https://github.com/IsaacLouzeiro/economie',
                    technologies: '[ HTML5 ] [ CSS3 ] [ JavaScript ]'
                },
                {
                    id: 4.1,
                    alt: "Image Final Paper System",
                    nome: "Final Paper System Petshop",
                    img: require('../assets/img/petshopenterprize.webp'),
                    description: 'Pet Shop web system, for a fictitious enterprise, focused on sale of products for pets, and the register of pets to the grooming service, in addition to the institutional website. Final Paper project of the course of Systems Development at ETEC Professor Basilides de Godoy.',
                    link: '',
                    repo: 'https://github.com/IsaacLouzeiro/petshop-tcc',
                    technologies: '[ HTML5 ] [ CSS3 ] [ Bootstrap ] [ JavaScript ] [ AspNet ] [ MySQL ]'
                },
                {
                    id: 5.1,
                    alt: "Image Institutional Website",
                    nome: "Institutional Website",
                    img: require('../assets/img/projetotcm.webp'),
                    description: 'This website was created by me, With the purpose of completing the first semester final exam at ETEC for Systems development course, and also to enhance my experience in the field.',
                    link: 'https://isaaclouzeiro.github.io/Site-institucional/',
                    repo: 'https://github.com/IsaacLouzeiro/Site-institucional',
                    technologies: '[ HTML5 ] [ CSS3 ] [ JavaScript ]'
                },
                {
                    id: 6.1,
                    alt: "image of website",
                    nome: "Museum of Modern Art",
                    img: require('../assets/img/mam.webp'),
                    description: 'Website created by me, based on the Museum of Modern Art of São Paulo. Website project have no connections with the museum itself.',
                    link: 'https://isaaclouzeiro.github.io/Museu-de-Arte-Moderna/',
                    repo: 'https://github.com/IsaacLouzeiro/Museu-de-Arte-Moderna',
                    technologies: '[ HTML5 ] [ CSS3 ] [ JavaScript ]',
                },
                {
                    id: 7.1,
                    alt: "Image Instagram Basic Display API",
                    nome: "Instagram Basic Display API",
                    img: require('../assets/img/apiinstagram.webp'),
                    description: 'The website was made with the intention of using the Instagram Basic Display API from Facebook Developer for study purposes.',
                    link: 'https://isaaclouzeiro.github.io/apiinstagram/',
                    repo: 'https://github.com/IsaacLouzeiro/apiinstagram',
                    technologies: '[ HTML5 ] [ SCSS ] [ Bootstrap ] [ JQuery ]'
                }
            ],
            linkWebsite: 'Visit website',
            about: 'About',
            technology: 'Technologies',


            // ContactSection.vue
            titleSectionContact: "Contact",
            subtitleSectionContact: "If you are interested in my work or need additional information, please, reach me out.",
            titleMaps: "Localization",
            email: "isaacelias1110@gmail.com",
            linkedinLink: "/in/isaac-louzeiro",
            localization: "São Paulo, SP | Brazil",
            linkMap: require('../assets/img/maps.webp')
        }
    },
    components: {
        EmManutencao,
        CustomCursor,
        NavBar,
        HomeSection,
        AboutSection,
        WorkSection,
        ContactSection
    },
    created() {
        var windowWidth = window.innerWidth;
        if(windowWidth < 768) {
            this.scrollDown = "swipe up"
        }

    },
    mounted() {
        if( /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent) ) {
            document.getElementById('mainContent').classList.add('scrollbar')
        }else {
            document.getElementById('mainContent').classList.remove('scrollbar')
        }

        // LANGUAGE

        const ptBr = () => {
            // NavBar.vue
            this.listNav = [ 
                "Início", 
                "Sobre", 
                "Projetos", 
                "Contato", 
                "Github", 
                "Linkedin",
                "Codepen"
            ],

            // HomeSection.vue
            this.welcome = "Bem vindo ao meu site.";
            this.subtitleSectionHome = "Recentemente minha paixão é criar sites. Eu sou uma pessoa curiosa, constantemente procurando coisas novas para aprender.",
            this.btnWhoIam = "Quem sou eu?",
            this.btnProjects = "Projetos",
            this.btnContact = "Contato",
            this.myName = "Isaac Louzeiro",
            this.profession = "Desenvolvedor Web Front-End",
            this.textWebResume = "Meu Currículo Web está no link a baixo",
            this.btnWebResume = "Currículo Web",''
            this.scrollDown = "Rolar à baixo",

            // AboutSection.vue
            this.titleSectionAbout = "Sobre mim",
            this.aboutText = [
                'Olá! Me chamo Isaac, sou apaixonado pela área de Desenvolvimento Web, principalmente na parte de Front-End. ', 
                
                'Gosto de aprender sobre o assunto, e principalmente mostrar na prática tudo o que sei nesta área, adicionando no meu Github, Codepen e Portfolio Web.', 
                
                'Sou uma pessoa bastante curiosa, que gosta de aprender e expandir meus conhecimentos. A cada dia tento melhorar minhas habilidades para que eu possa crescer profissionalmente.'
            ],
            this.moreDetails = "Para mais informações",
            this.titleSkills = "Habilidades",
            this.hardSkill = "Habilidades técnicas",
            this.softSkill = "Habilidades comportamentais",
            this.boxSoftSkill = ['Autodidata', 'Trabalho em equipe', 'Adaptável'],

            // WorkSection.vue
            this.titleSectionWork = "Meus projetos",
            this.btnFreela = "Freelances",
            this.btnPersonal = "Projetos relevantes",
            this.seeMore = "Veja Mais",
            this.linkWebsite = 'Visitar site',
            this.about = 'Sobre',
            this.technology = 'Tecnologias',

            // ContactSection.vue
            this.titleSectionContact = "Contato",
            this.subtitleSectionContact = "Se você estiver interessado no meu trabalho ou precisar de informações adicionais, por favor, entre em contato.",
            this.titleMaps = "Localização",
            this.localization = "São Paulo, SP | Brasil"
        }
        
        if(document.getElementById('enUsLang').classList.contains('selectedLang')) {
            ptBr
        }else {
            ptBr()
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

    * { cursor: none; &:hover { cursor: none; } }

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
        position: relative;

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

            &.scrollbar::-webkit-scrollbar {
                width: 0px;
            }
        }
    }

    footer {
        background-color: $color4;
        text-align: right;
        padding: 5px 10px;
        color: $color2;
    }
</style>
