<script>
  export default {
    name: 'vue-treeselect--multi-value-item-custom',

    props: {
      label: {
        type: String,
        required: true,
      },
      count: {
        type: Number,
        default: 0,
      },
    },

    render() {
      const { label } = this
      const itemClass = {
        'vue-treeselect__multi-value-item': true,
        'vue-treeselect__multi-value-item-disabled': true,
      }

      return (
        <div class="vue-treeselect__multi-value-item-container">
          <div class={itemClass}>
            <span class="vue-treeselect__multi-value-label">{ label }</span>
          </div>
        </div>
      )
    },
  }
</script>
