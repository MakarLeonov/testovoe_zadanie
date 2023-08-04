<template>
    <header>
        <div class="logotip-section">
            <div class="logo">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
                    <path d="M5 21C4.45 21 3.979 20.8043 3.587 20.413C3.19567 20.021 3 19.55 3 19V5C3 4.45 3.19567 3.979 3.587 3.587C3.979 3.19567 4.45 3 5 3H19C19.55 3 20.021 3.19567 20.413 3.587C20.8043 3.979 21 4.45 21 5V19C21 19.55 20.8043 20.021 20.413 20.413C20.021 20.8043 19.55 21 19 21H5ZM6 17H18L14.25 12L11.25 16L9 13L6 17Z" fill="#73AFF4"/>
                </svg>
                <p>Логотип</p>
            </div>
            <button>
                Каталог
            </button>
        </div>
        <div class="search-section">
            <input type="text" class="search" placeholder="Поиск по 100 000 товаров " v-model="searchBar">
            <div class="search-img">
                <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none">
                    <path d="M15.5 14H14.71L14.43 13.73C15.41 12.59 16 11.11 16 9.5C16 5.91 13.09 3 9.5 3C5.91 3 3 5.91 3 9.5C3 13.09 5.91 16 9.5 16C11.11 16 12.59 15.41 13.73 14.43L14 14.71V15.5L19 20.49L20.49 19L15.5 14ZM9.5 14C7.01 14 5 11.99 5 9.5C5 7.01 7.01 5 9.5 5C11.99 5 14 7.01 14 9.5C14 11.99 11.99 14 9.5 14Z" fill="#5A5A5A"/>
                </svg>
            </div>
            <Transition>
                <div class="clean-the-search" v-show="searchBar" @click="searchBar = ''">
                    <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
                        <g opacity="0.3">
                            <path fill-rule="evenodd" clip-rule="evenodd" d="M18.3334 10C18.3334 14.6024 14.6025 18.3333 10.0001 18.3333C5.39771 18.3333 1.66675 14.6024 1.66675 10C1.66675 5.39764 5.39771 1.66668 10.0001 1.66668C14.6025 1.66668 18.3334 5.39764 18.3334 10ZM13.0893 8.08927C13.4148 7.76383 13.4148 7.23619 13.0893 6.91076C12.7639 6.58532 12.2363 6.58532 11.9108 6.91076L10.0001 8.8215L8.08934 6.91076C7.7639 6.58532 7.23626 6.58532 6.91083 6.91076C6.58539 7.23619 6.58539 7.76383 6.91083 8.08927L8.82157 10L6.91083 11.9108C6.58539 12.2362 6.58539 12.7638 6.91083 13.0893C7.23626 13.4147 7.7639 13.4147 8.08934 13.0893L10.0001 11.1785L11.9108 13.0893C12.2363 13.4147 12.7639 13.4147 13.0893 13.0893C13.4148 12.7638 13.4148 12.2362 13.0893 11.9108L11.1786 10L13.0893 8.08927Z" fill="#333333"/>
                        </g>
                    </svg>
                </div>
            </Transition>
            
        </div>
        <nav>
            <a href="#">Информация о компании</a>
            <a href="#">Контакты</a>
            <a href="#">Полезные ссылки</a>
        </nav>
    </header>
</template>
<script>
export default {
    data() {
        return {
            searchBar: ''
        }
    },
}
</script>
<style lang="scss" scoped>

header {
    display: flex;
    padding: 12px 24px;
    margin-bottom: 24px;
    align-items: center;
    align-self: stretch;
    gap: 24px;;

    color: #000;
    font-family: Inter;

    .logotip-section {
        display: flex;
        gap: 8px;

        .logo {
            display: flex;
            height: 48px;
            padding: 0px 24px;
            align-items: center;
            gap: 8px;
            font-size: 16px;
        }

        button {
            display: flex;
            height: 48px;
            padding: 8px 24px;
            align-items: center;
            gap: 10px;
            border-radius: 8px;
            border: 1px solid #73AFF4;
            background-color: #fff;
            font-family: Inter;
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
            transition: all .2s ease-out;

            &:hover {
                background-color: #73AFF4;
                border: 1px solid #73AFF4;
                color: #fff;
                transition: all .2s ease-in;
            }
        }
    }

    .search-section {
        position: relative;
        flex: 1 0 0;
        align-self: stretch;

        input {
            width: -webkit-fill-available;
            height: 100%;
            padding: 0 48px;
            border-radius: 10px;
            border: 1px solid #73AFF4;
            background: #FFF;
            z-index: 1;
            font-family: Inter;
            font-size: 16px;
            outline: none;
            transition: all .2s ease-out;

            ::-webkit-input-placeholder {color:#5A5A5A;}
            ::-moz-placeholder          {color:#5A5A5A;}
            :-moz-placeholder           {color:#5A5A5A;}
            :-ms-input-placeholder      {color:#5A5A5A;}

            
        }

        .search-img {
            position: absolute;
            z-index: 3;
            top: 15px;
            left: 16px;
            cursor: pointer;
        }

        .clean-the-search {
            position: absolute;
            z-index: 3;
            top: 16px;
            right: 16px;
            cursor: pointer;
        }
    }

    nav {
        display: flex;
        gap: 20px;
        justify-content: space-between;

        a {
            color: #393939;
            font-size: 14px;
            color: #393939;
            text-decoration: none;
            transition: all .2s ease-out;

            &:hover {
                color: #2c83e6;
                transition: all .2s ease-in;
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