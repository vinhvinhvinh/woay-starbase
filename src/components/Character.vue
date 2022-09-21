<template>
    <div class="char-card p-3" @click="switchChar">
       <h6>Name: {{character.name}}</h6>
       <p class="card-text">Heihgt: {{character.height}}cm</p>
       <p class="card-text">Mass: {{character.mass}}kg</p>
       <p class="card-text">Hair Color: {{character.hair_color}}</p>
       <p class="card-text">Eye Color: {{character.eye_color}}</p>
    </div>
</template>


<script>


export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name:'Character',
  data(){
    return {
        character:{}
    }
  },
    props:['id'],
    methods:{
        getData(id){
            fetch(`https://swapi.dev/api/people/${id}`,{method:'GET'})
            .then(res=>res.json())
            .then(json=>{
                console.log(json);
                return this.character=json
            });
        },
    switchChar(){
        let randomId=Math.floor(Math.random()*10)+1;
        this.getData(randomId);
    }
  },
  created(){
    this.getData(this.id);
  },
}
</script>

<style>
.char-card{
    width:360px;
    border: 1px solid #02835a;
    border-radius: 4px;
    cursor: pointer;
}
</style>