<template>
    <v-toolbar color="black" dark extended >   
        <img src="../assets/logo.png" alt="" width="40px" height="40px">
        <h1>at</h1> 
      <v-toolbar-title class="white--text"><h3>ObjectStore</h3></v-toolbar-title>

    <template v-slot:extension>
        <div align="center">
            <v-toolbar flat  color="black">

            <v-menu :nudge-width="100">
                <template v-slot:activator="{ on }">
                <v-toolbar-title v-on="on">
                    <span>All Assets </span>
                    <v-icon dark>arrow_drop_down</v-icon>
                </v-toolbar-title>
                </template>

                <v-list>
                <v-list-tile
                    v-for="(item,i) in model"
                    :key="i"
                >
                    <v-list-tile-title v-text="item"></v-list-tile-title>
                </v-list-tile>
                </v-list>
            </v-menu>

            <v-spacer></v-spacer>
            <v-text-field
                    label="Search Company Directory"
                    dark
                    flat
                    solo-inverted
                    hide-details
                    clearable
                    prepend-inner-icon="search"
                    xs8
                ></v-text-field>
                <v-card flat color="black">
                    <v-card-text>Plus/Pro</v-card-text>
                </v-card>
                <v-card flat color="black">
                    <v-card-text>Impressive New Assets</v-card-text>
                </v-card>
            
            </v-toolbar>
        </div>
    </template>

    <v-spacer></v-spacer>

    <v-btn icon>
      <v-icon>search</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>apps</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>refresh</v-icon>
    </v-btn>

    <v-btn icon>
      <v-icon>more_vert</v-icon>
    </v-btn>
  </v-toolbar>
</template>

<script>
export default {
    data (){
        return {
            model: ['Free', 'Professional']
        }
    }
    
}
</script>

<style>

</style>
