<template>
    <v-container 
        class="mt-16 px-16 fill-height"
        fluid
    >
        <v-row
            justify="center"
        >
            <v-card
                class="pa-8"
            >
                <v-row no-gutters>
                    <v-col cols="6">
                        <p><b>Paciente:</b> Fulano de Tal</p>
                    </v-col>
                    <v-col cols="6">
                        <p><b>Nascimento:</b> 02-02-2002</p>
                    </v-col>
                </v-row>
                <v-row no-gutters>
                    <v-col cols="12">
                        <p><b>Número do Atedimento:</b> 123400</p>
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
                            <p><b>Tipo sanguíneo:</b> O</p>                     
                        </v-card>
                    </v-col>
                    <v-col cols="3">
                        <v-card outlined tile class="pl-2 pt-2">
                            <p><b>Fator RH:</b> P</p>                     
                        </v-card>                  
                    </v-col>
                    <v-col cols="3">
                        <v-card outlined tile class="pl-2 pt-2">
                            <p><b>Protocolo de laqueadura:</b> S</p>                     
                        </v-card>                               
                    </v-col> 
                    <v-col cols="3">
                        <v-card outlined tile class="pl-2 pt-2">
                             <p><b>Gestação:</b> 3</p>                      
                        </v-card>                      
                    </v-col>
                    <v-col cols="3">
                        <v-card outlined tile class="pl-2 pt-2">
                            <p><b>Parto:</b> 1</p>                      
                        </v-card>                     
                    </v-col>                  
                    <v-col cols="3">
                        <v-card outlined tile class="pl-2 pt-2">  
                            <p><b>Aborto:</b> 1</p>                      
                        </v-card>                     
                    </v-col>  
                    <v-col cols="3">
                        <v-card outlined tile class="pl-2 pt-2">     
                            <p><b>Realizou pré-natal?</b> S</p>                      
                        </v-card>                     
                    </v-col>
                    <v-col cols="3">
                        <v-card outlined tile class="pl-2 pt-2">     
                            <p><b>Parto Multiplo?</b> N</p>                      
                        </v-card>                     
                    </v-col>
                    <v-col cols="4">
                        <v-card outlined tile class="pl-2 pt-2">     
                            <p><b>IG por tempo:</b> 27s 6d</p>                      
                        </v-card>                      
                    </v-col>
                    <v-col cols="4">
                        <v-card outlined tile class="pl-2 pt-2">     
                            <p><b>DUM:</b> 27-01-2020</p>                     
                        </v-card>                     
                    </v-col>
                    <v-col cols="4">
                        <v-card outlined tile class="pl-2 pt-2">     
                            <p><b>IG por USG:</b> 29s 2d</p>                     
                        </v-card>                 
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
                        </v-simple-table>
                    </v-col>
                </v-row>
            </v-card>
        </v-row>
    </v-container>
</template>

<script>
    export default {
        name: 'MedicalRecord',    

        props: {

        },

        data: () => ({

        }),
    
        methods: {

        },
    }
</script>