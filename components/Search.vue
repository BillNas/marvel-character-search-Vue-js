<template>
<div class="container mt-1">
	<div class="search">
	<a href="http://marvel.com" 
		rel="noopener noreferrer" target="_blank">Data provided by Marvel © 2019 MARVEL</a>
		<input type="text" class="form-control mb-3" name="Search" placeholder="Enter Movie Name" v-model="query" @keypress.enter="characterSearch">
		<button type="button" class="btn btn-danger btn-md" v-on:click="characterSearch">Search</button>
	</div>
    </div>
</template>

<script>
	export default{
		data(){
			return{
				query:''
			}
		},

	
	methods:{
		characterSearch(){
			if (this.query=="") {	
				alert("Enter a character name");
			}
			else{
				this.$emit('requestSearch', this.query);
			}
		}
	}
}

</script>

<style> 



</style>
