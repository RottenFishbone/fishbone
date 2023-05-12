<script lang="ts">
  let classExtra = '';
  export {classExtra as class}

  const classInherent = '';
  const classCombined = `${classInherent} ${classExtra}`;
</script>

<ul class={classCombined} >
  <slot />
</ul>
