<template>
	<div class="list-rendering">
    <ul>
      <li v-for="(food, index) in foods"> {{ food.name }} - {{ index + 1 }} </li>
    </ul>

    <ul>
      <li v-for="food in foods"> {{ food.name }} </li>
    </ul>
	</div>
</template>

<script>
  export default {
    data() {
      return {
        foods: [
          {name: 'Hamburger'},
          {name: 'Sandwich'},
          {name: 'Chicken chop'},
        ]
      }
    }
  }
</script>
