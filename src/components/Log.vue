<template>
<div>
<x-header :right-options="{showMore: false}" :left-options="{showBack: true}">登陆</x-header>
<group>
<x-input title="手机号码" mask="999 9999 9999" v-model="phone" :max="13" is-type="china-mobile"></x-input>
<x-input title="密码" mask="999 9999 9999" v-model="password" :max="13"></x-input>
</group>
<div>
<x-botton @click.native='Log'>登陆></x-botton>
</div>
</div>
</template>


<script>

import { XInput, Group, XButton, Cell, Alert } from 'vux'

export default {
  components: {
    XInput,
    XButton,
    Group,
    Cell,
    Alert
  },
  methods: {
    Log () {
      if (this.password === '123456') {
          this, $router.push({path:'/'})
        }else{
            AlertModule.show({
                title:'登陆失败',
                content:'密码错误'
            })
        }
    }
},
data () {
    return {
    phone: '',
    password: ''
   }
}
}
</script>