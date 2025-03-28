<script setup lang="ts">
import Button from './Button.vue';
import Form from './new_form_builder/Form.vue';
import Input from './new_form_elements/Input.vue';
import Textarea from './new_form_elements/Textarea.vue';

</script>

<template>
	<Form id="contact" class="grid grid-cols-2 gap-5 backdrop-blur-md bg-light-gray rounded-xl p-6" >
		<Input
			name="firstName"
			:attributes="{
				placeholder: 'First Name'
			}"
			validation="required"
		/>
		<Input
			name="lastName"
			:attributes="{
				placeholder: 'First Name'
			}"
			validation="required"
		/>
		<div class="col-span-2" >
			<Input
				name="email"
				:attributes="{
					placeholder: 'Email'
				}"
				validation="required|email"
			/>
		</div>
		<div class="col-span-2" >
			<Input
				name="phone"
				:attributes="{
					placeholder: 'Phone Number'
				}"
				validation="required|phone"
			/>
		</div>
		<div class="col-span-2" >
			<Textarea
				name="message"
				:attributes="{
					placeholder: 'Your Message'
				}"
				validation="required|phone"
			/>
		</div>
		<Button class="col-span-2" type="primary" >
			Send Message
		</Button>
	</Form>
</template>