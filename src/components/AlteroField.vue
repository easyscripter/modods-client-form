<template>
  <div class="AlteroField">
    <input
      :id="fieldName"
      name="inputField"
      :placeholder="fieldPlaceholder"
      :value="value"
      @input="$emit('input', $event.target.value)"
    />
    <label :for="fieldName" :style="{ color: nameColor }">{{
      fieldName
    }}</label>
  </div>
</template>

<script>
export default {
  props: {
    value: {
      required: true,
    },
    fieldName: {
      type: String,
      required: true,
    },
    fieldPlaceholder: {
      type: String,
    },
    nameColor: {
      type: String,
    },
  },
  components: {},
  data: () => {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.AlteroField {
  width: 100%;
  position: relative;
  display: inline-block;
  margin-top: 40px;
  padding-right: 15px;
  margin-bottom: 15px;
  font-family: "Roboto", sans-serif;
  font-weight: normal;
}

label,
input {
  display: block;
}

label {
  position: absolute;
  top: 15px;
  font-size: 16px;
  font-weight: 600;
  text-align: left;
  color: rgba(0, 0, 0, 1);
  transition: top 0.4s ease-in-out;
  pointer-events: none;
}

input {
  position: relative;
  width: 100%;
  margin-top: 9px;
  padding-top: 10px;
  padding-bottom: 10px;
  font-family: "Roboto", sans-serif;
  font-weight: bold;
  color: #000000;
  border: none;
  border-bottom: 2px solid #8f9399;
  background: transparent;
  transition: border-bottom-color 0.4s ease-in-out;
  &:focus {
    outline: none;
    border-bottom-color: #39078d;
  }
  &:focus ~ label,
  &:valid ~ label {
    top: -10px;
  }
}

.icon {
  position: absolute;
  top: 34px;
  right: 10px;

  img {
    max-width: 23px;
    max-height: 23px;
  }
}
</style>
