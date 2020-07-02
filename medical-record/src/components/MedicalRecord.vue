<template>
    <v-container 
        class="mt-16 px-16 fill-height"
        fluid
    >
        <v-row
            justify="center"
            align="center"
        >
            <v-col cols="1">
                <v-btn 
                    dark 
                    fab 
                    color="#1d3557" 
                    large
                    @click="changeComponent"
                >
                    <v-icon large>mdi-chevron-left</v-icon>
                </v-btn>
            </v-col>
            <v-col cols='11'>
                <v-card
                    class="pa-8"
                >
                    <v-row no-gutters>
                        <v-col cols="6">
                            <p><b>Paciente:</b> {{medicalRecord.pacientName}}</p>
                        </v-col>
                        <v-col cols="6">
                            <p><b>Nascimento:</b> {{medicalRecord.pacientBirthDate}}</p>
                        </v-col>
                    </v-row>
                    <v-row no-gutters>
                        <v-col cols="12">
                            <p><b>Número do Atedimento:</b> {{attendance.number}}</p>
                        </v-col>
                    </v-row>
                    <v-row>
                        <v-col cols="12">
                            <h4>Características Gerais e obstétricas:</h4>
                        </v-col>
                    </v-row>
                    <v-row no-gutters>
                        <v-col cols="3">
                            <v-card outlined tile class="pl-2 pt-2">
                                <p><b>Tipo sanguíneo:</b> {{attendance.bloodType}}</p>                     
                            </v-card>
                        </v-col>
                        <v-col cols="3">
                            <v-card outlined tile class="pl-2 pt-2">
                                <p><b>Fator RH:</b> {{attendance.rhFactor}}</p>                     
                            </v-card>                  
                        </v-col>
                        <v-col cols="3">
                            <v-card outlined tile class="pl-2 pt-2">
                                <p><b>Protocolo de laqueadura:</b> {{attendance.sterilization}}</p>                     
                            </v-card>                               
                        </v-col> 
                        <v-col cols="3">
                            <v-card outlined tile class="pl-2 pt-2">
                                <p><b>Gestação:</b> {{attendance.gestation}}</p>                      
                            </v-card>                      
                        </v-col>
                        <v-col cols="3">
                            <v-card outlined tile class="pl-2 pt-2">
                                <p><b>Parto:</b> {{attendance.childBirth}}</p>                      
                            </v-card>                     
                        </v-col>                  
                        <v-col cols="3">
                            <v-card outlined tile class="pl-2 pt-2">  
                                <p><b>Aborto:</b> {{attendance.abortion}}</p>                      
                            </v-card>                     
                        </v-col>  
                        <v-col cols="3">
                            <v-card outlined tile class="pl-2 pt-2">     
                                <p><b>Realizou pré-natal?</b> {{attendance.prenatal}}</p>                      
                            </v-card>                     
                        </v-col>
                        <v-col cols="3">
                            <v-card outlined tile class="pl-2 pt-2">     
                                <p><b>Parto Multiplo?</b> {{attendance.multipleDelivery}}</p>                      
                            </v-card>                     
                        </v-col>
                        <v-col cols="4">
                            <v-card outlined tile class="pl-2 pt-2">     
                                <p><b>IG por tempo:</b> {{attendance.GAperTime}}</p>                      
                            </v-card>                      
                        </v-col>
                        <v-col cols="4">
                            <v-card outlined tile class="pl-2 pt-2">     
                                <p><b>DUM:</b> {{attendance.DUM}}</p>                     
                            </v-card>                     
                        </v-col>
                        <v-col cols="4">
                            <v-card outlined tile class="pl-2 pt-2">     
                                <p><b>IG por USG:</b> {{attendance.GAperUSG}}</p>                     
                            </v-card>                 
                        </v-col>
                    </v-row>
                    <v-row>
                        <v-col cols="12">
                            <p><b>Encaminhamento:</b> {{attendance.referral.name}}</p>
                        </v-col>
                    </v-row>
                    <v-row>
                        <v-col cols="6">
                            <h5>Negação</h5>
                            <v-simple-table class="elevation-0 teal lighten-5">
                                <thead>
                                    <tr>
                                        <th class="text-left">Código</th>
                                        <th class="text-left">Negação</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="denial in attendance.denials" :key="denial.id">
                                        <th class="text-left">{{denial.id}}</th>
                                        <th class="text-left">{{denial.name}}</th>
                                    </tr>
                                </tbody>
                            </v-simple-table>
                            <p></p>
                            <h5>Alergia</h5>
                            <v-simple-table class="elevation-0 teal lighten-5">
                                <thead>
                                    <tr>
                                        <th class="text-left">Código</th>
                                        <th class="text-left">Alergia</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="allergy in attendance.allergies" :key="allergy.id">
                                        <th class="text-left">{{allergy.id}}</th>
                                        <th class="text-left">{{allergy.name}}</th>
                                    </tr>
                                </tbody>
                            </v-simple-table>
                            <p></p>
                            <h5>Medicamento administrado</h5>
                            <v-simple-table class="elevation-0 teal lighten-5">
                                <thead>
                                    <tr>
                                        <th class="text-left">Código</th>
                                        <th class="text-left">Medicamento</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="medicine in attendance.medicines.administered" :key="medicine.id">
                                        <th class="text-left">{{medicine.id}}</th>
                                        <th class="text-left">{{medicine.name}}</th>
                                    </tr>
                                </tbody>
                            </v-simple-table>
                            <p></p>
                            <h5>Conduta</h5>
                            <v-simple-table class="elevation-0 teal lighten-5">
                                <thead>
                                    <tr>
                                        <th class="text-left">Código</th>
                                        <th class="text-left">Conduta</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="conduct in attendance.conducts" :key="conduct.id">
                                        <th class="text-left">{{conduct.id}}</th>
                                        <th class="text-left">{{conduct.name}}</th>
                                    </tr>
                                </tbody>
                            </v-simple-table>
                        </v-col>
                        <v-col cols="6">
                            <h5>Sintomas</h5>
                            <v-simple-table class="elevation-0 teal lighten-5">
                                <thead>
                                    <tr>
                                        <th class="text-left">Código</th>
                                        <th class="text-left">Sintomas</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="symptom in attendance.symptoms" :key="symptom.id">
                                        <th class="text-left">{{symptom.id}}</th>
                                        <th class="text-left">{{symptom.name}}</th>
                                    </tr>
                                </tbody>
                            </v-simple-table>
                            <p></p>
                            <h5>Medicamento em uso</h5>
                            <v-simple-table class="elevation-0 teal lighten-5">
                                <thead>
                                    <tr>
                                        <th class="text-left">Código</th>
                                        <th class="text-left">Medicamento</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="medicine in attendance.medicines.inUse" :key="medicine.id">
                                        <th class="text-left">{{medicine.id}}</th>
                                        <th class="text-left">{{medicine.name}}</th>
                                    </tr>
                                </tbody>
                            </v-simple-table>
                            <p></p>
                            <h5>Medicamento prescrito</h5>
                            <v-simple-table class="elevation-0 teal lighten-5">
                                <thead>
                                    <tr>
                                        <th class="text-left">Código</th>
                                        <th class="text-left">Medicamento</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="medicine in attendance.medicines.prescribed" :key="medicine.id">
                                        <th class="text-left">{{medicine.id}}</th>
                                        <th class="text-left">{{medicine.name}}</th>
                                    </tr>
                                </tbody>
                            </v-simple-table>
                            <p></p>
                            <h5>Droga</h5>
                            <v-simple-table class="elevation-0 teal lighten-5">
                                <thead>
                                    <tr>
                                        <th class="text-left">Código</th>
                                        <th class="text-left">Droga</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="drugs in attendance.drugss" :key="drugs.id">
                                        <th class="text-left">{{drugs.id}}</th>
                                        <th class="text-left">{{drugs.name}}</th>
                                    </tr>
                                </tbody>
                            </v-simple-table>
                        </v-col>
                    </v-row>
                    <v-row>
                        <v-col cols="12">
                            <h5>Comorbidade/Doença</h5>
                            <v-simple-table class="elevation-0 teal lighten-5">
                                <thead>
                                    <tr>
                                        <th class="text-left">Código</th>
                                        <th class="text-left">Comorbidade/Doença</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="disease in attendance.diseases" :key="disease.id">
                                        <th class="text-left">{{disease.id}}</th>
                                        <th class="text-left">{{disease.name}}</th>
                                    </tr>
                                </tbody>
                            </v-simple-table>
                        </v-col>
                    </v-row>
                    <v-row>
                        <v-col cols="12">
                            <h5>Exames</h5>
                            <v-simple-table class="elevation-0 teal lighten-5">
                                <thead>
                                    <tr>
                                        <th class="text-left">Código</th>
                                        <th class="text-left">Exame</th>
                                        <th class="text-left">Resultado</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr v-for="exam in attendance.exams.numeric" :key="exam.id">
                                        <th class="text-left">{{exam.id}}</th>
                                        <th class="text-left">{{exam.name}}</th>
                                        <th class="text-left">{{exam.result}}</th>
                                    </tr>
                                    <tr v-for="exam in attendance.exams.choice" :key="exam.id">
                                        <th class="text-left">{{exam.id}}</th>
                                        <th class="text-left">{{exam.name}}</th>
                                        <th class="text-left">{{exam.result}}</th>
                                    </tr>
                                    <tr v-for="exam in attendance.exams.charbool" :key="exam.id">
                                        <th class="text-left">{{exam.id}}</th>
                                        <th class="text-left">{{exam.name}}</th>
                                        <th class="text-left">{{exam.result}}</th>
                                    </tr>
                                </tbody>
                            </v-simple-table>
                        </v-col>
                    </v-row>
                </v-card>
            </v-col>
        </v-row>
    </v-container>
</template>

<script>
    export default {
        name: 'MedicalRecord',    

        props: {
            attendance : {
                type : Object,
            },
            medicalRecord : {
                type : Object,
            }
        },

        data: () => ({

        }),
    
        methods: {
            //emitindo para App que é necessário mudar o component renderizado
            changeComponent(){
                this.$emit("change-component")
            }
        },
    }
</script>