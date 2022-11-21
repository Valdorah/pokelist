<template>
  <tr class="row" :id="id">
    <td>
      <img :src="image"/>
    </td>
    <td>
      {{ name }}
    </td>
    <td>
      <button v-on:click="remove(tab, id)">Delete</button>
    </td>
  </tr>
</template>

<script>
export default {
  name: 'myLine',
  props: {
    id: Number,
    image: String,
    name: String,
    tab: Array
  },
  methods:{
    remove: (tab, id) => {
      tab.splice(id, 1)
    }
  }
};
</script>

<style>
  .row:hover{
    background-color: rgba(255, 255, 255, 0.8);
    transform: scale(1.05);
    transition-duration: 200ms;
    box-shadow: 0px 2px 4px black;
  }
</style>