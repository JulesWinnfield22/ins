<script setup lang="ts">
import Button from "./Button.vue";
import Form from "./new_form_builder/Form.vue";
import Input from "./new_form_elements/Input.vue";
import Textarea from "./new_form_elements/Textarea.vue";

const props = defineProps({
  pending: {
    type: Boolean,
    default: false,
  },
  onSubmit: {
    type: Function,
    required: true,
  },
});

function submitForm({ values }: { values: any }) {
  props.onSubmit && props.onSubmit(values);
}
</script>

<template>
  <Form
    v-slot="{ submit }"
    id="contact"
    class="grid grid-cols-2 gap-5 bg-accent rounded-xl p-6"
  >
    <Input
      name="firstName"
      :attributes="{
        placeholder: 'First Name',
      }"
      validation="required"
    />
    <Input
      name="lastName"
      :attributes="{
        placeholder: 'Last Name',
      }"
      validation="required"
    />
    <div class="col-span-2">
      <Input
        name="email"
        :attributes="{
          placeholder: 'Email',
        }"
        validation="required|email"
      />
    </div>
    <div class="col-span-2">
      <Input
        name="phone"
        :attributes="{
          placeholder: 'Phone Number',
        }"
        validation="required|phone"
      />
    </div>
    <div class="col-span-2">
      <Textarea
        name="message"
        :attributes="{
          placeholder: 'Your Message',
        }"
        validation="required|phone"
      />
    </div>
    <Button
      @click.prevent="submit(submitForm)"
      class="col-span-2"
      type="primary"
    >
      Send Message
    </Button>
  </Form>
</template>
