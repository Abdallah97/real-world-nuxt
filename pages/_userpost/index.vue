<template>
    <div>
      <h1> User # {{userpost}} </h1>
    </div>
  </template>
  
  <script>
  export default {
    name: '',
    head() {
      return {
        title: 'User list  - of USer  ' + this.userpost ,
        meta: [
          
          {
            hid: 'description',
            name: 'description',
            content: 'My custom User' + this.userpost 
          }
        ]
      
  }
  },
  computed: {
    userpost() {
      return this.$route.params.userpost;
    }
  }
  
}
  </script>
  