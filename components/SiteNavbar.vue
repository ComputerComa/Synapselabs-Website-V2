<template>
    <header class="header">
        <nav class="navbar">
            <div class="logo">
                <img src="/img/android-chrome-192x192.png"></img>
            </div>
            <div id="brand-text">
                <h1>Synapselabs Tech Solutions</h1>
                <h5>Tech Done Right</h5>
            </div>
            <div class="menu-bar">
                <ul class="nav-links">
                <li><NuxtLink  to="/" class="router-link">Home</NuxtLink ></li>
                    
                <li>
                    <NuxtLink to="/contact" class="router-link">Contact</NuxtLink ></li>
                <li>
                    <NuxtLink  to="/reviews" class="router-link">Reviews</NuxtLink ></li>
            </ul>
            </div>


        </nav>
    </header>
</template>

<script>
export default {
    data() {
        return {
            isMenuOpen: false,
        };
    },
    methods: {
        toggleMenu() {
            this.isMenuOpen = !this.isMenuOpen;
        },
    },
};
</script>

<style scoped>
#brand-text {
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-left: 1rem;
    color: red;
    text-align: center;
}
img {
    max-width: 100%;
    height: 64px;
}
.header {
    background-color: #333;
    color: #fff;
    padding: 1rem 2rem;
}

.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;

}

.logo a {
    color: #fff;
    text-decoration: none;
    font-size: 1.5rem;
    font-weight: bold;

}

.nav-links {
    list-style: none;
    display: flex;
    gap: 1.5rem;
    align-items: center;
    text-decoration: none;
    
}

.nav-links a:visited{
    text-decoration: none;
    color: #ffffff;
}

.nav-link a:hover {
    color: #636363;
}
.nav-link a:link{
    text-decoration: none;
    color: #ffffff;
}

.nav-link{

    position: relative;
    padding: 0.5rem 0;
}



.menu-toggle {
    display: none;
    background: none;
    border: none;
    cursor: pointer;
}

.menu-toggle span {
    display: block;
    width: 25px;
    height: 3px;
    background: #fff;
    margin: 5px 0;
    transition: 0.3s;
}

.menu-toggle span.open {
    transform: rotate(45deg);
    background: red;
}
a:visited{
    text-decoration: none;
    color: #ffffff;
}


html.dark body div#__nuxt.isolate header.header nav.navbar ul.nav-links li a.router-link-active.router-link-exact-active.router-link-active {
    color: #13337A;
    background-color: #fff;
    border: #333;
    border-radius: 5px;
    padding: 0.5rem 1rem;
}

.menu-bar .open {
display: inline;
}

@media screen and (max-width: 768px) {
    .menu-bar .nav-links{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
        width: 75%;
        padding: 1rem;
        margin: 0.5rem 0;
    }
    .logo {
        display: none;
    }


    
}

</style>