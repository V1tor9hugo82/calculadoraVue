<template>
  <button
    class="button"
    @click="$emit('onClick', label)"
    :class="{ double, triple, operation }"
  >
    {{ label }}
  </button>
</template>

<script>
export default {
  props: {
    label: {},
    operation: { type: Boolean },
    double: { type: Boolean },
    triple: { type: Boolean },
  },
};
</script>

<style>
:root {
  --bg-button: #fffdd6;
  --border-button: solid 1px #6c6c6c;
}

.button {
  font-size: 1.4em;
  background-color: var(--bg-button);
  border: none;
  border-right: var(--border-button);
  border-bottom: var(--border-button);
  outline: none;
}

.button:active {
  background-color: #ccc;
}

.button.double {
  grid-column: span 2;
}

.button.triple {
  grid-column: span 3;
}

.button.operation {
  background-color: #36c43e;
  color: #fff;
}

.button.operation:active {
  background-color: #36c43ecc;
}
</style>