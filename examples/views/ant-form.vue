<template>
  <div>
    <InputDemo></InputDemo>

    <a-form :form="form" :label-col="{ span: 5 }" :wrapper-col="{ span: 12 }">
      <a-form-item>
        <a-input v-decorator="['field1', { initialValue: 'abc' }]"></a-input>
      </a-form-item>
    </a-form>
  </div>
</template>
<script>
import InputDemo from './input-demo';
export default {
  components: { InputDemo },
  data() {
    return {
      form: this.$form.createForm(this),
    };
  },
};
</script>
