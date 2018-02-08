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
      <inline-tags-input v-model="tags"></inline-tags-input>
    </div>
    <div class="mb-8">
      <label class="form-label">Tags</label>

      <tags-input v-model="tags">
        <div slot-scope="{ tag, removeTag, inputBindings, inputEventHandlers }">
          <input class="text-input mb-2" placeholder="Reviewed, packed, delivered"
            v-on="inputEventHandlers"
            v-bind="inputBindings"
          >

          <div>
            <span class="tags-input-tag inline-flex items-center bg-grey-light text-grey-darkest px-2" v-for="tag in tags">
              <span>{{ tag }}</span>
              <button type="button" class="tags-input-remove text-grey-dark" @click="removeTag(tag)">
                <svg class="fill-current h-3 w-3" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32"><path d="M18.263 16l10.07-10.07c.625-.625.625-1.636 0-2.26s-1.638-.627-2.263 0L16 13.737 5.933 3.667c-.626-.624-1.637-.624-2.262 0s-.624 1.64 0 2.264L13.74 16 3.67 26.07c-.626.625-.626 1.636 0 2.26.312.313.722.47 1.13.47s.82-.157 1.132-.47l10.07-10.068 10.068 10.07c.312.31.722.468 1.13.468s.82-.157 1.132-.47c.626-.625.626-1.636 0-2.26L18.262 16z"></path></svg>
              </button>
            </span>
          </div>
        </div>
      </tags-input>

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
