<template>
  <form @submit="submit" class="card">
    <h1 class="text-center mb-8">Start a New Discussion</h1>
    <div class="mb-8">
      <label>
        <span class="form-label">Thread Title</span>
        <input type="text" class="text-input" placeholder="New thread" v-model="title">
      </label>
    </div>
    <div class="mb-6">
      <textarea class="text-input" placeholder="Write your post..." rows="6" v-model="body"></textarea>
    </div>
    <div class="mb-8">
      <label class="form-label">Tags</label>
      <tags-input v-model="tags"></tags-input>
    </div>
    <div class="text-right">
      <button type="submit" class="btn btn-primary">Start Discussion</button>
    </div>
  </form>
</template>

<script>
  export default {
    data() {
      return {
        title: '',
        category: null,
        body: '',
        tags: [],
        categories: [
          'General',
          'Best Practices',
          'Eloquent',
          'Testing',
          'Design',
          'Vue',
        ],
      }
    },
    methods: {
      submit() {
        // ...
      }
    }
  }
</script>
