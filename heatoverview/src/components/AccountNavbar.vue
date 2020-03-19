<template>
<div>
  <b-navbar toggleable="lg" type="dark" variant="info" style="height: 60px">
    <b-navbar-brand href="/">
        <img src="../assets/logo.png" height="20">
    </b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
            <b-nav-item-dropdown text="Pages" left>
                <template v-for='page in pageList'>
                    <page-list :id="page.name" :to="page.to" :key="page.name"></page-list>
                </template>
            </b-nav-item-dropdown>    
        </b-navbar-nav>
        <b-navbar-nav class="ml-auto">
            <b-nav-item-dropdown variant="primary" right>
                <template v-slot:button-content>
                    <b-icon-gear></b-icon-gear>Settings
                </template>
                <template v-for='setting in settingList'>
                    <page-list :id="setting.name" :to="setting.to" :key="setting.name"></page-list>
                </template>
            </b-nav-item-dropdown>  

        </b-navbar-nav>
      <!-- <b-navbar-nav>
        <b-nav-item href="#" @click="">Link</b-nav-item>
        <b-nav-item href="#" disabled>Disabled</b-nav-item>
      </b-navbar-nav> -->
    </b-collapse>
  </b-navbar>
  <page-navbar :currentLink='currentLink' style="height: 60px"></page-navbar>

</div>
</template>




<script>
import { BNavbarBrand, BNavbar, BNavItem, BNavbarToggle, BNavItemDropdown, BNavForm, BButton, BCollapse, BDropdownItem, BNavbarNav, BIcon, BIconGear} from 'bootstrap-vue'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Vue from 'vue'
import PageNavbar from './PageNavbar'

Vue.component('page-navbar', PageNavbar)
Vue.component('b-dropdown-item', BDropdownItem)
// Vue.component('b-nav-item-dropdown', BNavItemDropdown)


Vue.component('page-list', {
    props: ['id', 'to'],
    template: '<b-dropdown-item :to="to">{{id}}</b-dropdown-item>'
})

export default{
    name: 'AccountNavbar', 
    data(){
        return {
            pageList: [],
            settingList: [],
            currentLink: ""
        }
    },
    components: {
      BNavbar,
      BNavbarNav,
      BNavbarBrand,
      BNavItem,
      BCollapse,
      BNavbarToggle,
      BNavItemDropdown,
      BIcon,
      BIconGear,
    },
    beforeMount(){
        this.pageList = [{
            name: "axnxnnxnx",
            to: "a1"
        }, {
            name: "b",
            to: "b1"
        }, {
            name: "c",
            to: "c1"
        }];
        this.settingList = [{
            name: "sa",
            to: "sa1"
        }, {
            name: "sb",
            to: "sb1"
        }, {
            name: "sc",
            to: "sc1"
        }];
        this.currentLink =  this.pageList.filter(d=>d['to'] === window.location.href.split('/').pop()).pop() ?  this.pageList.filter(d=>d['to'] === window.location.href.split('/').pop()).pop().name : "Welcome!"
  
    },
    methods:{
    }
}

</script>