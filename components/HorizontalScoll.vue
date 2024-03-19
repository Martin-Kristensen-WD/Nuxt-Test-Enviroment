<template>
  <main ref="scrollContainer" class="overflow-x-hidden flex">
    <section class="min-w-[50vw] min-h-[90vh] grid text-center items-center text-4xl">
      <h1>Beep</h1>
    </section>
    <section class="min-w-[50vw] min-h-[90vh] grid text-center items-center text-4xl bg-slate-500">
      <h1>Boop</h1>
    </section>
    <section class="min-w-[50vw] min-h-[90vh] grid text-center items-center text-4xl">
      <h1>Boooom</h1>
    </section>
    <section class="min-w-[50vw] min-h-[90vh] grid text-center items-center text-4xl bg-slate-500">
      <h1>The End</h1>
    </section>
  </main>
</template>

<script setup lang="ts">

const scrollContainer = ref<HTMLElement | null>(null)

function handleWheel(event: WheelEvent) {
  event.preventDefault()
  if (scrollContainer.value) {
    scrollContainer.value.scrollLeft += event.deltaY
  }
}

onMounted(() => {
  scrollContainer.value?.addEventListener("wheel", handleWheel);
})

</script>
