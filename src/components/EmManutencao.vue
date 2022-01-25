<template>
    <section>
        <h1>A criar...</h1>
        <h2>Codando um portifólio diferente do que você viu por ai!</h2>
        <h3>Novidades em breve</h3>
        <a href="https://github.com/IsaacLouzeiro/">Meu Github</a>        
    </section>
</template>

<script>
export default {
    name: 'EmManutencao',
    data() {
        return {
            
        }
    },
    props: {
        situacao: Boolean
    }
}
</script>

<style lang="scss" scoped>
    h1, h2, h3 {
        margin: 5px 0;
    }
    
    h1 {
        font-size: 2em;
        color: #2d3436;
    }

    h2 {
        color: #636e72;
    }

    h3 {
        color: #34495e;
        margin-top: 1em;
        margin-bottom: 0;
    }

    a {
        display: inline-block;
        padding: 10px 16px;
        font-size: 1em;
        text-decoration: none;
        color: #fff;
        background-color: #16a085;
        border-radius: 5px;
        margin-top: 10px;

        &:hover {
            background-color: #1abc9c;
        }
    }
</style>