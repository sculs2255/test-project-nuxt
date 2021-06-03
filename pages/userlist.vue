<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card>
        <v-card-title class="headline">
         User Data
        </v-card-title>
        
        <v-simple-table>
            <tr class="text-center" >
                <th>ID</th>
                <th>Name</th>
                <th>E-mail</th>
                <th>stats</th>
                 <th>Action</th>
            </tr>
                <tr v-for="use in userlist" :key="use.id" class="text-center " style="border-bottom:1px ">
                    <td style="width:100px">{{use.id}}</td>
                    <td>{{use.name}}</td>
                    <td>{{use.email}}</td>
                    <td>{{use.stats}}</td>
                    <td>
                        <v-btn color="green accent-4">Edit</v-btn>
                        <v-btn color="red accent-4">Delete</v-btn>
                    </td>
            </tr>
        </v-simple-table>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
    data () {
        return{
            userlist: [
            {
                id:1,
                name:'Kittipot Subsoongnern',
                email:'ktpssn@hotmail.com',
                stats:'Admin'
            },
            {
                id:2,
                name:'Test test',
                email:'test@hotmail.com',
                stats:'user'
            },
            {
                id:3,
                name:'Test2 test2',
                email:'test2@hotmail.com',
                stats:'user'
            },
            {
                id:4,
                name:'Test3 test3',
                email:'test3@hotmail.com',
                stats:'user'
            },
            ]
        }
    }
}
</script>

<style>
    .tr{
        margin: 50px;
    }
    .td{
        margin: 100px;
    }

</style>