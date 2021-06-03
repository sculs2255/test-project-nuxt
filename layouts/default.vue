<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
    >
      <v-list>
        <v-list-item v-for="(item, i) in items" :key="i" :to="item.to" router exact>
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar :clipped-left="clipped" fixed app  v-for="(user, i) in users" :key="i">
      <v-app-bar-nav-icon @click.stop="drawer = !drawer,clipped = !clipped"  />

      <v-spacer />

      <v-tabs centered>
        <v-tab to="/userlist" >User Data</v-tab>
        <v-tab to="/productlist">Product Data</v-tab>
      </v-tabs>

      <v-spacer />

      <v-avatar color="primary" size="32"  >
        <span>{{user.initials}}</span>
      </v-avatar>

      <span>{{ user.email }}</span>

      <v-btn fab small>
        <v-icon  color="light">mdi-export</v-icon>
      </v-btn>

    </v-app-bar>

    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>

    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-account-circle',
          title: 'Profile',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'Inspire',
          to: '/inspire'
        },
                {
          icon: 'mdi-chart-bubble',
          title: 'asddsa',
          to: '/fds'
        }
      ],
      users:[
        {
          initials: 'JD',
          fullName: 'John Doe',
          email: 'john.doe@doe.com',
        }
      ],

      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js'
    }
  }
  
}
var randomColor = Math.floor(Math.random()*16777215).toString(16);

</script>

<style>
  .v-btn{
    margin: 10px;
  }
  .v-avatar{
    margin: 10px;
  }
</style>