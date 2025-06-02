<!-- Global footer component that will be added to all slides -->
<template>
  <footer
    v-if="
      $slidev.nav.currentLayout !== 'intro' &&
      $slidev.nav.currentLayout !== 'center' &&
      $slidev.nav.currentPage !== $slidev.nav.total
    "
    class="absolute bottom-0 left-0 right-0 px-4 py-2 border-t border-gray-200/10"
  >
    <div class="text-gray-400/80">
      <span class="font-medium"
        >Signal Processing Laboratory (University of São Paulo)</span
      >
      <span class="absolute right-4"
        >{{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}</span
      >
    </div>
  </footer>
</template>
