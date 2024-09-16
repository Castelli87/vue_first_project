
<!--  Options API  -->

<script>
export default {
  data() {
    return {
      name: "Davide",
      isVisible: true,
      status:'pending',
      placeLived: ["Belpasso", "Porcari City", "Elba", "Liverpool"],
      link:'https://davidecastelli.tech/'
    };
  },
  methods:{
    toogleStatus(){
      if (this.status === 'active'){
        this.status = 'pending'
      } else if ( this.status === 'pending'){
        this.status = 'inactive'
      }else{
        this.status = 'active'
      }
    }
  }
};
</script>
<template>
  <h1>Hello World from a Vue project</h1>
  <p v-if="isVisible">{{ name }}</p>

  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h3>Place where i lived</h3>
  <ul>
    <li v-for="i in placeLived" :key="i">{{ i }}</li>
  </ul>

  <h3>My personal portfolio</h3>
  <a v-bind:href="link">Click to open from the long way</a>
  <div>
    <a :href="link">Click to open</a>
  </div>

  <br>

  <button v-on:click="toogleStatus">Change Status</button>



</template>
