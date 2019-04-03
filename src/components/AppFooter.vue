<template>
    <div>
        <v-footer dark height="auto" color="black">
            <v-container grid-list-md text-xs-center>
                <v-card-text>
                    <v-btn
                    v-for="icon in icons"
                    :key="icon"
                    class="mx-3 white--text"
                    icon
                    >
                    <v-icon size="24px">{{ icon }}</v-icon>
                    </v-btn>
                </v-card-text>

                
                <v-layout row wrap>
                    <v-flex xs2>
                        <v-card color="black" >
                            <p><b>Language</b></p>
                            <p v-for="(lang,i) in languages" :key="i">{{lang}}</p>
                        </v-card>
                    </v-flex>

                    <v-flex xs2 v-for="(ro,i) in row" :key="i">
                        <v-card  color="black" >
                        <v-card-text>{{ro.title}}</v-card-text>
                        <v-card-text v-for="(it,j) in ro.child" :key="j">
                            <a :href="it.link" >{{it.title}}</a>
                        </v-card-text>
                        </v-card>
                    </v-flex>
                    <v-flex xs4>
                        <v-card >
                        <v-card-text>kkkkk</v-card-text>
                        <v-card-text>kkkkk</v-card-text>
                        </v-card>
                    </v-flex>
                </v-layout>

                <v-divider></v-divider>

                <v-card-text class="white--text">
                    &copy;2018 — <strong>Vuetify</strong>
                </v-card-text>
            </v-container>
        </v-footer>
    </div>
</template>

<script>
export default {
    data: () => ({
      icons: [
        'fab fa-facebook',
        'fab fa-twitter',
        'fab fa-google-plus',
        'fab fa-linkedin',
        'fab fa-instagram'
      ],
      languages: ['English', 'Francais', 'Deutsch'],
      currentLang: 0,
      row: [
          {
              title: 'Sell Object on Artefact',
              child: [
                  {
                      title: 'Submission Guidelines',
                      link: '#'
                  },
                  {
                      title: 'Object Store Tools',
                      link: '#'
                  },
                  {
                      title: 'Publisher Login',
                      link: '#'
                  },
                  {
                      title: 'FAQ',
                      link: '#'
                  }
              ]
          },
          {
              title: 'Discover',
              child: [
                  {
                      title: 'Submission Guidelines',
                      link: '#'
                  }
              ]
          },
          {
              title: 'Affiliate Program',
              child: [
                  {
                      title: 'Submission Guidelines',
                      link: '#'
                  }
              ]
          }
      ]
    })
    
}
</script>

<style>

</style>
