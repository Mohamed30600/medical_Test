<!-- <template>
    <div id="app">
       
      <main>
        
        <label for="healthIndex">Entrez l'index de santé :</label>
        <input v-model="healthIndex" type="text" id="healthIndex" />
        <button class="btn btn-primary" @click="diagnostic">Simulation du retour de l'index du capteur</button>
        <div v-if="result !== null">
          <p>Résultat du diagnostic : {{ result }}</p>
        </div>
      </main>
    </div>
  </template> -->
  <template>
    <blockquote class="blockquote text-center mt-5">
        <h2 >Saisir l'index de santer pour savoir ou le patient sera rediriger:</h2>
    </blockquote>
    
    <div>
      <div class="container mt-4">
        <div class="input-group mb-3">
          <div class="input-group-prepend">
            <button @click="diagnostic" class="btn btn-outline-secondary " type="button">Button</button>
        </div>
        <label for="healthIndex"></label>
        <input  v-model="healthIndex" type="text" id="healthIndex"  class="form-control " placeholder="index de santé a saisir" aria-label="" aria-describedby="basic-addon1" >
        </div>
        <div v-if="result !== null">
            <div class="row mt-5">
           <h5>la patient doit etre rediriger dans le ou les services: {{ result }}</h5>

            </div>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
import { ref } from 'vue';

const healthIndex = ref('');
const result = ref(null);

const diagnostic = async () => {
  try {
    const response = await fetch(`http://localhost:8080/softwayMedical/diagnostic?indexSante=${healthIndex.value}`);
    const data = await response.json();
    result.value = data.result;
    healthIndex.value = ''
  } catch (error) {
    console.error("Erreur lors du diagnostic", error);
  }
};
</script>

<style scoped>

</style>

  