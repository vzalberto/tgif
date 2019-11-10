<template>
	<div>
		<p>TGIF!</p>
		<div v-bind:key="gif.id" v-for="gif in gifs">
			<img :src=gif.images.fixed_height_small_still.url />
			
		</div>
	</div>
</template>

<script>
export default {
  name: 'TGIF',
  props: {
    gifs: Array
  }
}
</script>
