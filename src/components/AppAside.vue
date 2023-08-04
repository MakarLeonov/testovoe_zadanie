<template>
    <aside>
        <div class="categories-filters">
            <div class="title">
                <p>Название категории</p>
                <p>3</p>
            </div>
            <div class="item" v-for="item in 3" :key="index">
                <p>Название категории</p>
                <p>3</p>
            </div>
        </div>
        <div class="slider-filters">
            <asideTitle>Цена</asideTitle>
            <div>
                <div class="input">
                    <p>от</p>
                    <input type="number" value="5500">
                </div>
                <div></div>
                <div class="input">
                    <p>до</p>
                    <input type="number" value="5500">
                </div>
            </div>
        </div>
        <div class="brand-filters">
            <div class="head">
                <asideTitle>Бренд</asideTitle>
                <div @click="cleanFilters">Очистить</div>
            </div>
            <div class="input">
                <div class="search-icon">
                    <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" viewBox="0 0 16 16" fill="none">
                        <g opacity="0.3">
                            <path fill-rule="evenodd" clip-rule="evenodd" d="M7.33333 2.75C4.80203 2.75 2.75 4.80203 2.75 7.33333C2.75 9.86464 4.80203 11.9167 7.33333 11.9167C9.86464 11.9167 11.9167 9.86464 11.9167 7.33333C11.9167 4.80203 9.86464 2.75 7.33333 2.75ZM1.25 7.33333C1.25 3.9736 3.9736 1.25 7.33333 1.25C10.6931 1.25 13.4167 3.9736 13.4167 7.33333C13.4167 10.6931 10.6931 13.4167 7.33333 13.4167C3.9736 13.4167 1.25 10.6931 1.25 7.33333Z" fill="#333333"/>
                            <path fill-rule="evenodd" clip-rule="evenodd" d="M10.5698 10.5696C10.8627 10.2768 11.3375 10.2768 11.6304 10.5696L14.5304 13.4696C14.8233 13.7625 14.8233 14.2374 14.5304 14.5303C14.2375 14.8232 13.7627 14.8232 13.4698 14.5303L10.5698 11.6303C10.2769 11.3374 10.2769 10.8625 10.5698 10.5696Z" fill="#333333"/>
                        </g>
                    </svg>
                </div>
                <input type="text" placeholder="Поиск" v-model="brandSearch">
                <Transition>
                    <div class="clean-the-search" v-show="brandSearch" @click="brandSearch = ''">
                        <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
                            <g opacity="0.3">
                                <path fill-rule="evenodd" clip-rule="evenodd" d="M18.3334 10C18.3334 14.6024 14.6025 18.3333 10.0001 18.3333C5.39771 18.3333 1.66675 14.6024 1.66675 10C1.66675 5.39764 5.39771 1.66668 10.0001 1.66668C14.6025 1.66668 18.3334 5.39764 18.3334 10ZM13.0893 8.08927C13.4148 7.76383 13.4148 7.23619 13.0893 6.91076C12.7639 6.58532 12.2363 6.58532 11.9108 6.91076L10.0001 8.8215L8.08934 6.91076C7.7639 6.58532 7.23626 6.58532 6.91083 6.91076C6.58539 7.23619 6.58539 7.76383 6.91083 8.08927L8.82157 10L6.91083 11.9108C6.58539 12.2362 6.58539 12.7638 6.91083 13.0893C7.23626 13.4147 7.7639 13.4147 8.08934 13.0893L10.0001 11.1785L11.9108 13.0893C12.2363 13.4147 12.7639 13.4147 13.0893 13.0893C13.4148 12.7638 13.4148 12.2362 13.0893 11.9108L11.1786 10L13.0893 8.08927Z" fill="#333333"/>
                            </g>
                        </svg>
                    </div>
                </Transition>
            </div>
            <div class="brand-list">

                <div class="item" v-for="filter in brandListFilters" :key="filter.id">
                    <div class="atribut">
                        <checkbox :isDisabled="filter.isDisabled" @changeDisable="changeBrandDisable(filter.id - 1)"/>   
                        <p>Атрибут {{ filter.id }}</p>
                    </div>
                    <p>3</p>
                </div>
                
            </div>
        </div>
        <div class="size-filters">
            <asideTitle>Размер</asideTitle>
            <div class="brand-list">

                <div class="item" v-for="filter in sizeListFilters" :key="filter.id">
                    <div class="atribut">
                        <checkbox :isDisabled="filter.isDisabled" @changeDisable="changeSizedDisable(filter.id - 1)"/>   
                        <p>Атрибут {{ filter.id }}</p>
                    </div>
                    <p>3</p>
                </div>

            </div>
        </div>
    </aside>
</template>
<script>
import asideTitle from '@/components/UI/asideTitle.vue'
import checkbox from '@/components/UI/checkbox.vue'
export default {
    components: {
        asideTitle, checkbox,
    },

    data() {
        return {
            brandSearch: '',
            brandListFilters: [
                {id: 1, isDisabled: true},
                {id: 2, isDisabled: false},
                {id: 3, isDisabled: false},
                {id: 4, isDisabled: false},
                {id: 5, isDisabled: false},
                {id: 6, isDisabled: true},
                {id: 7, isDisabled: false},
                {id: 8, isDisabled: false},
                {id: 9, isDisabled: false},
            ],
            sizeListFilters: [
                {id: 1, isDisabled: false},
                {id: 2, isDisabled: false},
                {id: 3, isDisabled: false},
                {id: 4, isDisabled: false},
                {id: 5, isDisabled: false},
                {id: 6, isDisabled: false},
            ],
        }
    },

    methods: {
        cleanFilters() {
            this.brandSearch = ''
            this.brandListFilters.forEach(el => el.isDisabled = false)
            this.sizeListFilters.forEach(el => el.isDisabled = false)
        },

        changeBrandDisable(id) {
            this.brandListFilters[id].isDisabled = !this.brandListFilters[id].isDisabled
        },

        changeSizedDisable(id) {
            this.sizeListFilters[id].isDisabled = !this.sizeListFilters[id].isDisabled
        },
    },
}
</script>
<style lang="scss" scoped>

aside {
    display: flex;
    width: 280px;
    flex-direction: column;
    align-items: flex-start;
    gap: 28px;
    font-family: PT Sans;
    // background-color: antiquewhite;

    .categories-filters {
        width: 100%;
        display: flex;
        flex-direction: column;
        font-size: 14px;
        line-height: 16px;

        div {
            display: flex;
            height: 30px;
            padding: 0px 16px 0px 8px;
            justify-content: space-between;
            align-items: center;
            align-self: stretch;
            border-radius: 5px;
        }

        .item {
            padding: 0px 16px 0px 32px;
            cursor: pointer;
            transition: all .2s ease-out;

            &:hover {
                background: var(--font-background-hover, #E2EFFF);
                transition: all .2s ease-in;
            }
        }
    }
    
    .slider-filters {
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 16px;

        div {
            display: flex;
            align-items: center;
            gap: 16px;

            div {
                width: 10px;
                height: 1px;
                background: #D5D5D5;
            }

            .input {
                position: relative;
                width: 119px;
                height: 36px;

                input {
                    display: flex;
                    padding: 10px 8px 10px 26px;
                    flex: 1 0 0;
                    border-radius: 4px;
                    border: 1px solid var(--tech-borderand-others, #D5D5D5);
                    background: var(--tech-white, #FFF);
                    width: 100%;
                    z-index: 1;

                    color: var(--font-primary, #333);
                    font-size: 14px;
                    font-weight: 400;
                    line-height: 16px;
                }
                
                p {
                    position: absolute;
                    top: 11px;
                    left: 8px;
                    z-index: 2;
                    font-size: 12px;
                    font-weight: 400;
                    line-height: 14px;
                    color: #AAA;
                }
            }
        }
    }

    .brand-filters, .size-filters {
        width: 100%;
        display: flex;
        flex-direction: column;
        gap: 16px;

        -webkit-touch-callout: none; 
        -webkit-user-select: none; 
        -khtml-user-select: none; 
        -moz-user-select: none;
        -ms-user-select: none; 
        user-select: none;

        .head {
            width: 100%;
            display: flex;
            justify-content: space-between;
            align-items: center;

            div {
                color: var(--font-secondary, #AAA);
                font-size: 12px;
                line-height: 12px;
                text-decoration-line: underline;
                cursor: pointer;
            }
        }

        .input {
            position: relative;
            width: 100%;

            input {
                width: -webkit-fill-available;
                padding: 10px 36px;
                align-items: flex-start;
                gap: 8px;
                align-self: stretch;
                border-radius: 4px;
                border: 1px solid var(--tech-borderand-others, #D5D5D5);
                background: var(--tech-white, #FFF);
                outline: none;
                transition: all .2s ease-out;

                ::-webkit-input-placeholder {color:#AAAAAA;}
                ::-moz-placeholder          {color:#AAAAAA;}
                :-moz-placeholder           {color:#AAAAAA;}
                :-ms-input-placeholder      {color:#AAAAAA;}
            }

            .clean-the-search {
                position: absolute;
                z-index: 3;
                top: 10px;
                right: 12px;
                cursor: pointer;
            }

            .search-icon {
                position: absolute;
                top: 10px;
                left: 12px;
            }
        }

        .brand-list {
            height: 182px;
            overflow-y: scroll;
            display: flex;
            padding: 2px 0 2px;
            flex-direction: column;
            gap: 12px;

            &::-webkit-scrollbar {
                width: 3px;
                height: 121px;
            }

            &::-webkit-scrollbar-thumb {
                background-color: #CBCBCB;
                border-radius: 10px;
            }

            .item {
                height: 20px;
                padding-right: 16px;
                display: flex;
                justify-content: space-between;
                align-items: center;
                
                
                .atribut {
                    display: flex;
                    gap: 12px;
                    align-items: center;
                    color: #333333;
                    font-family: PT Sans;
                    font-size: 14px;
                    font-style: normal;
                    font-weight: 400;
                    line-height: 16px; 

                    .checkmark {
                        display: block;
                        width: 20px;
                        height: 20px;
                        border: 1px solid var(--tech-borderand-others, #D5D5D5);        display: flex;
                        justify-content: center;
                        align-items: center;
                        border-radius: 3px;

                        transition: all .1s ease-in-out;
                        cursor: pointer;
                    }
                }
            }
        }
    }
}

.v-enter-active,
.v-leave-active {
  transition: opacity 0.2s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}
    
</style>