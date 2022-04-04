<template>
	<div>

		<b-container fluid="sm">
  


       <h1>Editar Usuário {{ this.$route.params.id }}</h1>

      
		  
		    
		    <div class="row mt-2">
		     	
		     	<div class="col-6">
		     		 <b-form-input placeholder="Name"></b-form-input>
		     		 
		     	</div>
		     	
		     	<div class="col-6">
		     		<b-form-input  placeholder="E-mail"></b-form-input>
		     		
		     	</div>

		     </div>

		     <div class="row mt-2">
		     	
		     	<div class="col-6">
		     		 <b-form-input  placeholder="Telefone"></b-form-input>
		     	</div>
		     	
		     	<div class="col-6">
		     		<b-form-input placeholder="Senha"></b-form-input>
		     	</div>

		     </div>

		     <div class="row mt-2">
		     	
		     	<div class="col-12 mt-2">
		     		 <b-form-file v-model="photo" plain></b-form-file>
		     	</div>
		     
		     </div>

		     <div class="row mt-4">
		     	<div class="col-12">
		     		<b-button style="margin-right:5px;" block variant="primary">Salvar</b-button>
		     		<b-button block variant="danger">Excluir</b-button>
		     	</div>
		     </div>

		 </b-container>
		
	</div>
</template>


<script>

	export default{

	}
	
</script>


<style lang="scss" scoped>
	
</style>