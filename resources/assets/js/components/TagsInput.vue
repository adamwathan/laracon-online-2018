<script>
  export default {
    model: {
      prop: 'tags',
      event: 'update'
    },
    props: ['tags'],
    data() {
      return {
        newTag: '',
      }
    },
    methods: {
      handleTagBackspace(e) {
        if (this.newTag.length === 0) {
          this.$emit('update', this.tags.slice(0, -1))
        }
      },
      addTag() {
        if (this.newTag.length === 0 || this.tags.includes(this.newTag)) {
          return
        }

        this.$emit('update', [...this.tags, this.newTag])
        this.newTag = ''
      },
      removeTag(tag) {
        this.$emit('update', this.tags.filter(t => t !== tag))
      },
    },
    render() {
      return this.$scopedSlots.default({
        tags: this.tags,
        removeTag: this.removeTag,
        inputBindings: { value: this.newTag },
        inputEventHandlers: {
          input: (e) => { this.newTag = e.target.value },
          keydown: (e) => {
            if (e.keyCode === 8) {
              this.handleTagBackspace()
            }
            if (e.keyCode === 13) {
              e.preventDefault()
              this.addTag()
            }
          }
        }
      })
    },
  }
</script>
