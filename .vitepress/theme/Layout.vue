<script setup lang="ts">
import { useData } from 'vitepress'
import Home from './Home.vue'
import Article from './Article.vue'
import NotFound from './NotFound.vue'

const { page, frontmatter } = useData()
</script>

<template>
  <div class="antialiased bg-[#1a1a1a]">
    <div class="max-w-3xl mx-auto px-4 sm:px-6 xl:max-w-5xl xl:px-0">
      <nav class="flex justify-between items-center py-10 font-bold">
        <a class="text-xl" href="/" aria-label="The Vue Point">
          <img
            class="inline-block mr-2"
            style="width: 36px; height: 31px"
            alt="logo"
            src="/code_main.svg"
          />
          <span
            v-if="!frontmatter.index"
            class="hidden md:inline text-white"
            >Hello, Chan Dinh</span
          >
        </a>
        <div class="text-sm text-gray-500 text-white leading-5">
          <a
            class="hover:text-gray-200"
            href="https://github.com/dinhhoangbaochan"
            target="_blank"
            rel="noopener"
            ><span class="hidden sm:inline">My </span>Github
          </a>
        </div>
      </nav>
    </div>
    <main class="max-w-3xl mx-auto px-4 sm:px-6 xl:max-w-5xl xl:px-0">
      <Home v-if="frontmatter.index" />
      <NotFound v-else-if="page.isNotFound" />
      <Article v-else />
    </main>
  </div>
</template>