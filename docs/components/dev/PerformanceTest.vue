<template>
<!-- @search-change="changeScroll" -->
  <treeselect
    :options="zzjgOptions"
    :multiple="true"
    :appendToBody="true"
    class="search-input search-input-tree"
    placeholder="请选择"
    valueFormat="object"
    noResultsText="无数据"
    noOptionsText="无数据"
    noChildrenText="无数据"
    :limit="4"
    :limitText="(count) => `${count} 个已选项已折叠`"
    clearable
    :disableFuzzyMatching="true"
    :preferredExactMatch="false"
  />
</template>

<script>
import { generateZzjg } from "../utils";

export default {
  data: () => ({
    zzjgOptions: null,
  }),
  created() {
    this.zzjgOptions = JSON.parse(JSON.stringify(generateZzjg()));
  },
}
</script>
