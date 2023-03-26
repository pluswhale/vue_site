<template>
    <button style="width: {{ props.width }};" class={setClassName} >
       {{ this.name }}
    </button>
</template>

<script>
    export default {
    name: 'Button',
    data: {
            
    },
    methods: {
        setClassName() {
            switch (props.variant) {
                case 'standard':
                    return 'standard_btn';
                case 'non-bg':
                    return 'non_bg_btn'
                default:
                    return 'standard'
            }
        }
    },
    props: {
        variant: {
            type: String,
            require: true
        },
        name: {
            type: String,
            require: true
        },
    }
    }
</script>

<style lang="scss" scoped>

.standard {
    border-radius: 44px;
    background-color: #f42f54;
    color: white;
    border: none;
    min-width: 120px;
    font-size: 13px;
    padding: 12px 30px;
    line-height: 25px;
    text-transform: uppercase;
    text-align: center;
    cursor: pointer;
    white-space: nowrap;
    display: inline-flex;
    align-items: center;
    justify-content: center;
}

.non_bg_btn {
    border-radius: 44px;
    background-color: transparent;
    color: white;
    border: 2px solid #f42f54;
    min-width: 120px;
    font-size: 13px;
    padding: 12px 30px;
    line-height: 25px;
    text-transform: uppercase;
    text-align: center;
    cursor: pointer;
    white-space: nowrap;
    display: inline-flex;
    align-items: center;
    justify-content: center;
}

</style>