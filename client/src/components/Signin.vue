<template>
<div class="container mt-5">
	<div class="row justify-content-center">
		<div class="col-md-6">
			<form v-on:submit.prevent="signin">
				<div class="form-group">
					<label for="exampleInputEmail1">Email address</label>
					<input type="email" v-model="email" class="form-control" id="exampleInputEmail1" name="email" aria-describedby="emailHelp">
					
				</div>
				<div class="form-group">
					<label for="exampleInputPassword1">Password</label>
					<input type="password" v-model="password" class="form-control" id="exampleInputPassword1" name="password">
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
	const url = 'http://localhost:4000/api/auth/';
	export default{
		data() {
			return {
				email: '',
				password: ''
			}
		},

		methods: {
			signin() {
				axios.post(url, {
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