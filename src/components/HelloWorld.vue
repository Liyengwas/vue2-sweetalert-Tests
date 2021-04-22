<template>
  <div class="container">
    <div class="large-12 medium-12 small-12 cell">
      <h1 style="font-family:ubuntu">Vue toastr notifications example</h1>
        <button v-on:click="showAlert">Hello world</button>
        <button v-on:click="showAlertConfirm">Confirm Me</button>
    </div>
  </div>
</template>
     
<script>
       
  export default {
    methods: {
        showAlert(){
            this.$swal('Hello Vue world!!!');
        },
        showAlertConfirm(){
            this.$swal({
              title: 'Are you sure?',
              text: "You won't be able to revert this!",
              type: 'warning',
              showCancelButton: true,
              confirmButtonColor: '#3085d6',
              cancelButtonColor: '#d33',
              confirmButtonText: 'Yes, delete it!'
            }).then((result) => {
              if (result.value) {
                this.$swal(
                  'Deleted!',
                  'Your file has been deleted.',
                  'success'
                )
              }
            });
        }
    }
  }
</script>