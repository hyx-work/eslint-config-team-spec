<template>  
  <cool-component />
  <coolComponent />
  <Cool-component />

  <UnregisteredComponent />
  <unregistered-component />

  <registered-in-kebab-case />
  <registeredInCamelCase />
</template>

<script>
export default {
  components: {
    CoolComponent,
    'registered-in-kebab-case': VueComponent1,
    'registeredInCamelCase': VueComponent2
  }
}
</script>