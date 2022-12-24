<template>
  <div class="container mx-auto mt-20 mb-20 lg:px-10 px-5">
    <div class="lg:flex justify-between">
      <p class="text lg:w-1/3 text-center text-base font-light mb-5 text-black">
        {{ contacts.address }}
      </p>
      <p class="text lg:w-1/3 text-center text-base font-bold mb-5 text-black">
        Phone:{{ contacts.phone1 }}
      </p>
      <p class="text lg:w-1/3 text-center text-base font-bold mb-5 text-black">
        E-mail:{{ contacts.mail1 }}
      </p>
    </div>
    <div class="form">
      <h5 class="formTitle mb-5">Write to us</h5>
      <a-form-model
        ref="ruleForm"
        :model="form"
        :label-col="labelCol"
        :wrapper-col="wrapperCol"
        :rules="rules"
      >
        <div class="w-full flex flex-col md:flex-row">
          <div class="md:w-1/2 w-full">
            <a-form-model-item prop="name" class="mb-5">
              <a-input
                class="w-full"
                v-model="form.name"
                placeholder="Fullname"
              />
            </a-form-model-item>
            <a-form-model-item prop="email" class="mb-5">
              <a-input
                class="w-full"
                v-model="form.email"
                placeholder="E-mail"
              />
            </a-form-model-item>
            <a-form-model-item prop="phone" class="mb-5">
              <a-input
                class="w-full"
                v-model="form.phone"
                placeholder="Phone"
                type="number"
                min="1"
              />
            </a-form-model-item>
          </div>
          <div class="md:w-1/2 w-full">
            <a-form-model-item prop="message" class="flex justify-end">
              <a-input
                class="w-full"
                v-model="form.message"
                type="textarea"
                placeholder="Message"
              />
            </a-form-model-item>
          </div>
        </div>

        <a-form-model-item>
          <a-button class="sendBtn" type="primary" @click="onSubmit">
            Send
          </a-button>
        </a-form-model-item>
      </a-form-model>
    </div>
  </div>
</template>
<script>
import contacts from '@/assets/json/contacts.json'
export default {
  data() {
    return {
      // isMounted: false,
      // coords: [37.903192, 58.38063],
      labelCol: { span: 4 },
      wrapperCol: { span: 22 },
      form: {
        name: '',
        email: '',
        phone: '',
        message: '',
      },
      rules: {
        name: [
          {
            required: true,
            message: 'Must be filled',
            trigger: 'blur',
          },
        ],
        email: [
          {
            required: true,
            message: 'Must be filled',
            trigger: 'blur',
          },
        ],
        phone: [
          {
            required: true,
            message: 'Must be filled',
            trigger: 'blur',
          },
        ],
        message: [
          {
            required: true,
            message: 'Must be filled',
            trigger: 'blur',
          },
        ],
      },
    }
  },
  components: {},
  computed: {
    contacts: () => contacts,
  },

  methods: {
    onSubmit() {
      this.$refs.ruleForm.validate(async (valid) => {
        if (valid) {
          const formData = {
            fullName: this.form.name,
            phone: this.form.phone,
            email: this.form.email,
            content: this.form.message,
          }
          //   const resp = await this.$axios.post("/api/send", formData);
          //   this.$message.destroy();
          console.log(formData)
          this.$message.success('Successfully ')
          this.$refs.ruleForm.resetFields()
        } else {
          this.$message.destroy()
          this.$message.error('Some error')

          return false
        }
      })
    },
  },
}
</script>
