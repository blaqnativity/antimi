<script setup lang="ts">
const items = [
  [
    {
      label: "blaqnativity@gmail.com",
      slot: "account",
      disabled: true,
    },
  ],
  [
    {
      label: "Edit Profile",
      icon: "i-heroicons-user",
      to: "/dashboard/profile",
    },
    {
      label: "Sign-out",
      icon: "i-heroicons-arrow-arrow-left-on-rectangle",
      // onClick: "/dashboard/profile",
    },
  ],
];
</script>

<template>
  <UDropdown
    :items="items"
    :ui="{ item: { disabled: 'cursor-text select-text' } }"
    :popper="{ placement: 'bottom-start' }"
  >
    <UAvatar src="https://avatars.githubusercontent.com/u/739984?v=4" />

    <template #account="{ item }">
      <div class="text-left">
        <p>Signed in as</p>
        <p class="truncate font-medium text-gray-900 dark:text-white">
          {{ item.label }}
        </p>
      </div>
    </template>

    <template #item="{ item }">
      <span class="truncate">{{ item.label }}</span>

      <UIcon
        :name="item.icon"
        class="flex-shrink-0 h-4 w-4 text-gray-400 dark:text-gray-500 ms-auto"
      />
    </template>
  </UDropdown>
</template>
