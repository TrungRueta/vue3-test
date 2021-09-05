<script setup lang="ts">
enum MyEnum {
  test = "true",
}

// this hint correct null | boolean type
let a = $ref(null as null | boolean);

// this lost null check
interface Ok {
  ok: boolean;
}
let b = $ref(null as null | Ok);

// this should be mark error by typescript. Should be b?.ok
b.ok;
</script>

<template>
  <div>
    {{ MyEnum }}
  </div>
</template>
