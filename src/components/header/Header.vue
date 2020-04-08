<template>
    <div class="container">
        <div>
            <h1>
                <span style="color: #45BF55">L</span>itter
                <span style="color: #45BF55">D</span>etection
            </h1>
        </div>
        <div class="headerBar">
            <div style="flex: 6" class="headerSearchItemContainer" >
                <div class="headerSearchItem">
                    <a-icon type="search" class="icons" />
                    <input style="border: none; font-size: 17px" size="30" placeholder="Location">
                </div>
            </div>
            <div class="divider"></div>
            <div style="flex: 2" class="headerBarItems">
                <a-icon type="sort-descending" class="icons"/>
                <span style="color: #A1A9B7; font-weight: bold">
                <a-select defaultValue="This year" style="width: 120px" @change="handleChange">
                    <a-select-option value="This year">This year</a-select-option>
                    <a-select-option value="Last year">Last year</a-select-option>
                </a-select>
                </span>
            </div>
            <div class="divider"></div>
            <div style="flex: 2" class="headerBarItems">
                <button style="display: flex; flex-direction: row; border: none; cursor: pointer">
                    <a-icon type="export" class="icons" />
                    <span style="color: #A1A9B7; font-weight: bold">
                    Export
                </span>
                </button>

            </div>
        </div>
    </div>
</template>

<script>
    import 'ant-design-vue/lib/select/style/css';
    export default {
        name: "Header",
        methods: {
            handleChange(value) {
                console.log(`selected ${value}`);
            },
        },
    }
</script>

<style scoped>
    .container {
        height: 100px;
        background-color: transparent;
        display: flex;
        flex-direction: row;
        align-items: center;
        margin-right: 2%;
        margin-left: 2%;
    }
    .headerBar {
        background-color: white;
        display: flex;
        flex-direction: row;
        width: 100%;
        align-items: center;
        height: 60px;
        border-radius: 10px;
        padding-left: 10px;
        box-shadow: 6px 5px 10px grey;
    }

    .divider {
        width: 1px;
        background-color: #DEE4EF;
        height: 100%
    }
    .headerBarItems {
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .headerSearchItemContainer {
        display: flex;
        align-items: center;
    }

    .headerSearchItem {
        display: flex;
        flex-direction: row;
        border-bottom: 1px solid #D9D7D7;
        padding-bottom: 5px
    }

    .icons {
        display: flex;
        align-items: center;
        margin-right: 5px;
        color: #45BF55;
        font-size: 22px;
    }
</style>