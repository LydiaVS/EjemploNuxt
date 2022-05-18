<template>
  <main>
    <banner-image :source="'/img2.jpg'" :alt="'imagen de plantas'"  />
    <section />
    <h1>About</h1>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatum recusandae quam alias, ullam quo eos quaerat. Aperiam deleniti, ipsa error voluptatum harum nulla, inventore accusamus et incidunt ducimus recusandae ab.</p>
    <section class="article-card">
      <article-card 
      v-for="(item,i) in post"
      :key="i"
      :post="item.title">
        
      </article-card>
    </section>
  </main>
</template>
  <style  lang="postcss" >
      section{
    @apply p-5;
  }
    h1{
    @apply text-3xl ml-20 mb-10;

  }
  p{
    @apply ml-20 mr-28;
  }
  .article-card{
    display: flex;
  }
  </style>

<script>
export default {
  name: 'AbouPage',
    data() {
      return{
        post:[
          {id: 1, title:'Esto es 1'},
          {id: 2, title:'Esto es 2'},
          {id: 3, title:'Esto es 3'},
          {id: 4, title:'Esto es 4'}
          

        ]
      }

  },
}
</script>
