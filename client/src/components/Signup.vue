<template>
<div class="container mt-5">
	<div class="row justify-content-center">
		<div class="col-md-6">
			<form v-on:submit.prevent="signup">
				<div class="form-group">
					<label for="exampleInputEmail1">First Name</label>
					<input type="text" v-model="first_name" name="first_name" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
					
				</div>
				<div class="form-group">
					<label for="exampleInputEmail1">Last Name</label>
					<input type="text" v-model="last_name" name="last_name" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
					
				</div>
				<div class="form-group">
					<label for="exampleInputEmail1">Email</label>
					<input type="email" v-model="email" name="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp">
					
				</div>
				<div class="form-group">
					<label for="exampleInputPassword1">Password</label>
					<input type="password" v-model="password" class="form-control" id="exampleInputPassword1">
				</div>
				<div class="form-group">
					<label for="exampleInputPassword1">Confirm Password</label>
					<input type="password" class="form-control" id="exampleInputPassword1">
				</div>
				
				<button type="submit" class="btn btn-primary">Submit</button>
			</form>
		</div>
	</div>
</div>
</template>
<script>
	import axios from 'axios'
	import router from '../router'
	const url = 'http://localhost:4000/api/users/';
	export default{
		data() {
			return {
				first_name: '',
				last_name: '',
				email: '',
				password: ''
			}
		},

		methods: {
			signup() {
				axios.post(url, {
					first_name: this.first_name,
					last_name: this.last_name,
					email: this.email,
					password: this.password
				}).then(res => {
					router.push({ name: 'dashboard'})
				}).catch(err => {
					console.log(err);
				})
				
			}
		}
	}
</script>