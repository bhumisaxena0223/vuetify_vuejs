<template>
  <v-app>
    <!-- <v-container  pa-5>
        <v-layout class="container1" pa-5 color="pink">
    <v-flex style="padding:68px;">-->
    <template>
      <v-card flat pt-5 class="hidden-sm-and-down">
        <v-toolbar style="height:220px;" color="pink" dark extended flat></v-toolbar>

        <v-card class="mx-auto" max-width="900" style="margin-top: -110px;">
          <v-toolbar flat mt-5>
            <v-btn icon>
              <v-icon>arrow_back</v-icon>
            </v-btn>
            <v-toolbar-title class="grey--text ma-3">
              <v-tabs color="pink">
                <v-tab>My Bookings</v-tab>
                <v-tab>Cancelled Bookings</v-tab>
                <v-tab>Booking History</v-tab>
              </v-tabs>
            </v-toolbar-title>

            <v-spacer></v-spacer>

            <v-btn icon>
              <v-icon>refresh</v-icon>
            </v-btn>
          </v-toolbar>
          <v-divider></v-divider>
          <v-container fluid>
            <v-layout>
              <v-flex xs4 order-md2 order-xs1 class="ma-2 mr-3">
                <v-card class="mx-auto pa-2 ma-2" max-width="344" color="grey lighten-4">
                  <v-card-title>
                    <v-avatar>
                      <v-icon large>person</v-icon>
                    </v-avatar>
                    <div>{{data_content[0].name}}</div>
                    <span class="grey--text subtitle-2">Photographer</span>
                  </v-card-title>

                  <v-card-actions>
                   
                      <v-flex class="body-2">July 20 2019                      

                      </v-flex>
                      <v-icon @click="show = !show">{{ show ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
                    <v-btn style="padding-left:20px;" text>OTP:<v-chip> {{data_content[0].otp}}</v-chip> </v-btn>
                  </v-card-actions>

                  <v-expand-transition>
                    <div v-show="show">
                      <v-card-text
                        color="white"
                        v-for="item in content"
                        :key="item"
                      >{{item.text}} {{item.price}}</v-card-text>
                      <v-divider></v-divider>
                       <v-btn text @click="show = !show"></v-btn>
                    </div>
                  </v-expand-transition>
                </v-card>
              </v-flex>
              <v-flex xs4 order-md3 order-xs2 class="ma-2 mr-3">
                <v-card class="mx-auto pa-2 ma-2" max-width="344" color="grey lighten-4">
                  <v-card-title>
                    <v-avatar>
                      <v-icon large>person</v-icon>
                    </v-avatar>&nbsp;&nbsp;&nbsp;
                    <div>{{data_content[1].name}}</div>
                   <span class="grey--text subtitle-2">Photographer</span>
                  </v-card-title>

                  <v-card-actions>
                    <v-flex>
                        <span>July 20 2019</span>
                      </v-flex>
                      <v-icon @click="show1 = !show1">{{ show1 ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
                    <v-btn text style="padding-left:20px;"> OTP:<v-chip> {{data_content[1].otp}}</V-chip> </v-btn>
                  </v-card-actions>

                  <v-expand-transition>
                    <div v-show="show1">
                      <v-card-text
                        color="white"
                        v-for="item in content"
                        :key="item"
                      >{{item.text}} {{item.price}}</v-card-text>
                      <v-divider></v-divider>
                       <v-btn text @click="show = !show">cancel</v-btn>
                    </div>
                  </v-expand-transition>
                </v-card>
              </v-flex>
            </v-layout>
          </v-container>
        </v-card>
      </v-card>
      <v-card>
      <v-toolbar pa-0 class="hidden-md-and-up pa-0 ma-0">
        <v-btn icon>
          <v-app-bar-nav-icon></v-app-bar-nav-icon>
        </v-btn>
        <v-toolbar-title class="grey--text">
          <v-tabs color="pink">
            <v-tab>My Bookings</v-tab>
            <v-tab>Cancelled Bookings</v-tab>
            <v-tab>Booking History</v-tab>
          </v-tabs>
        </v-toolbar-title>
      </v-toolbar>
      <div class="hidden-md-and-up">
          <v-flex order-md2 order-xs1 class="ma-2 mr-3">
                <v-card class="mx-auto pa-2 ma-2" color="grey lighten-4">
                  <v-card-title>
                    <v-avatar>
                      <v-icon large>person</v-icon>
                    </v-avatar>
                    <div>{{data_content[0].name}}</div>
                    <span class="grey--text subtitle-2">Photographer</span>
                  </v-card-title>

                  <v-card-actions>
                    <v-flex>
                        <span>July 20 2019</span>
                      </v-flex>
                      <v-icon @click="show1 = !show1">{{ show1 ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
                     <v-btn style="padding-left:50px;" class="text-right" text>OTP:<v-chip> {{data_content[0].otp}} </v-chip> </v-btn>
                  </v-card-actions>

                <v-expand-transition>
                    <div v-show="show1">
                      <v-card-text
                        color="white"
                        v-for="item in content"
                        :key="item"
                      >{{item.text}} {{item.price}}</v-card-text>
                      <v-divider></v-divider>
                       <v-btn text @click="show = !show">cancel</v-btn>
                    </div>
                  </v-expand-transition>
                </v-card>
              </v-flex>
              <v-flex order-md3 order-xs2 class="ma-2 mr-3">
                <v-card class="mx-auto pa-2 ma-2" color="grey lighten-4">
                  <v-card-title>
                    <v-avatar>
                      <v-icon large>person</v-icon>
                    </v-avatar>&nbsp;&nbsp;&nbsp;
                    <div>{{data_content[1].name}} </div><span class="grey--text subtitle-2">Photographer</span>
                  </v-card-title>

                  <v-card-actions>
                    <v-flex class="mx-auto">
                        <p >July 20 2019</p>
                      </v-flex>

                      <v-icon @click="show = !show">{{ show ? 'keyboard_arrow_down' : 'keyboard_arrow_up' }}</v-icon>
                    <v-btn text style="padding-left:50px;"> OTP: <v-chip>{{data_content[1].otp}} </v-chip> </v-btn>
                  </v-card-actions>

                 <v-expand-transition>
                    <div v-show="show">
                      <v-card-text
                        color="white"
                        v-for="item in content"
                        :key="item"
                      >{{item.text}} {{item.price}}</v-card-text>
                      <v-divider></v-divider>
                       <v-btn text @click="show = !show">cancel</v-btn>
                    </div>
                  </v-expand-transition>
                </v-card>
              </v-flex>
      </div>
      </v-card>
    </template>
  </v-app>
</template>

<script>
import HelloWorld from "./components/HelloWorld";
export default {
  name: "App",
  components: {
    HelloWorld
  },
  data() {
    return {
      show: false,
      show1: false,
      a: "cccc",

      data_content: [
        {
          name: "Raul Singh",
          otp: 4638
        },
        {
          name: "Ritik Verma",
          otp: 3801
        }
      ],
      content: [
        {
          text: "Profile Photo Shoot (1 Photo Softcopy)",
          price: 50
        },
        {
          text: "The Goodbye Shoot (10 Softcopy)",
          price: 800
        },
        {
          text: "The Goodbye Shoot (20 Softcopy)",
          price: 1200
        }
      ]
    };
  }
};
</script>
<style>
.container1 {
  padding: 16px !important;
}
</style>

