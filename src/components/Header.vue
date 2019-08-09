<template>
    <header>
        


        <b-navbar  class="navbar-top" toggleable="md" type="dark"  variant="info">

  <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>

  <b-navbar-brand href="#"> <img src="./../assets/hdpi.png"> The Periodic Table</b-navbar-brand>

  <b-collapse is-nav id="nav_collapse" class="pull-right">

    <b-navbar-nav >
      <b-nav-item onclick="window.print()">Print</b-nav-item>
      <b-nav-item href="./../assets/ptreal.pdf">Pdf</b-nav-item>
      <b-nav-item href="https://iw.co.zw/about" >About</b-nav-item>
    </b-navbar-nav>


<div>
  
  <b-modal id="modalPopover" title="Modal with Popover" ok-only>
    <p>
      Coming Soon. Please Check Later.
     
    </p>
    
  </b-modal>
</div>


    <!-- Right aligned nav items -->
    <b-navbar-nav class="ml-auto">

      <!--<b-nav-form>
        <b-form-input size="sm" class="mr-sm-2" type="text" placeholder="Search"/>
        <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
      </b-nav-form>-->

      <!--<b-nav-item-dropdown text="Lang" right>
        <b-dropdown-item href="#">EN</b-dropdown-item>
        <b-dropdown-item href="#">ES</b-dropdown-item>
        <b-dropdown-item href="#">RU</b-dropdown-item>
        <b-dropdown-item href="#">FA</b-dropdown-item>
      </b-nav-item-dropdown>-->

     <!-- <b-nav-item-dropdown right>
        Using button-content slot -->
        <!--<template slot="button-content">
          <em>User</em>
        </template>
        <b-dropdown-item href="#">Profile</b-dropdown-item>
        <b-dropdown-item href="#">Signout</b-dropdown-item>
      </b-nav-item-dropdown>-->
    </b-navbar-nav>

  </b-collapse>
</b-navbar>

<!-- navbar-1.vue -->


    </header>
</template>
<script>
export default {
   
    data(){
        return{

            title: "This is the Title"

        }
    },
    methods: {
      printPage: function(){
        window.print();
      }
      
    }
}
</script>
<style scoped>
navbar-top{
  background-color: #16A085;
}
</style>
