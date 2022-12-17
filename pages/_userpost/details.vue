<template>
    <div>
      <h1> User # {{id}} - Details</h1>
    </div>
  </template>
  
  <script>
  export default {
    name: 'CreatePage',
    head() {
      return {
        title: 'EventListing  - of event  ' + this.id ,
        meta: [
          
          {
            hid: 'description',
            name: 'description',
            content: 'My custom event' + this.id 
          }
        ]
      
  }
  },
  computed: {
    id() {
      return this.$route.params.userpost;
    }
  }
}
  </script>
  