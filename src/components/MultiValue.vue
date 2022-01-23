<script>
  // import MultiValueItem from './MultiValueItem'
  import MultiValueItemCustom from './MultiValueItemCustom'
  import Input from './Input'
  import Placeholder from './Placeholder'

  export default {
    name: 'vue-treeselect--multi-value',
    inject: [ 'instance' ],

    methods: {
      renderMultiValueItems() {
        const { instance } = this

        const selectedRegions = instance.internalValue.filter(n => n.split('-')[0] === '1').slice(0, instance.limit)
        // const selectedRegionsCount = selectedRegions.length

        // if (selectedRegionsCount === 1) {
        //   return this.renderRegion(selectedRegions[0])
        // } else if (selectedRegionsCount > 1) {
        //   return instance.internalValue
        //     .filter(n => n.split('-')[0] === '1')
        //     .slice(0, instance.limit)
        //     .map(instance.getNode)
        //     .map(node => (
        //       <MultiValueItem key={`multi-value-item-${node.id}`} node={node} />
        //     ))
        // }

        return selectedRegions
          .map(this.renderRegion)
      },

      renderRegion(regionId) {
        const { instance } = this
        const region = instance.getNode(regionId)
        const regionCitiesCount = region.count.ALL_CHILDREN

        const selectedRegionCities = instance.internalValue
          .filter(n => n.split('-').length === 3)
          .filter(n => {
            // console.log({
            //   i: n.split('-')[1],
            //   r: region,
            // })
            return n.split('-')[1] === `${region.raw.id}`
          })
        const selectedRegionCitiesCount = selectedRegionCities.length

        let label = region.label + ' (' + selectedRegionCitiesCount + ')'

        if (selectedRegionCitiesCount === 1) {
          label = region.label + '/' + instance.getNode(selectedRegionCities[0]).label
        } else if (selectedRegionCitiesCount === regionCitiesCount) {
          label = region.label
        }

        return (
          <MultiValueItemCustom key={`multi-value-item-${regionId}`} label={ label } />
        )
      },

      renderExceedLimitTip() {
        const { instance } = this
        const count = instance.internalValue.filter(n => n.split('-')[0] === '1').length - instance.limit

        if (count <= 0) return null

        return (
          <div class="vue-treeselect__limit-tip vue-treeselect-helper-zoom-effect-off" key="exceed-limit-tip">
            <span class="vue-treeselect__limit-tip-text">...</span>
          </div>
        )
      },
    },

    render() {
      const { renderValueContainer } = this.$parent
      const transitionGroupProps = {
        props: {
          tag: 'div',
          name: 'vue-treeselect__multi-value-item--transition',
          appear: true,
        },
      }

      return renderValueContainer(
        <transition-group class="vue-treeselect__multi-value" {...transitionGroupProps}>
          {this.renderMultiValueItems()}
          {this.renderExceedLimitTip()}
          <Placeholder key="placeholder" />
          <Input ref="input" key="input" />
        </transition-group>,
      )
    },
  }
</script>
