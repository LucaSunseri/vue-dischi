<template>
  <div>
    <b-form-select v-model="selected" :options="options" :b-form-select="$emit('filterType', selected)"></b-form-select>
    <div class="mt-3">Selected: <strong>{{ selected }}</strong></div>
  </div>
</template>

<script>
  export default {
    name: 'Select',
    data() {
      return {
        selected: null,
        options: [
          { value: null, text: 'Please select an option' },
          { value: 'Pop', text: 'Pop'},
          { value: 'Rock', text: 'Rock'},
          { value: 'Jazz', text: 'Jazz'},
          { value: 'Metal', text: 'Metal'}
        ]
      }
    }
  }
</script>