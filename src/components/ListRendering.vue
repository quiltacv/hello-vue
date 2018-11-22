<template>
	<div class="list-rendering">
    <h2>v-for</h2>
    <ul>
      <li v-for="(food, index) in foods" :key="index"> {{ food.name }} - {{ index + 1 }} </li>
    </ul>

    <ul>
      <li v-for="(value, key, index) of myGirl" :key="index">{{ key }} : {{ value }} - {{ index }}</li>
    </ul>
	</div>
</template>

<script>
  export default {
    data() {
      return {
        myGirl: {
          name: 'Hana',
          age: '20',
          phone: '0909777888',
        },
        foods: [
          {name: 'Hamburger'},
          {name: 'Sandwich'},
          {name: 'Chicken chop'},
        ]
      }
    }
  }
</script>
