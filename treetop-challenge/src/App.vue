<template class="picker">
  <h1> Welcome To Treetop Component Picker </h1>
<div class="picker__lists">
  <ul>
    <li class="picker__item">
      <TreetopComponent
      class="picker__component"
        v-for="component in components"
        :key="component.code"
        :name="component.name"
        :code="component.code"
        :details="component.details">
          <input type="checkbox" v-model="componentList" :value="component.name" class="picker__checkbox">
      </TreetopComponent>
    </li>
  </ul>
  <div>
    <h2>Selected: </h2>
    <ul>
       <li v-for="(selectedComponent, i) in componentList" :key="selectedComponent"> {{selectedComponent}}
         <button type="button" @click="deleteItem(i)"> remove </button>
        </li>
    </ul>
  </div>
</div>

</template>

<script>

import TreetopComponent from './components/TreetopComponent.vue'

export default {
  name: 'App',
  components: {
    TreetopComponent,
  },
  data() {
    return {
      componentList: [],
      components: [{
            name: 'Component A',
            code: 20430,
            details: 'Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. '
          },
          {
            name: 'Component B',
            code: 83499,
            details: 'At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.'
          },
          {
            name: 'Component C',
            code: 50895,
            details: 'Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat.'
          },
          {
            name: 'Component D',
            code: 90098,
            details: 'sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum.'
          },
          {
            name: 'Component E',
            code: 93243,
            details: 'Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.'
          },
          {
            name: 'Component F',
            code: 87232,
            details: 'Lorem Ipsum ajnfafnakjfnödkjsnfdökjf',
          },
          {
            name: 'Component G',
            code: 98348,
            details: 'Lorem Ipsum ajnfafnakjfnödkjsnfdökjf',
          },
          {
            name: 'Component H',
            code: 93474,
            details: 'Lorem Ipsum ajnfafnakjfnödkjsnfdökjf',
          },
          {
            name: 'Component I',
            code: 45368,
            details: 'Lorem Ipsum ajnfafnakjfnödkjsnfdökjf',
          },
        ],
    }
  },
  methods: {
    deleteItem(i) {
      this.componentList.splice(i, 1);
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
}

.picker__lists {
  display: flex;
}

.picker__item,
.picker__component {
  list-style: none;
}

.picker__checkbox {
  margin-left: 2rem;
}

</style>
