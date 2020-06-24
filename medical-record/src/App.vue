<template>
  <v-app style="
    background: linear-gradient(to top, #f1faee, #a8dadc, #457b9d);
  ">
    <v-app-bar
      color="#1d3557" 
      app
      dark
      hide-on-scroll
    >
      <v-toolbar-title>Prontuários</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-text-field
        name="medical-record"
        label="Número do Prontuário"
        flat
        solo-inverted
        hide-details
        prepend-inner-icon="mdi-magnify"
        @keyup.enter="searchMedicalRecord"
      ></v-text-field>
    </v-app-bar>
    <component v-if="currentComponent != null"
      :parentAttendances="attendancesList" 
      :is="currentComponent"
      @set-attendance="setAttendance"
    >
    </component>
  </v-app>
</template>

<script>
import Attendances from "./components/Attendances.vue" 
import MedicalRecord from "./components/MedicalRecord.vue"

export default {
  name: 'App',

  components: {
    Attendances,
    MedicalRecord,   
  },

  data: () => ({
    attendancesList : [
        {
          number : "123400",
          entryDate : "19-05-2020",
          dischargeDate : "19-06-2020",
        },
        {
          number : "220029",
          entryDate : "07-01-2019",
          dischargeDate : "15-01-2019",
        },
      ],
      currentComponent : null,
  }),

  methods : {
    setAttendance() {
      this.currentComponent = MedicalRecord
      console.log()
    },

    searchMedicalRecord() {
      this.currentComponent = Attendances
    }
  }
};
</script>
