<template>


    <v-row  >
      <v-col cols="2" sm="2" md="2">
<!-- -------------------List of players----------------------  -->

          <v-card class="mx-auto" max-width="300" tile >
            <v-list rounded>
              <v-subheader> Players online </v-subheader>
              <v-list-item-group v-model="selectedItem" color="primary" >
                <v-list-item  v-for="(item, i) in items"  :key="i" >
                  <v-list-item-icon>
                    <v-icon v-text="item.icon"></v-icon>
                  </v-list-item-icon>
                  <v-list-item-content>
                    <v-list-item-title v-text="item.text"></v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list-item-group>
            </v-list>
          </v-card>

<!-- -------------------Game----------------------  -->
      </v-col>
      <v-col cols="8" sm="8" md="8">
        <template>
          <v-container>
            <div class="d-flex flex-column justify-space-between align-center">
              <v-img  lazy-src="https://miro.medium.com/max/1190/1*bD9nGMBuGWBdawdmrMmzVA.png"  
                src="https://miro.medium.com/max/1190/1*bD9nGMBuGWBdawdmrMmzVA.png" ></v-img>
            </div>
          </v-container>

          <v-container>
            <v-row  align="center"  justify="space-around">
              <v-btn depressed color="primary"> Normal </v-btn>
              <v-btn depressed color="primary"> Primary </v-btn>
              <v-btn depressed color="primary"> Error</v-btn>
              <v-btn depressed color="primary"> Disabled</v-btn>
            </v-row>
          </v-container>


        </template>
<!-- -------------------Chat----------------------  -->
      </v-col>
      <v-col cols="2" sm="2" md="2">
        <v-container fluid>
                <v-textarea  solo  name="input-7-4"  label="there will be the messages" ></v-textarea>
          </v-container>
          <v-form>
            <v-container>
                  <v-text-field  v-model="title"  :rules="rules" counter="25" hint="enter your message"  label="chat"></v-text-field>
                  <v-btn  depressed  color="primary"> Send </v-btn>
            </v-container>
          </v-form>

      </v-col>
    </v-row>



</template>



<script>
export default {
    data () {
      return {
        selectedItem: 1,
        items: [
          { text: 'Player 1', icon: 'mdi-account' },
          { text: 'Player 2', icon: 'mdi-account' },
          { text: 'Player 3', icon: 'mdi-account' },
        ],
        title: 'typical message',
        rules: [v => v.length <= 25 || 'Max 25 characters'],
      }
    },
  }
</script>