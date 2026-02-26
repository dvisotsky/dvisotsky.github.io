<script setup lang="ts">
import { computed, onBeforeUnmount, onMounted, ref } from "vue";

type NavLink = {
  href: string;
  label: string;
};

const props = withDefaults(
  defineProps<{
    currentPath: string;
    links?: NavLink[];
  }>(),
  {
    links: () => [
      { href: "/", label: "Home" },
      { href: "/blog", label: "Blog" },
      { href: "/about", label: "About" },
    ],
  },
);

const isOpen = ref(false);
const navRoot = ref<HTMLElement | null>(null);

const normalizedPath = computed(() => {
  if (!props.currentPath) return "/";
  return props.currentPath.endsWith("/") && props.currentPath !== "/"
    ? props.currentPath.slice(0, -1)
    : props.currentPath;
});

const isActive = (href: string) => {
  const pathname = normalizedPath.value;
  const subpath = pathname.match(/[^/]+/g);
  return href === pathname || href === "/" + (subpath?.[0] || "");
};

const closeMenu = () => {
  isOpen.value = false;
};

const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};

const handleOutsidePointer = (event: PointerEvent) => {
  if (!isOpen.value || !navRoot.value) return;
  const target = event.target;
  if (target instanceof Node && !navRoot.value.contains(target)) {
    isOpen.value = false;
  }
};

onMounted(() => {
  document.addEventListener("pointerdown", handleOutsidePointer);
});

onBeforeUnmount(() => {
  document.removeEventListener("pointerdown", handleOutsidePointer);
});
</script>

<template>
  <div ref="navRoot" class="responsive-nav">
    <button
      class="menu-toggle"
      type="button"
      :aria-expanded="isOpen"
      aria-controls="site-mobile-menu"
      aria-label="Toggle navigation menu"
      @click="toggleMenu"
    >
      <svg
        class="menu-icon"
        viewBox="0 0 24 24"
        aria-hidden="true"
        focusable="false"
      >
        <path fill="currentColor" d="M3 18v-2h18v2zm0-5v-2h18v2zm0-5V6h18v2z" />
      </svg>
    </button>

    <div id="site-mobile-menu" class="internal-links" :class="{ open: isOpen }">
        <a
        v-for="link in links"
        :key="link.href"
        :href="link.href"
        :class="{ active: isActive(link.href) }"
        @click="closeMenu"
      >
        {{ link.label }}
      </a>
    </div>
</div>
</template>

<style scoped>
.responsive-nav {
  position: relative;
  display: flex;
  align-items: center;
}

.internal-links {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

a {
  display: inline-block;
  padding-right: 0.2em;
  color: var(--fg);
  border-bottom: 1px solid transparent;
  text-decoration: none;
  transition: 0.2s;
}

a:hover {
  border-bottom-color: var(--accent);
}

a.active {
  text-decoration: none;
  border-bottom-color: var(--accent);
}

.menu-toggle {
  display: none;
  background: transparent;
  border: 1px solid rgb(var(--gray));
  color: var(--fg);
  border-radius: 4px;
  padding: 0.35em 0.55em;
  cursor: pointer;
  line-height: 1;

  transition: 0.2s;
}

.menu-toggle:hover {
  border-color: var(--accent);
  color: var(--accent);
}

.menu-icon {
  width: 1rem;
  height: 1rem;
  display: block;
  color: currentColor;
}

@media (max-width: 720px) {
  .menu-toggle {
    display: inline-flex;
    align-items: center;
  }

  .internal-links {
    position: absolute;
    top: calc(100% + 0.5rem);
    right: -8px;
    flex-direction: column;
    align-items: flex-start;
    gap: 0.45rem;
    min-width: 9rem;
    padding: 0.6rem 0.75rem;
    background: var(--bg);
    border: 1px solid rgb(var(--gray));
    border-radius: 4px;
    z-index: 20;

    opacity: 0;
    transition: 0.2s;
    pointer-events: none;
  }

  .internal-links.open {
    pointer-events: auto;
    display: flex;
    top: calc(100% + 0.5rem);
    right: 0;
    opacity: 1;
  }

  a {
    padding-right: 0;
  }
}
</style>
