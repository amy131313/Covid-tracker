<template>
    <select v-model="selected" @change="onChange()" class="form-select mt-10 block w-full border p-3 rounded">
      <option value="0">Select Country</option>
        <option v-for="country in countries"
          :value="country.ID"
          :key="country.ID">
          {{ country.Country }}
        </option>
    </select>
</template>
<script>
export default {
    
    name: 'CountrySelect',
    props: ['countries'],
    data() {
        return {
            selected: 0
        }
    }, 
    methods: {
        onChange() {
            const country2 = this.countries?.find( i =>  i.ID=== this.selected)
            console.log(country2)
            this.$emit('get-country',country2)
        }
    }
}
</script>