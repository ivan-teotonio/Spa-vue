<template>
	<div>

		<b-container fluid="sm">
 


		  <b-button v-b-modal.modal-1>Adicionar Usuário</b-button>
		  <b-modal id="modal-1" title="Cadastrar Usúario">
		    
		    <div class="row mt-2">
		     	
		     	<div class="col-6">
		     		 <b-form-input v-model="nome" placeholder="Name"></b-form-input>
		     		 
		     	</div>
		     	
		     	<div class="col-6">
		     		<b-form-input v-model="email" placeholder="E-mail"></b-form-input>
		     		{{ email }}
		     	</div>

		     </div>

		     <div class="row mt-2">
		     	
		     	<div class="col-6">
		     		 <b-form-input v-model="phone" placeholder="Telefone"></b-form-input>
		     	</div>
		     	
		     	<div class="col-6">
		     		<b-form-input v-model="password"  placeholder="Senha"></b-form-input>
		     	</div>

		     </div>

		     <div class="row mt-2">
		     	
		     	<div class="col-12">
		     		 <b-form-file v-model="photo" plain></b-form-file>
		     	</div>
		     
		     </div>

		     <div class="row mt-4">
		     	<div class="col-12">
		     		<b-button @click="addUsuario" block variant="primary">Salvar</b-button>
		     	</div>
		     </div>

		  </b-modal>
            
          
		 <table class="table">
  <thead>
    <tr>
      <th scope="col">Foto</th>
      <th scope="col">Nome</th>
      <th scope="col">E-mail</th>
      <th scope="col">Telefone</th>
      <th scope="col">Ações</th>
      
    </tr>
  </thead>
  <tbody>

    <tr v-for="user in listagem" :key="user.id">
      <td>{{ user.photo }}</td>
      <td>{{ user.nome }}</td>
      <td>{{ user.email }}</td>
      <td>{{ user.phone }}</td>
      <td><b-button variant="outline-primary">Editar</b-button></td>
    </tr>
   
  </tbody>
</table>

	</b-container>

	</div>
</template>


<script>

	export default{

		data(){
			return{
				listagem:[],
				nome:'',
				email:'',
				phone:'',
				password:'',
				photo:''
			}
		},
		methods: {
			adicionarListagem(){

			},
			addUsuario(){
				let data = {
				   nome:this.nome,
				   email:this.email,
				   phone:this.phone,
				   password:this.password,
				   photo:this.photo
				}
				this.$http.post('adicionar',data).then((response) =>{
					console.log(response)
				})
				
				this.listagem.push({
					nome:this.nome,
					email:this.email,
					phone:this.phone,
					password:this.password,
					photo:this.photo
				})
			}
		},
		created(){
			let list = [
			 { photo: 'ana.png',
			   nome: 'Ana',
			   email: 'ana@gmail.com',
			   phone: '98765342',
			   id:1 }

			];
			this.listagem = list;
		}
	}
	
</script>


<style lang="scss" scoped>
	
</style>