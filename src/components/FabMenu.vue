<template>
    <div class="fabMenu">
        <div class="fabMenuArea">
            <div class="menuButton">
                <input type="checkbox" name="menu" id="menu" @click="toggleVisibility">
            </div>
            <transition name="fade">
                <div class="actionButtons-bar" v-if="isVisible">
                    <ul class="action_buttons" >
                        <li v-for="action_item of action_items"
                        :key=action_item.id>
                            <i class="material-icons md-18">{{action_item.name}}</i>
                        </li>
                        
                    </ul>
                </div>
            </transition>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'FabMenu',
        data: function () {
            return {
                isVisible: true,
                action_items: [
                    {name: 'favorite'},
                    {name:'share'},
                    {name:'get_app'},
                    {name: 'chat'}
                ]
            }
        },
        methods: {
            toggleVisibility: function () {
                this.isVisible = !this.isVisible
            }
        }
    }
</script>

<style scoped>
    .fade-enter-active,
    .fade-leave-active {
        transition: opacity .65s;
    }

    .fade-enter,
    .fade-leave-active {
        opacity: 0;
    }
    .action_buttons span{

    }
    
    .material-icons {
  font-family: 'Material Icons';
  font-weight: normal;
  font-style: normal;
  font-size: 32px;  /* Preferred icon size */
  display: inline-block;
  color:#111;
  line-height: 1;
  text-transform: none;
  letter-spacing: normal;
  word-wrap: normal;
  white-space: nowrap;
  direction: ltr;

  /* Support for all WebKit browsers. */
  -webkit-font-smoothing: antialiased;
  /* Support for Safari and Chrome. */
  text-rendering: optimizeLegibility;

  /* Support for Firefox. */
  -moz-osx-font-smoothing: grayscale;

  /* Support for IE. */
  font-feature-settings: 'liga';
}
</style>