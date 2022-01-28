<template>
    <nav class="d-flex flex-column justify-content-between">
        <div class="box-lang dropdown">
            <button class="dropdown-toggle" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
                <font-awesome-icon :icon="['fas', 'language']" class="icon-lang" />
            </button>
            <ul class="dropdown-menu" aria-labelledby="dropdownMenuButton1">
                <li><a class="dropdown-item" href="#">pt-br</a></li>
                <li><a class="dropdown-item active" href="#">en-us</a></li>
            </ul>
        </div>

        <ul class="nav flex-column list-group" id="list-example">
            <li class="nav-item">
                <a class="nav-link" href="#Home"><font-awesome-icon :icon="['fas', 'home']" /></a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#About"><font-awesome-icon :icon="['fas', 'book-reader']" /></a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#Work"><font-awesome-icon :icon="['fas', 'code']" /></a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#Contact"><font-awesome-icon :icon="['fas', 'envelope']" /></a>
            </li>
        </ul>

        <div class="social-network d-flex flex-column justify-content-between">
            <a href="https://github.com/IsaacLouzeiro" target="_blank"><font-awesome-icon :icon="['fab', 'github-square']" /></a>
            <a href="https://www.linkedin.com/in/isaac-louzeiro/" target="_blank"><font-awesome-icon :icon="['fab', 'linkedin']" /></a>
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

    nav {
        max-width: 70px;
        width: 100%;
        min-height: 100%;
        height: 100%;
        background-color: $color3;

        .box-lang {
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
            }
            
            .dropdown-menu {
                background-color: $color1;
                min-width: 100px;
                border: 0;
                box-shadow: 1px 1px 5px rgba(117, 117, 117, 0.3);

                a {
                    color: $color5;

                    &:hover, &:focus {
                        background-color: $color3
                    }
                }

                .active {
                    background-color: $color5;
                    color: $color2;
                }
            }
        }

        .nav {
            li {
                a {
                    display: inline-block;
                    font-size: 1.2em;
                    width: 80%;
                    margin: 1px 0;
                    padding: 7px 10px;
                    border-radius: 4px;
                    color: $color1;

                    &:hover, &:active {
                        background-color: $color5;
                        color: $color2;
                    }
                }
            }
        }

        .social-network {
            margin-bottom: 10px;
            a {
                font-size: 1.6em;
                color: $color1;
                margin: 2px auto;
                display: flex;

                &:hover {
                    color: $color2;
                }

                @media only screen and (max-width: 768px) {
                    font-size: 1.6em;
                }
            }
        }

        @media only screen and (max-width: 768px) {
            max-width: 65px;
        }
    }
</style>