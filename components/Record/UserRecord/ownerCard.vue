<template>
  <v-card class="elevation-5">
    <v-card-title>ข้อมูลเจ้าของสัตว์</v-card-title>
    <v-divider class="darker-divider"></v-divider>
    <div class="px-10 py-5">
      <v-row no-gutters>
        <v-col lg="1" md="2" sm="3" cols="4">
          <v-row no-gutters>
            <v-col cols="12">
              <v-avatar size="100">
                <v-img :src="require('~/assets/profile/001-user.svg')"></v-img>
              </v-avatar>
            </v-col>
            <v-col cols="12">
              <v-menu offset-y nudge-left="80">
                <template v-slot:activator="{ on, attrs }">
                  <v-btn
                    class="mx-7"
                    color="cusblue2"
                    dark
                    v-bind="attrs"
                    icon
                    depressed
                    large
                    v-on="on"
                  >
                    <v-icon>mdi-dots-horizontal-circle</v-icon>
                  </v-btn>
                </template>

                <v-list width="200">
                  <v-list-item>
                    <h4>Action</h4>
                  </v-list-item>
                  <v-divider></v-divider>
                  <v-btn
                    v-for="actionBtn in actionBtns"
                    :key="actionBtn.text"
                    class="cusblue2--text"
                    block
                    text
                    tile
                    >{{ actionBtn.text }}</v-btn
                  >
                </v-list>
              </v-menu>
            </v-col>
          </v-row>
        </v-col>
        <v-col class="pa-6" lg="11" md="10" sm="9" cols="8">
          <v-row no-gutters>
            <v-col cols="12">
              <div class="font-weight-medium">{{ owner.name }}</div>
            </v-col>
            <v-col lg="3" md="6" cols="12">
              <span class="font-weight-medium">เบอร์ติดต่อ :</span>
              <span class="font-weight-light">{{ owner.tel }}</span>
            </v-col>
            <v-col lg="4" md="6" cols="12">
              <span class="font-weight-medium">Email :</span>
              <span class="font-weight-light">{{ owner.email }}</span>
            </v-col>
            <v-col lg="5" md="12" cols="12">
              <span class="font-weight-medium">ที่อยู่ :</span>
              <span class="font-weight-light">{{ owner.address }}</span>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </div>
  </v-card>
</template>

<script>
export default {
  props: {
    owner: {
      default: null,
      type: Object,
      required: false,
    },
  },
  data() {
    return {
      actionBtns: [
        { text: 'แก้ไขข้อมูล', action: '' },
        { text: 'ลบข้อมูล', action: '' },
      ],
    }
  },
}
</script>
