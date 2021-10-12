<template>
<div>
  <Header/>
  <DashboardLayout>
    <template v-slot:mainContent>
      <div class="analysis">
        <div style="margin-right: 1rem" class="analysisCard">
          <span class="title">Total saving</span>
          <span class="figures">30,750</span>
        </div>
        <div style="margin-right: 1rem" class="analysisCard">
          <span class="title">Total D/L</span>
          <span class="figures">100,000</span>
        </div>
        <div class="analysisCard">
          <span class="title">Total B/L</span>
          <span class="figures">100,000</span>
        </div>
      </div>
      <div class="d-flex justify-space-between align-center mb-4">
        <div></div>
        <div>
          <v-dialog
              v-model="dialog"
              persistent
              max-width="600px"
          >
            <template v-slot:activator="{ on, attrs }">
              <v-btn
                  color="#03a84e"
                  dark
                  v-bind="attrs"
                  v-on="on"
              >
                Create New Member
              </v-btn>
            </template>
            <v-card>
              <v-card-title>
                <span class="text-h5">Member Profile</span>
              </v-card-title>
              <v-card-text>
                <v-container>
                  <v-row>
                    <v-col cols="12"
                           sm="6"
                           md="4">
                      <v-container grid-list-xl>
                        <ImageInput v-model="avatar">
                          <div slot="activator">
                            <v-avatar size="150px" v-ripple v-if="!avatar" class="grey lighten-3 mb-3">
                              <span>Click to add avatar</span>
                            </v-avatar>
                            <v-avatar size="150px" v-ripple v-else class="mb-3">
                              <img :src="avatar.imageURL" alt="avatar">
                            </v-avatar>
                          </div>
                        </ImageInput>
                        <v-slide-x-transition>
                          <div v-if="avatar && saved == false">
                            <v-btn  color="#03a84e" @click="uploadImage" :loading="saving">Save Avatar</v-btn>
                          </div>
                        </v-slide-x-transition>
                      </v-container>
                    </v-col>
                    <v-col
                        cols="12"
                        sm="6"
                        md="4"
                    >
                      <v-text-field
                          color="#03a84e"
                          label="First name*"
                          required
                      ></v-text-field>
                    </v-col>
                    <v-col
                        cols="12"
                        sm="6"
                        md="4"
                    >
                      <v-text-field
                          color="#03a84e"
                          label="Last name"
                      ></v-text-field>
                    </v-col>
                    <v-col
                        cols="12"
                        sm="6"
                        md="4"
                    >
                      <v-text-field
                          color="#03a84e"
                          label="Card Number*"
                          persistent-hint
                          required
                      ></v-text-field>
                    </v-col>
                    <v-col
                        cols="12"
                        sm="6"
                    >
                      <v-text-field
                          color="#03a84e"
                          label="Total Saving*"
                          required
                      ></v-text-field>
                    </v-col>
                    <v-col
                        cols="12"
                        sm="6"
                    >
                      <v-text-field
                          color="#03a84e"

                          label="Amount Paid"
                          required
                      ></v-text-field>
                    </v-col>
                  </v-row>
                </v-container>
                <small>*indicates required field</small>
              </v-card-text>
              <v-card-actions>
                <v-spacer></v-spacer>
                <v-btn
                    color="#03a84e"
                    text
                    @click="dialog = false"
                >
                  Close
                </v-btn>
                <v-btn
                    color="#03a84e"
                    text
                    @click="dialog = false"
                >
                  Save
                </v-btn>
              </v-card-actions>
            </v-card>
          </v-dialog>
        </div>
      </div>
      <div class="card-table mt-7">
        <div class="d-flex justify-space-between mb-4">
          <h4>Member-name</h4>
          <div>
            <span>Click to view details</span>
          </div>
        </div>
        <v-expansion-panels>
          <v-expansion-panel style="margin-bottom: 0.8rem; border-radius: 10px"
              v-for="(name,i) in 5"
              :key="i"
          >
            <v-expansion-panel-header >
              <div class="d-flex align-center">
                <v-avatar
                    size="36px"
                >
                  <img
                      alt="Avatar"
                      src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
                  >
                </v-avatar>
                <h5 style="margin-left: 0.5rem">kemi AJALA</h5>

              </div>
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </div>

    </template>
  </DashboardLayout>

</div>

</template>

<script>

import Header from "../components/resusable/Header";
import DashboardLayout from "../components/resusable/DashboardLayout";
import ImageInput from "../components/ImageInput";
export default {
  name: "BranchDetails",
  components: {ImageInput, DashboardLayout, Header,},
  data () {
    return {
      dialog: false,
      avatar: null,
      saving: false,
      saved: false
    }
  },
  watch:{
    avatar: {
      handler: function() {
        this.saved = false
      },
      deep: true
    }
  },
  methods: {
    uploadImage() {
      this.saving = true
      setTimeout(() => this.savedAvatar(), 1000)
    },
    savedAvatar() {
      this.saving = false
      this.saved = true
    }
  }
}
</script>

<style scoped lang="scss">
.analysis {
  display: flex;
  justify-content: space-between;
  flex-direction: row;
  margin-bottom: 1rem;
  @media (max-width: 450px) {
    flex-direction: column;
  }
}
.analysisCard{
  height: 95px;
  min-width: 100px;
  width: 100%;
  background: #03a84e;
  border-radius: 18px;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  box-shadow: 0 8px 16px #F0F9FF ;
  @media (max-width: 450px) {
    margin-bottom: 1rem;
  }
  .title {
    font-size: 15px;
    color: #fdd384;
  }
  .figures {
    font-size: 30px;
    font-weight: bolder;
    color: #ffffff;
  }
}

.imgDiv{
  width: 40px;
  height: 40px;

  img{
    width: 100%;
    height: 100%;
    border-radius: 100%;
    object-fit: contain;
  }
}


</style>