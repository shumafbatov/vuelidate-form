<template>
  <div>

    Base input: {{ value }}
    <input type="text" :value="value" @change="onChange({ value: $event.target})" @input="onInput">

  </div>
</template>
<script lang="ts" setup>

interface Props {
  value: string
}

defineProps<Props>()
const onChange = ({ value }: { value: EventTarget | null }) => {
  if (value) {
    const target = value.value
    console.log({ value });
  }
}

const onInput = (event) => {
  console.log({ event });
}
</script>
