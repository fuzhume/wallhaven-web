<template>
    <a-config-provider :locale="locale">
        <div id="app" @contextmenu.prevent>
            <router-view></router-view>
        </div>
    </a-config-provider>
</template>

<script>
import zh_CN from "ant-design-vue/es/locale/zh_CN";

export default {
    data(){
        return {
            locale: zh_CN
        }
    },
    metaInfo() {
        const {meta} = this.$route;
        const option = {
            title: process.env.VUE_APP_SYSTEM_VERSION,
            titleTemplate: `%s | ${process.env.VUE_APP_SYSTEM_NAME} v${process.env.VUE_APP_SYSTEM_VERSION}`
        }

        if (meta && meta.title) option.title = meta.title;

        return option;
    },
    name: 'App'
}
</script>

<style lang="less">
@import "assets/iconfont/iconfont.css";

.hevue-imgpreview-wrap {
    .he-img-wrap {
        background-color: rgba(0, 0, 0, 0.75) !important;
    }

    .he-control-bar {
        background-color: rgba(0, 0, 0, 1) !important;
    }
}

::-webkit-scrollbar {
    background-color: #ffffff;
    width: 6px;
    height: 6px;
}

::-webkit-scrollbar-thumb {
    background-color: #dedede;

    &:hover {
        background-color: #555555;
    }
}
</style>
