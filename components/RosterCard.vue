<script setup>
const props = defineProps({
  student: {
    type: Object,
    default() {
      return {
        avatar: "default.svg",
        label: "Default Label",
        tagline: "Web Developer",
      };
    },
  },
});
</script>

<template>
  <figure>
    <img
      :src="'/images/roster/f23/' + student.avatar"
      :alt="student.label + ' Profile Pic'"
    />
    <figcaption>
      <aside class="badges">
        <!-- <ul>
          <Badge
            v-for="badge in student.badges"
            :key="badge.id"
            :badge="badge"
          />
        </ul> -->
      </aside>
      <header>{{ student.label }}</header>
      <p>{{ student.tagline }}</p>
      <footer class="social">
        <ul>
          <SocialLink
            v-for="link in student.links"
            :key="link.id"
            :link="link"
          />
        </ul>
      </footer>
    </figcaption>
  </figure>
</template>
