<template>
<div class="container mt-1">
	<div class="search">
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
		movieSearch(){
			if (this.query=="") {	
				alert("No movies found.");
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