<template>
    <b-navbar-nav class="ml-auto">
        <b-nav-item-dropdown right>
        <template #button-content>
            <em>Login</em>
        </template>
        <b-dropdown-item href="#">Sign in</b-dropdown-item>
        <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
    </b-navbar-nav>
</template>

<script>
export default {
    name : 'login'
}
</script>

<style>
.dropdown-menu{
    background-color: #2e2e2e!important;
}
.dropdown-menu .dropdown-item{
    color: #fff!important;
}
.dropdown-item:hover{
    background-color: #747474!important;
}
</style>