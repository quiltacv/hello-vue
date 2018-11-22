<template>
    <div class="form-input-binding">
        <div class="text">
            {{ message }}
        </div>
        <div class="input-form">
            <input type="text" v-model="input" name="">
        </div>

        <div class="input-form">
            <select v-model="select">
                <option disabled="">Choose one</option>
                <option :value="valueSelect.one">One</option>
                <option :value="valueSelect.two">Two</option>
            </select>
        </div>

        <div class="input-form">
           <input type="checkbox" v-model="checkbox" name="">
        </div>

        <div class="input-form">
            <input type="radio" v-model="radio" value="one">
            <input type="radio" v-model="radio" value="two">
        </div>
    </div>

</template>

<script>
    export default {
        data() {
            return {
                message: 'foxzi',
                input: '',
                checkbox: false,
                radio: '',
                select: '',
                valueSelect: {
                  one: 'One',
                  two: 'Two'
                }
            }
        }
    }
</script>
