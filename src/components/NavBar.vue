<template>
    <nav>
        <div class="box-lang dropdown">
            <button class="dropdown-toggle" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
                Dropdown button
            </button>
            <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
                <li><a class="dropdown-item" href="#">Action</a></li>
                <li><a class="dropdown-item" href="#">Another action</a></li>
            </ul>
        </div>

        <ul class="nav flex-column list-group" id="list-example">
            <li class="nav-item">
                <a class="nav-link" href="#Home">Home</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#About">About</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#Work">Work</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#Contact">Contact</a>
            </li>
        </ul>

        <div class="social-network">
            <a href="https://github.com/IsaacLouzeiro"></a>
            <a href="https://www.linkedin.com/in/isaac-louzeiro/"></a>
        </div>
    </nav>
</template>

<script>
export default {
    name: 'NavBar'
}
</script>

<style lang="scss" scoped>
    @import '../assets/scss/colors.scss';


</style>