<template>
  <section>
    <base-card>
      <template v-slot:header>
        <h3>{{ fullName }}</h3>
        <base-badge :type="role" :caption="role.toUpperCase()"></base-badge>
      </template>
      <template v-slot:default>
        <p>{{ infoText }}</p>
      </template>
    </base-card>
  </section>
</template>

<script>
import BaseBadge from "./BaseBadge";
import BaseCard from "./BaseCard";
export default {
  props: ["fullName", "infoText", "role"],
  components: { BaseBadge, BaseCard },
};
</script>
