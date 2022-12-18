<template>
  <div>
    <v-app id="inspire">
      <span class="bg d-flex">
        <div class="header-train">
          <h1>Trains To Egypt</h1>
          <p>Save 61% on average when you buy in advance†</p>
        </div>

        <div class="booking">
          <v-card class="mx-auto" max-width="330" height="404">
            <span class="d-flex">
              <v-col cols="12" md="6">
                <v-text-field label="From" single-line filled></v-text-field>
              </v-col>
              <v-col cols="12" md="6">
                <v-text-field label="To" single-line filled></v-text-field>
              </v-col>
            </span>

            <span class="d-flex">
              <v-col cols="12" md="6">
                <v-dialog
                  ref="dialog"
                  v-model="modal"
                  :return-value.sync="date"
                  persistent
                  width="290px"
                >
                  <template v-slot:activator="{ on, attrs }">
                    <v-text-field
                      v-model="date"
                      label="Out"
                      prepend-icon="mdi-calendar"
                      readonly
                      v-bind="attrs"
                      v-on="on"
                    ></v-text-field>
                  </template>
                  <v-date-picker v-model="date" scrollable>
                    <v-spacer></v-spacer>
                    <v-btn text color="primary" @click="modal = false">
                      Cancel
                    </v-btn>
                    <v-btn
                      text
                      color="primary"
                      @click="$refs.dialog.save(date)"
                    >
                      OK
                    </v-btn>
                  </v-date-picker>
                </v-dialog>
              </v-col>

              <v-col cols="12" md="6">
                <v-dialog
                  ref="dialog"
                  v-model="modal"
                  :return-value.sync="date"
                  persistent
                  width="290px"
                >
                  <template v-slot:activator="{ on, attrs }">
                    <v-text-field
                      v-model="date"
                      label="Return"
                      prepend-icon="mdi-calendar"
                      readonly
                      v-bind="attrs"
                      v-on="on"
                    ></v-text-field>
                  </template>
                  <v-date-picker v-model="date" scrollable>
                    <v-spacer></v-spacer>
                    <v-btn text color="primary" @click="modal = false">
                      Cancel
                    </v-btn>
                    <v-btn
                      text
                      color="primary"
                      @click="$refs.dialog.save(date)"
                    >
                      OK
                    </v-btn>
                  </v-date-picker>
                </v-dialog>
              </v-col>
            </span>

            <v-col>
              <v-text-field label="Person" single-line filled></v-text-field>
            </v-col>
            <v-col cols="12" md="12">
              <v-btn
                style="
                  background-color: #00a88f;
                  color: #fff;
                  width: 100%;
                  height:55px;
                "
                >Get times and tickets
              </v-btn>
            </v-col>
          </v-card>
        </div>
      </span>

      <v-layout row justify-center>
        <v-toolbar color="white">
          <v-toolbar-title>
            <div class="logoWrapper-Na8Fx" data-testid="logo-wrapper">
              <a
                href="/"
                title="Trainline"
                class="logoLink-m6nF+"
                data-testid="trainline-logo-link"
                ><picture
                  ><source
                    srcset="
                      https://static.trainlinecontent.com/content/vul/logos/trainline-mint.svg
                    "
                    media="(min-width: 992px)" />
                  <img
                    data-testid="trainline-logo-image"
                    class="logo-oVgUw"
                    alt="Trainline logo"
                    src="https://static.trainlinecontent.com/content/vul/logos/trainline-mint.svg" /></picture
              ></a>
            </div>
          </v-toolbar-title>

          <v-spacer></v-spacer>

          <v-toolbar-items>
            <v-btn v-for="item in nav" :key="item.icon" :title="item.title">{{
              item.text
            }}</v-btn>
          </v-toolbar-items>

          <v-btn
            class="ms-3 sign"
            style="border-radius: 25px; background-color: #e7ebeb"
            >Sign in</v-btn
          >
        </v-toolbar>
      </v-layout>
    </v-app>
  </div>
  
</template>

<script>
export default {
  name: "NavbarComponent",
  data() {
    return {
      dialog: false,
      nav: [
        {
          text: "Basket",
          title: "Back to Home page",
          active: true,
        },
        {
          text: "My Bookings",
          title: "About this demo",
          active: false,
        },
      ],
      date: new Date(Date.now() - new Date().getTimezoneOffset() * 60000)
        .toISOString()
        .substr(0, 10),
    };
  },
};
</script>

<style scoped>
#inspire {
  position: relative;
}
.bg {
  width: 100%;
  height: 85%;
  position: absolute;
  top: 0;
  left: 0;
  background: url("../assets/pyramids-2371501_1280.jpg") no-repeat center center;
  background-size: cover;
  background-color: #e7ebeb;
  transform: scale(1.1);
}

.header-train {
  position: absolute;
  padding-bottom: 0;
  top: 55%;
  right: 58%;
}

.booking {
  position: absolute;
  padding-bottom: 0;
  top: 25%;
  left: 65%;
  border-radius: 10px;
}
.header-train h1 {
  color: #fff;
  font-family: Circular, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto,
    Helvetica, Arial, PingFang SC, Microsoft YaHei New, Microsoft Yahei,
    微软雅黑, STXihei, 华文细黑, sans-serif;
  letter-spacing: -0.015em;
}

.header-train p {
  color: #d3f1e8;
  font-family: Circular, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto,
    Helvetica, Arial, PingFang SC, Microsoft YaHei New, Microsoft Yahei,
    微软雅黑, STXihei, 华文细黑, sans-serif;
  font-size: 20px;
  font-weight: bold;
}

.theme--light.v-btn.v-btn--has-bg {
  background-color: #fff;
}

.theme--light.v-btn.v-btn--has-bg[data-v-688b5e20]:hover {
  background-color: #e7ebeb;
}

.v-application .white {
  border-bottom-right-radius: 40px;
}
.v-btn--is-elevated {
  box-shadow: none;
}
</style>
