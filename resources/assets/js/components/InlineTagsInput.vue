<template>
  <tags-input :tags="tags" @update="(tags) => { $emit('update', tags) }">
    <div class="tags-input" slot-scope="{ tag, removeTag, inputBindings, inputEventHandlers }">
      <span class="tags-input-tag" v-for="tag in tags">
        <span>{{ tag }}</span>
        <button type="button" class="tags-input-remove" @click="removeTag(tag)">&times;</button>
      </span>

      <input class="tags-input-text" placeholder="Add tag..."
        v-on="inputEventHandlers"
        v-bind="inputBindings"
      >
    </div>
  </tags-input>
</template>

<script>
  export default {
    model: {
      prop: 'tags',
      event: 'update'
    },
    props: ['tags'],
  }
</script>
