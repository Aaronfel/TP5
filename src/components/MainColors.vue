<template>
    <div id="container">
			<Square 
				class="square" 
        :index="index"
				:mensajes="mensajes"
				:square="sq"
				@e-square="eSquare"
				:set-all-colors-to="setAllColorsTo"
				:picked-color="pickedColor"
				v-for="(sq,index) in squares"
				:key="index"
			/>
		</div>

</template>

<script>

  import Square from './Square'

  export default  {
    name: 'src-components-main-colors',
    props: [
      'squares',
      'mensajes',
      'pickedColor',
      'setAllColorsTo'
    ],
    components: {
      Square
    },
    mounted () {

    },
    data () {
      return {

      }
    },
    methods: {
      eSquare(index,color) {
        //console.log(index,color)
        this.$emit('e-square',index,color)
      }
    },
    computed: {

    }
}


</script>

<style scoped lang="css">
</style>
