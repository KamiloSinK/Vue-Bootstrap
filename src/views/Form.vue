<template>
    <div class="mt-5">
        <h1>Formularios</h1>

        <form>
            <b-row>
                <b-col md="3">
                    <b-form-input type="text" v-model="texto" :state="comprobar"></b-form-input>
                    <small>Minimo 3 caracteres</small>
                    <p>Texto: {{texto}}</p>
                </b-col>
                <b-col md="3">
                    <b-form-select v-model="select" :options="animales"></b-form-select>
                    <p>Seleccion: {{select}}</p>
                </b-col>
                <b-col md="3">
                    <b-form-radio-group v-model="radio" :options="animal2"></b-form-radio-group>
                    <p>Elijes: {{radio}}</p>
                </b-col>
                <b-col md="3">
                    <b-form-checkbox-group v-model="check" :options="animal2"></b-form-checkbox-group>
                    <p>Opciones: {{check}}</p>
                </b-col>
            </b-row>
        </form>
    </div>
</template>

<script>
export default {
    name: 'Form',
    data(){
        return{
            texto: '',
            radio: '',
            check: [],
            select: null,
            animales: [
                {value: null, text: 'Elija un Animal'},
                {value: 'perro', text: 'Guau'},
                {value: 'gato', text: 'Miau'},
                {value: 'pato', text: 'Cuack'}
            ],
            animal2: [
                {value: 'perro', text: 'Guau'},
                {value: 'gato', text: 'Miau'},
                {value: 'pato', text: 'Cuack'}
            ]
        }
    },
    computed:{
        comprobar(){
            return this.texto.length > 2 ? true : false;
        }
    }
}
</script>