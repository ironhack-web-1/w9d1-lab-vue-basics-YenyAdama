<template>
<div>
  <div>
    <h1>Iteración 2: </h1>
    <h3>2+2 es : {{2+2}}</h3>
    <div >Haga click para devolver la cadena: {{property}}</div>
    <button @click="newFunction">Press me</button>
    <h1>Iteración 3:</h1>
  </div>
  <div v-if="x">
    Se muestra la iteración #3 de este laboratorio (True)
  </div>
  <button @click="boolFunction">True/False</button>
  <div>
    <h1>Iteración 4:</h1>
    <div v-for="i in projects" :key="i.title">
      {{i.title}}: {{i.description}}
    </div>
    <h1>Iteración 5:</h1>
    <div class="bonus" style="--color-b">
      Bonus
    </div>
    <button @click="bonusFunction">Bonus</button>

  </div>
 
</div>

  <NavBar></NavBar>
  <Footer></Footer>
</template>

<script>
import NavBar from './components/navbar.vue'
import Footer from './components/footer.vue'
export default {
  name: 'App',
  components: {
    NavBar,
    Footer
  },
  data() {
        return{
            property: null,
            x:true,
            projects:[
              {
                title:'Proyecto 1',
                description:'Acciones para el proyecto 1',
                content: 'este es el contenido del proyecto 1',
              },
              {
                title:'Proyecto 2',
                description:'Acciones para el proyecto 2',
                content: 'este es el contenido del proyecto 2',
              },
              {
                title:'Proyecto 3',
                description:'Acciones para el proyecto 3',
                content: 'este es el contenido del proyecto 3',
              },
            ],
        }
    },
    methods: {
        newFunction(){
            this.property="string"
        },
        boolFunction(){
          if(this.x==true){
            this.x=false
          } else{
            this.x=true
          }
        },
        bonusFunction(){

        },
    },
}
</script>

<style>
.bonus{
  color: white;
  background-color: var(--color-b);
}
</style>
