<template>
  <p>Aaaand your score isss!!!- {{ score }}</p>
  <p class="reaction">{{ reaction }}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            reaction: null
        }
    },
    mounted() {
      if(this.score < 290) {
          this.reaction = "What the! I didn't see... do it again!?"
      }
      else if (this.score < 350 ) {
        this.reaction = "Power level increasing"  
      }  
      else {
        this.reaction = "Flash is dissapointed"
      }
    }
}
</script>

<style>
  .reaction {
      font-size: 1.4em;
      color: #000000;
      font-weight: bold;
  }
</style>