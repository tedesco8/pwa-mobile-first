<template>
  <div>
    {{ $colorMode.preference }}
    <IconDark
      v-if="$colorMode.preference != 'dark'"
      @click="changeTheme('dark')"
    />
    <IconLight v-else @click="changeTheme('light')" />
  </div>
</template>

<script>
export default {
  name: 'ColorSwitch',
  components: {
    IconDark: () => import('@/assets/icons/dark.svg?inline'),
    IconLight: () => import('@/assets/icons/light.svg?inline'),
  },
  methods: {
    changeTheme(theme) {
      this.$colorMode.preference = theme
    },
  },
}
</script>
