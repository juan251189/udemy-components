<template>
  <div>
<div>
  <slot name="title"></slot>
  <div>
    <slot name="content"></slot>
  </div>
</div>

  </div>
</template>

<script>
export default{

}
</script>

<style scoped>


div{
  border:1px solid grey;
  box-shadow: 1px 1px 2px black
}
h1{
  color: #a83010;
}
p{
  font-style: italic;
  color:#8c9399;
}
</style>
