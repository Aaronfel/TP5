<template>
    <div :style="square" @click="squareClick()"></div>
</template>

<script>

  export default  {
    name: 'src-components-square',
    props: [
      'index',
      'square', 
      'mensajes',
      'pickedColor',
      'setAllColorsTo'
    ],
    mounted () {

    },
    data () {
      return {

      }
    },
    methods: {
      squareClick(){
        var clickedColor = this.square.backgroundColor;
        if (clickedColor === this.pickedColor) {
          this.mensajes.f.messageDisplay("You Picked Right!");
          this.setAllColorsTo(this.pickedColor);
          this.mensajes.f.restartButton("Play Again!");
          this.mensajes.f.headerColor(this.pickedColor);
        } else {
          this.$emit('e-square',this.index,"#232323")
          this.mensajes.f.messageDisplay("Try Again!");
        }
      }
    },
    computed: {
    }
}


</script>

<style scoped lang="css">
</style>
