<template>
  <v-container 
    class="mt-16 fill-height"
    fluid
  >
    <v-row 
      justify="center"
    >
      <v-card 
        class="pa-16"
        width="800px"
      >
        <v-row no-gutters>
          <v-col cols="6">
            <p><b>Paciente:</b> {{medicalRecord.pacientName}}</p>
          </v-col>
          <v-col cols="6">
            <p><b>Nascimento:</b> {{medicalRecord.pacientBirthDate}}</p>
          </v-col>
        </v-row>
        <v-row>
          <v-col cols="12">
            <p><b>Resultado</b></p>
          </v-col>
        </v-row>
        <v-simple-table>
          <template v-slot:default>  
            <thead>
              <tr>
                <th class="text-left">Atendimento</th>
                <th class="text-left">Internação</th>
                <th class="text-left">Alta</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="attendance in medicalRecord.attendances" :key="attendance.number"
                @click="setAttendance(attendance)"
              >
                <td>{{ attendance.number }}</td>
                <td>{{ attendance.entryDate }}</td>
                <td>{{ attendance.dischargeDate }}</td>
              </tr>
            </tbody>
          </template>
        </v-simple-table>
      </v-card>
    </v-row>
  </v-container>
</template>

<script>
  export default {
    name: 'Attendances',

    props: {
      medicalRecord: {
        type: Object
      }
    },

    data: () => ({
    }),

    methods: {
      //emitindo para App o atendimento escolhido pelo usuário
      setAttendance(attendance){
        this.$emit('set-attendance', attendance)
      }
    }
  }
</script>
