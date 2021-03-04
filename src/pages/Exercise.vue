<template>
	<!--
	Awesome Exercise 2 - Vue.js Lists & Components

	1) Create an array for the food items you see on the page. Each object in the array should contain properties for the image url, name, description and deliciousness
	2) Create a v-for loop that displays these food items onto the page, with all the data coming from the food array (hint: for the image src, use :src)
	3) Add your own food item to the list
	4) Create a child component and use it to display each of your items (don't use the components/Solution/Food.vue file)
	5) Add unique id's to the food array for each item, and apply these to a :key property on your v-for loop

	-->
  <q-page padding>
  	<div
	  class="q-pa-md row items-stretch">

  	  <food
		v-for="( food, id ) in foods"
	  	:key="id"
		:food="food">
  	  </food>
  	  
  	</div>
  </q-page>
</template>

<script>
	export default {
		data() {
			return {
				foods: [
					{
						id: 1,
						url: 'https://i.imgur.com/0umadnY.jpg',
						name: 'Burger',
						desc: 'A burger is a sandwich consisting of one or more cooked patties of ground meat, usually beef, placed inside a sliced bread roll or bun.',
						delish: '4/5'
					},
					{
						id: 2,
						url: 'https://i.imgur.com/b9zDbyb.jpg',
						name: 'Pizza',
						desc: 'Pizza is a savory dish of Italian origin, consisting of a usually round, flattened base of leavened wheat-based dough.',
						delish: '5/5'
					},
					{	id: 3,
						url: 'https://i.imgur.com/RbKjUjB.jpg',
						name: 'Sprouts',
						desc: 'The Brussels sprout is a member of the Gemmifera Group of cabbages, grown for its edible buds.',
						delish: '1/5'
					},
					{	id: 4,
						url: 'https://www.persnicketyplates.com/wp-content/uploads/2009/12/best-macaroni-cheese-SQUARE.jpg',
						name: 'Mac & Cheese',
						desc: 'Macaroni and cheese is a dish of cooked macaroni pasta and a cheese sauce, most commonly cheddar. It can also incorporate other ingredients, such as breadcrumbs or meat.',
						delish: '5/5'
					}
				]
			}
		},
		components: {
			'food' : require('components/Food.vue').default
		}
	}
</script>

<style>
	.card {
		flex-basis: 210px;
		border: 1px solid #ccc;
		border-radius: 5px;
		padding: 5px;
		margin-right: 10px;
		margin-bottom: 10px;
	}
	.card img {
		max-width: 100%;
	}
	.card-content {
		padding: 0 10px;
	}
	h1 {
		font-size: 23px;
	}
	p {
		font-size: 14px;
	}
</style>
