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
        v-model="selectedMedicalRecord"
        label="Número do Prontuário"
        flat
        solo-inverted
        hide-details
        prepend-inner-icon="mdi-magnify"
        @keyup.enter="setMedicalRecord"
      ></v-text-field>
    </v-app-bar>
    <component v-if="currentComponent != null"
      :attendance="currentAttendance"
      :medicalRecord="currentMedicalRecord"
      :is="currentComponent"
      @set-attendance="setAttendance"
      @change-component="changeComponent"
    >
    </component>
  </v-app>
</template>

<script>
import Attendances from "./components/Attendances.vue" 
import MedicalRecord from "./components/MedicalRecord.vue"
import data from "./assets/data.json"

export default {
  name: 'App',

  components: {
    Attendances,
    MedicalRecord,   
  },

  data: () => ({
    selectedMedicalRecord: null,
    currentMedicalRecord: null,
    currentComponent : null,
    currentAttendance : null,
    medicalRecords : data,
  }),

  methods : {
    changeComponent(){
      this.currentComponent == MedicalRecord ? (this.currentComponent = Attendances) : (this.currentComponent = MedicalRecord) 
    },

    setAttendance(attendance) {
      this.currentComponent = MedicalRecord
      this.currentAttendance = attendance
    },

    setMedicalRecord() {
      if(Object.prototype.hasOwnProperty.call(this.medicalRecords, this.selectedMedicalRecord)){
        this.currentComponent = Attendances
        this.currentMedicalRecord = this.medicalRecords[this.selectedMedicalRecord]
        this.attendancesList = this.medicalRecords[this.selectedMedicalRecord].attendances
      } else {
        alert("Insira um valor válido!")
      }
    }
  }
};
</script>
