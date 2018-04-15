<template>
  <div class="hello">
   <div v-for="fsh in fishies" :key="fsh.key" class="fish" :id="fsh.key">
     <img class="fish-img" :src="fsh.src" :alt="fsh.key"/>
     <div class="fish-text">
       <p>Photo by 
         <a :href="fsh.reference">{{fsh.photographer}}</a> on
         <a href="https://unsplash.com/search/photos/fish?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>
       </p>
     </div>     
   </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data: function () {
    return {
      fishies: [
        {key: 'jellyfish', src:'jelly.jpg', photographer: 'naomi tamar', reference: 'https://unsplash.com/photos/u1iIIQwtRqU?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText'},
        {key: 'ray', src:'ray.jpg', photographer: 'Alex Suprun', reference: 'https://unsplash.com/photos/yF8RUx0i7pA?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText'},
        {key: 'shark', src:'shark.jpg', photographer: 'Matt Helbig', reference: 'https://unsplash.com/photos/wdL8UywQtWU?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText'},
        {key: 'yellow', src:'yellow.jpg', photographer: 'David Clode', reference: 'https://unsplash.com/photos/dzQXyjruzVg?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText'},
        {key: 'zebra', src:'zebra.jpg', photographer: 'Alexandra Baeva', reference: 'https://unsplash.com/photos/PuxXygVWWkU?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText'},
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .fish {
    max-width: 100%;
    position: relative;
  }
  .fish-img{
    max-width: 100%;
  }
  .fish-text{
    background-color: white;
    display: inline-block;
    padding: 0 .5rem;
    position: absolute;
    bottom: 2rem;
    right: 2rem;
  }
</style>
