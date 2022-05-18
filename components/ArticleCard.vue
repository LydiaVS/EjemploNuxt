<template>
    <article>
        <div>
            <img class="card" src="/card1.jpg" alt="">
            <button @click= "playpause">
                <MIconPlay v-show="!isPlaying" />
                <MIconPause v-show="isPlaying" />
                {{post}}</button>
        </div>
    </article>
</template>
<script>
    import {Howl, Howler} from 'howler';

    export default {
        
        props:['post'],
        data(){
            return{
                sound: '',
                isPlaying: false

            }
        },
        mounted(){
            this.sound = new Howl({
                src: ['/audios/test.mp3']
            })

        },
        methods: {
            playpause(){
                if(this.sound.playing()){
                    this.sound.pause()
                    this.isPlaying = false
                }else{
                    this.sound.play()
                    this.isPlaying = true
                }
            }

        }

    }
</script>
<style lang="postcss">
    article{
        @apply w-1/5 ml-16 mt-20 ;
        .card{
        @apply rounded-3xl w-full;
        }
        button{
        @apply bg-gray-300 p-3 w-full rounded-3xl my-3;
        }
        button:hover{
            @apply bg-gray-500;
        }

    }



</style>