<template>
  <v-container 
    class="mt-16 pa-16" 
    fluid
  >
    <v-row 
      align="center"
      justify="center"
    >
      <v-card 
        class="pa-16"
        width="800px"
      >
        <v-simple-table>
          <template v-slot:default>  
            <thead>
              <th class="text-left">Atendimento</th>
              <th class="text-left">Internação</th>
              <th class="text-left">Alta</th>
            </thead>
            <tbody>
              <tr v-for="(item, index) in attendancesList" :key="index">
                <td>{{ item.number }}</td>
                <td>{{ item.entryDate }}</td>
                <td>{{ item.dischargeDate }}</td>
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
      parentAttendances : Object,
    },

    data: () => ({
      attendancesList : this.parentAttendances
    }),
  }
</script>
