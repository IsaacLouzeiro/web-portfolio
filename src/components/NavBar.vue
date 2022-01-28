<template>
    <nav class="d-flex flex-column justify-content-between">
        <div class="box-lang dropdown">
            <button class="dropdown-toggle" type="button" id="dropdownMenuButton1" data-bs-toggle="dropdown" aria-expanded="false">
                <font-awesome-icon :icon="['fas', 'language']" />
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
                font-size: 1.3em;

                &::after {
                    color: $color5;
                }
            }
            
            .dropdown-menu {
                background-color: $color5;
                min-width: 100px;
                border: 0;
                box-shadow: 1px 1px 5px rgba(117, 117, 117, 0.3);

                a {
                    color: $color1;

                    &:hover, &:focus {
                        opacity: .5;
                    }
                }

                .active {
                    background-color: $color1;
                    color: $color5;
                }
            }
        }

        .nav {
            li {
                a {
                    display: inline-block;
                    font-size: 1.3em;
                    width: 80%;
                    margin: 5px 0;
                    padding: 7px 10px;
                    border-radius: 8px;
                    color: $color1;

                    &:hover, &:active {
                        background-color: $color5;
                    }
                }
            }
        }

        .social-network {
            margin-bottom: 10px;
            a {
                display: inline-block;
                max-height: 35px;
                font-size: 1.8em;
                margin: 3px 0;
                color: $color1;

                &:hover {
                    opacity: .7;
                }
            }
        }

        @media only screen and (max-width: 768px) {
            max-width: 65px;
            font-size: .9em;
        }
    }
</style>