<template>
  <v-container fluid class="py-0 my-0 mt-0">
    <v-row class="py-0 my-0" align="center" justify="center">
      <v-col md="12" sm="12" cols="12" class="py-0 my-0">
        <v-row class="py-0">
          <v-col cols="12" md="12" sm="12" lg="12" class="py-0">
            <v-row class="py-0">
              <v-col cols="12" md="12" class="pa-0">
               <div class="wistia_responsive_padding" style="padding:56.25% 0 0 0;position:relative;"><div class="wistia_responsive_wrapper" style="height:100%;left:0;position:absolute;top:0;width:100%;"><div class="wistia_embed wistia_async_mbrsjv0thn seo=false videoFoam=true" style="height:100%;position:relative;width:100%"><div class="wistia_swatch" style="height:100%;left:0;opacity:0;overflow:hidden;position:absolute;top:0;transition:opacity 200ms;width:100%;"><img src="https://fast.wistia.com/embed/medias/mbrsjv0thn/swatch" style="filter:blur(5px);height:100%;object-fit:contain;width:100%;" alt="" aria-hidden="true" onload="this.parentNode.style.opacity=1;" /></div></div></div></div>
                <!-- <v-img
                  :src="getImgUrl(data.image, 'eventbanner.jpg')"
                  :lazy-src="getImgUrl(data.image, 'eventbanner.jpg')"
                  width="100%"
                  cover
                  style="border-top-left-radius:5px;"
                  gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,1)"
                  height="300px"
                >
                  <template v-slot:placeholder>
                    <v-row class="fill-height ma-0" align="center" justify="center">
                      <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                    </v-row>
                  </template>
                  <v-card-title class="fill-height align-end google-font pb-5 white--text">
                    <p>
                      <span style="font-size:150%">{{data.name}}</span>
                    </p>
                  </v-card-title>
                  <v-layout slot="placeholder" fill-height align-center justify-center ma-0>
                    <v-progress-circular indeterminate color="grey lighten-5"></v-progress-circular>
                  </v-layout>
                </v-img> -->
              </v-col>
            </v-row>
            <v-row class="blue">
              <!-- {{data}} -->
              <v-col cols="12" md="12" class="pa-0">
                <v-tabs
                  v-model="tab"
                  grow
                  :background-color="this.$vuetify.theme.dark == true?'grey darken-4':'primary'"
                  dark
                  class="elevation-0"
                  :prev-icon="prevIcon ? 'mdi-arrow-left-bold-box-outline' : undefined"
                  :next-icon="nextIcon ? 'mdi-arrow-right-bold-box-outline' : undefined"
                  :icons-and-text="icons"
                >
                  <v-tabs-slider></v-tabs-slider>

                  <v-tab v-for="item in items" :key="item">{{item}}</v-tab>

                  <v-tabs-items v-model="tab">
                    <v-tab-item class="px-5">
                      <v-card flat color="basil">
                        <LayoutAbout :data="data" />
                      </v-card>
                    </v-tab-item>

                    <v-tab-item class="px-5">
                      <v-card flat color="basil">
                        <LayoutSpeakers :data="data" />
                      </v-card>
                    </v-tab-item>

                    <v-tab-item class="px-5">
                      <v-card flat color="basil">
                        <LayoutAgenda :data="data" />
                      </v-card>
                    </v-tab-item>

                    <v-tab-item class="px-5">
                      <v-card flat color="basil">
                        <LayoutPartners :data="data" />
                      </v-card>
                    </v-tab-item>
                  </v-tabs-items>
                </v-tabs>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  components: {
    LayoutAbout: () => import("@/views/Events/layout/sublayout/LayoutAbout"),
    LayoutSpeakers: () =>
      import("@/views/Events/layout/sublayout/LayoutSpeakers"),
    LayoutAgenda: () => import("@/views/Events/layout/sublayout/LayoutAgenda"),
    LayoutPartners: () =>
      import("@/views/Events/layout/sublayout/LayoutPartner")
  },
  props: ["data"],
  data() {
    return {
      blogsData: [],
      tab: null,
      items: ["About", "Speakers", "Agenda", "Partners"],
      icons: false,
      centered: false,
      grow: false,
      vertical: false,
      prevIcon: false,
      nextIcon: false,
      right: false,
      tabs: 3
    };
  },
  methods: {
  },
  created() {}
};
</script>