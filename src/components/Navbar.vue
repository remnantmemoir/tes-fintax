<template>
    <div>
        <b-navbar toggleable="lg" type="dark" variant="dark">
            <b-navbar-brand href="#">ARK</b-navbar-brand>

            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

            <b-collapse id="nav-collapse" is-nav>
                <b-navbar-nav>
                    <!-- Home -->
                    <b-nav-item>
                        <router-link class="nav-link" to="/">Home</router-link>
                    </b-nav-item>

                    <!-- About -->
                    <b-nav-item>
                        <router-link class="nav-link" to="/table">Table</router-link>
                    </b-nav-item>
                </b-navbar-nav>
                
                <!-- nested component | login -->
                <login></login>

            </b-collapse>
        </b-navbar>
    </div>
</template>

<script>
import Login from './Login.vue'

export default {
    name: 'Navbar',
    components: {
        'login': Login
    }
}
</script>

<style scoped>
.bg-dark {
    background-color: #202020 !important;
}

</style>