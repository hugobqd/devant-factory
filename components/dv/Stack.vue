<template>
  <component 
    data-comp="DvStack" 
    as="div" 
    class="flex gap-3" 
    :class="[`gap-${gap}`, orientation === 'horizontal' ? 'flex-row' : 'flex-col']"
  >
    <slot />
  </component>
</template>

<script lang="ts">
import { ref, computed, watch, onMounted, defineComponent } from 'vue'
// import { useAppConfig } from '#app'
import type { PropType } from 'vue'
import { defu } from 'defu'
// import { useAppConfig } from '#imports'
// const appConfig = useAppConfig()


export default defineComponent({
  name: 'DvStack',
  components: {},
  props: {
    orientation: {
      type: String as PropType<'horizontal' | 'vertical'>,
      default: 'vertical',
      validator: (value: string) => ['horizontal', 'vertical'].includes(value)
    },
    // ui: {
      // type: Object as PropType<Partial<typeof appConfig.ui.tabs>>,
      // default: () => appConfig.ui.stack
    // },
    gap: {
      type: Number as PropType<number>,
      default: 3
    }
  },
  setup(props, { emit }) {
    const appConfig = useAppConfig()
    const ui = computed<Partial<typeof appConfig.ui.stack>>(() => defu({}, props.ui, appConfig.ui.stack))

    return { ui }
  },
})
</script>
