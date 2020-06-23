<template>
  <v-container 
    class="mt-16 fill-height"
    fluid
    color="#f9fbf2"
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
              <tr>
                <th class="text-left">Atendimento</th>
                <th class="text-left">Internação</th>
                <th class="text-left">Alta</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item, index) in parentAttendances" :key="index"
                @click="algumacoisa"
              >
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
      parentAttendances: {
        type: Object
      }
    },

    data: () => ({
    }),

    methods: {
      algumacoisa(){
        console.log("Isso")
      }
    }
  }
</script>
