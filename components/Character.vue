<template>
	<div class="new"> 
		<div class="container mt-2">
	<div class="card border-dark mb-3" style="max-width: 40rem;">
  <div class="card-header text-center">
		<h1><span class="badge badge-dark">{{character.name}}</span></h1>
	</div>
  <div class="card-body">
	<h4 class="card-header text-center"><u>Description</u>
	<br> 
	{{character.description}}
	</h4>
    <img :src="character.thumbnail.path+'.jpg'" class="card-img-top">
  </div>
	</div>
</div>
<hr>
	<div class="container mt-2">
		<ul class="list-group">
				<div class="card border-dark mb-3" style="max-width: 40rem;">
			<div class="card-header text-center">Comics including {{ character.name}}
				 ({{character.comics.items.length}})
				 </div>
			</div>
		<div v-for="comic in character.comics.items" v-bind:key="comic.id">
  <li class="list-group-item list-group-item-dark">{{comic.name}}</li>
	</div>
</ul>
	</div>
		<div class="container mt-2">
		<ul class="list-group">
				<div class="card border-dark mb-3" style="max-width: 40rem;">
			<div class="card-header text-center">Events including {{ character.name}}
				 ({{character.events.items.length}})
				 </div>
			</div>
		<div v-for="event in character.events.items" v-bind:key="event.id">
  <li class="list-group-item list-group-item-dark">{{event.name}}</li>
	</div>
</ul>
	</div>
	</div>
</template>

<script>
export default {
  props: ["character"]
};
</script>

<style>
.card-img-top {
  width: 100%;
  height: 50vw;
  object-fit: cover;
}
.error {
  color: #ff0022;
  text-align: center;
}

</style>