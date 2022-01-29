<template>
  <div class="home">
    <div v-show="this.manut == 1" class="manutencao">
        <EmManutencao />
    </div>

    <!-- site funcional -->
    <section v-show="this.manut == 0" class="principal d-flex">
        <!-- menu navegação -->
        <NavBar />

        <!-- conteudo principal -->
        <main class="w-100">
            <HomeSection :welcome="welcome" :subtitleSection="subtitleSectionHome" :btnWhoIam="btnWhoIam" :btnProjects="btnProjects" :btnContact="btnContact" :myName="myName" :profession="profession" :textWebResume="textWebResume" :btnWebResume="btnWebResume" :scrollDown="scrollDown" />
        
            <AboutSection />
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
            scrollDown: "scroll down"
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
        }
    },
    components: {
        EmManutencao,
        NavBar,
        HomeSection,
        AboutSection
    },
    created() {
        var windowWidth = window.innerWidth;
        if(windowWidth < 768) {
            this.scrollDown = "swipe up"
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';

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

            &::-webkit-scrollbar {
                width: 0px;
            }
        }
    }

</style>
