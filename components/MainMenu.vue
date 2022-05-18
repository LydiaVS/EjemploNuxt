<template>
    <nav>
        <ul>
            <li>
                <NuxtLink to="/"> 
                    <MIconHome />
                    Home 
                </NuxtLink>
            </li>
            <li>
                <NuxtLink to="/about"> <MIconPhone /> About </NuxtLink>
            </li>
        </ul>
        <div class="user" @click="panelIsOpen = !panelIsOpen"> <MIconAccount /></div>
        <div class="panel" v-show="panelIsOpen" ></div>
    </nav>
</template>
<script>
    export default {
        data(){
            return{
                panelIsOpen: false
            }
        }
    
}
</script>
<style lang="postcss">
    nav{
        display:flex;
        justify-content: space-between;
        align-items: center;
        @apply bg-gray-200;
        ul{
            display: flex;
            li{
                @apply p-5;
            }
        }
        .user{
            @apply w-11 h-11 rounded-full bg-gray-700 mr-8;
        }
        .panel{
            @apply w-48 h-28 bg-white mr-8 ;
            position:absolute;
            top: 80px;
            right: 0;
            
        }
    }
    .nuxt-link-exact-active{
        font-weight: bold;
    }

</style>