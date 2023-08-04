<template>
    <div class="card">
        <div class="image">
            <svg xmlns="http://www.w3.org/2000/svg" width="60" height="60" viewBox="0 0 60 60" fill="none">
                <g opacity="0.5" clip-path="url(#clip0_6034_1106)">
                    <path fill-rule="evenodd" clip-rule="evenodd" d="M58.23 11.1487C58.7521 11.3571 59.1997 11.7171 59.5152 12.1823C59.8307 12.6476 59.9996 13.1966 60 13.7587V46.2412C59.9996 46.8034 59.8307 47.3524 59.5152 47.8177C59.1997 48.2829 58.7521 48.6429 58.23 48.8512L31.0425 59.7262C30.3721 59.9944 29.6242 59.9944 28.9538 59.7262L1.76625 48.8512C1.24488 48.6423 0.79802 48.282 0.483227 47.8169C0.168434 47.3517 0.000130725 46.8029 0 46.2412L0 13.7587C0.000130725 13.1971 0.168434 12.6483 0.483227 12.1831C0.79802 11.718 1.24488 11.3577 1.76625 11.1487L27.9113 0.689995L27.9488 0.678745L28.9538 0.273745C29.6253 0.00461759 30.3747 0.00461759 31.0463 0.273745L32.055 0.678745L32.0925 0.689995L58.23 11.1487ZM39.015 7.5L15.9375 16.7287L6.9225 13.125L3.75 14.3962V15.8962L28.125 25.6462V55.3537L30 56.1037L31.875 55.3537V25.65L56.25 15.9V14.4L53.0775 13.1287L30 22.3537L20.985 18.75L44.0625 9.52125L39.015 7.5Z" fill="#A6A9C7"/>
                </g>
                <defs>
                    <clipPath id="clip0_6034_1106">
                        <rect width="60" height="60" fill="white"/>
                    </clipPath>
                </defs>
            </svg>
            <div class="bestseller-label">
                <p>Хит продаж</p>
                <svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 20 20" fill="none">
                    <path d="M3.33337 11.6667C3.33337 10.2083 3.6806 8.90972 4.37504 7.77083C5.06949 6.63194 5.83337 5.67361 6.66671 4.89583C7.50004 4.11806 8.26393 3.52417 8.95837 3.11417L10 2.5V5.25C10 5.76389 10.1737 6.17 10.5209 6.46833C10.8681 6.76667 11.257 6.91611 11.6875 6.91667C11.9237 6.91667 12.1495 6.86806 12.365 6.77083C12.5806 6.67361 12.7784 6.51389 12.9584 6.29167L13.3334 5.83333C14.3334 6.41667 15.1389 7.22555 15.75 8.26C16.3612 9.29444 16.6667 10.43 16.6667 11.6667C16.6667 12.8889 16.3681 14.0036 15.7709 15.0108C15.1737 16.0181 14.3889 16.8128 13.4167 17.395C13.6528 17.0617 13.837 16.6969 13.9692 16.3008C14.1014 15.9047 14.1673 15.485 14.1667 15.0417C14.1667 14.4861 14.0625 13.9617 13.8542 13.4683C13.6459 12.975 13.3473 12.5342 12.9584 12.1458L10 9.25L7.06254 12.1458C6.65976 12.5486 6.35421 12.9931 6.14587 13.4792C5.93754 13.9653 5.83337 14.4861 5.83337 15.0417C5.83337 15.4861 5.89949 15.9064 6.03171 16.3025C6.16393 16.6986 6.34782 17.0631 6.58337 17.3958C5.61115 16.8125 4.82643 16.0172 4.22921 15.01C3.63199 14.0028 3.33337 12.8883 3.33337 11.6667ZM10 11.5833L11.7709 13.3125C12.007 13.5486 12.1875 13.8125 12.3125 14.1042C12.4375 14.3958 12.5 14.7083 12.5 15.0417C12.5 15.7222 12.257 16.3019 11.7709 16.7808C11.2848 17.2597 10.6945 17.4994 10 17.5C9.3056 17.5 8.71532 17.2603 8.22921 16.7808C7.7431 16.3014 7.50004 15.7217 7.50004 15.0417C7.50004 14.7222 7.56254 14.4131 7.68754 14.1142C7.81254 13.8153 7.9931 13.5481 8.22921 13.3125L10 11.5833Z" fill="#FF8743"/>
                </svg>
            </div>
            <div class="discount">
                25%
            </div>
        </div>
        <p class="brand">{{ product.brand }}</p>
        <p class="name">{{ product.name }}</p>
        <div class="cost">
            <p class="current-cost" v-show="product.inStock">{{ product.currentCost }} ₽</p>
            <p class="former-cost" v-show="product.inStock">{{ product.formerCost }} ₽</p>
        </div>
        <button class="buy-button" v-if="product.inStock">Купить</button>
        <button class="message-button" v-else>Сообщить о поступлении</button>
    </div>
</template>
<script>
export default {
    props: ['product'],
}
</script>
<style lang="scss" scoped>

.card {
    box-sizing: border-box;
    flex-basis: 23.4%;
    // width: 23.5%;
    height: 356px;
    background-color: #fff;
    font-family: PT Sans;
    display: flex;
    flex-direction: column;
    gap: 16px;
    transition: all .3s ease-out;
    border-radius: 20px;
    border-radius: 10px;
    cursor: pointer;


    &:hover {
        padding: 5px;
        box-shadow: 0px 0px 25px rgba($color: #000000, $alpha: .07);
        gap: 12.6px;
        transition: all .3s ease-in;

        .image {
            border-radius: 15px;
            border-radius: 5px;
        }
    }

    .image {
        position: relative;
        height: 200px;
        align-self: stretch;
        background: #F8F8FA;
        display: flex;
        justify-content: center;
        align-items: center;

        .bestseller-label {
            position: absolute;
            top: 12px;
            left: 12px;
            display: flex;
            height: 32px;
            padding: 0px 8px;
            justify-content: center;
            align-items: center;
            gap: 4px;
            border-radius: 4px;
            border: 1px solid var(--tech-scroll-bar, #F2F2F2);
            background: var(--tech-white, #FFF);

            & > p {
                color: var(--font-primary, #333);
                text-align: right;
                font-size: 14px;
                line-height: 16px;
            }
        }
        .discount {
            display: inline-flex;
            padding: 6px 10px;
            justify-content: center;
            align-items: center;
            gap: 4px;
            position: absolute;
            left: 12px;
            bottom: 12px;
            border-radius: 4px;
            background: var(--brand-primary, #7397F5);
            color: var(--tech-white, #FFF);
            text-align: right;
            font-size: 14px;
            font-weight: 700;
            line-height: 14px; 
        }

    }
    .brand {
        color: #AAA;
        font-size: 14px;
        font-style: normal;
        font-weight: 400;
        line-height: 16px;
    }
    .name {
        color: var(--font-primary, #333);
        font-size: 14px;
        font-style: normal;
        font-weight: 400;
        line-height: 16px;
        transition: all .2s ease-out;


        &:hover {
            color: var(--font-hover, #125BAE);
            transition: all .2s ease-in;
        }
    }
    .cost {
        display: flex;
        height: 14px;
        gap: 8px;

        .current-cost {
            color: var(--font-primary, #333);
            font-size: 16px;
            font-weight: 700;
            line-height: 14px;
        }
        .former-cost {
            color: var(--font-secondary, #AAA);
            font-size: 12px;
            line-height: 14px;
            text-decoration-line: strikethrough;
        }
    }

    .buy-button {
        height: 38px;
        width: 75px;
        display: flex;
        padding: 12px 16px;
        justify-content: center;
        align-items: center;
        gap: 4px;
        border-radius: 4px;
        border: 1px solid var(--brand-primary, #7397F5);
        background: var(--tech-white, #FFF);

        color: var(--brand-primary, #7397F5);
        font-size: 14px;
        font-weight: 700;
        line-height: 14px;
        transition: all .2s ease-out;
        cursor: pointer;

        &:hover {
            background: #7397F5;
            color: #fff;
            transition: all .2s ease-in;
        }
    }
    .message-button {
        height: 38px;
        border-radius: 4px;
        border: 1px solid var(--font-secondary, #AAA);
        background: var(--tech-white, #FFF);

        color: var(--font-secondary, #AAA);
        font-family: PT Sans;
        font-size: 14px;
        font-weight: 700;
        line-height: 14px;
        cursor: pointer;

        &:hover {
            background: #AAA;
            color: #fff;
            transition: all .2s ease-in;
        }
    }


}


@media (max-width: 1770px) {
    .card {
        flex-basis: 23%;
    }
}

@media (max-width: 1530px) {
    .card {
        flex-basis: 22.8%;
    }
}

@media (max-width: 1440px) {
    .card {
        flex-basis: 22.5%;
    }
}

@media (max-width: 1330px) {
    .card {
        flex-basis: 48%;
    }
}

@media (max-width: 1120px) {
    .card {
        flex-basis: 47.5%;
    }
}
    
</style>