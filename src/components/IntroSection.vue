<template>
    <section id="intro">
        <div class="intro__inner">
            <h2 class="intro__title">port developer</h2>
            <div class="intro__lines" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
            <div class="intro__text">
                <div class="text">
                    <div>talent is</div>
                    <div>found at the end of the</div>
                    <div>effort</div>
                </div>
                <div class="img">
                    <img
                        src="https://images.unsplash.com/photo-1535295972055-1c762f4483e5?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTA3fHxwZW9wbGV8ZW58MHx8MHx8fDA%3D"
                        alt=""
                    />
                </div>
            </div>
            <div class="intro__lines bottom" aria-hidden="true">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
#intro {
    height: 100vh;

    .intro__inner {
        width: 100%;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        padding: 16px;

        .intro__title {
            font-size: 10vw;
            line-height: 1;
            font-weight: 700;
            white-space: nowrap;
            text-transform: uppercase;
            letter-spacing: -0.3vw;
            text-indent: -0.5vw;
            color: #372936;
        }
        .intro__lines {
            width: 100%;
            .line {
                display: block;
                width: 100%;
                height: 1px;
                background-color: #ee7894;
                margin-top: 0.5vw;

                &:nth-child(1) {
                    height: 1px;
                }
                &:nth-child(2) {
                    height: 2px;
                }
                &:nth-child(3) {
                    height: 4px;
                }
                &:nth-child(4) {
                    height: 8px;
                }
                &:nth-child(5) {
                    height: 10px;
                }
                &:nth-child(6) {
                    height: 15px;
                }
                &:nth-child(7) {
                    height: 20px;
                }
            }
            &.bottom {
                .line {
                    background-color: #ee7894;

                    &:nth-child(1) {
                        height: 7px;
                    }
                    &:nth-child(2) {
                        height: 6px;
                    }
                    &:nth-child(3) {
                        height: 5px;
                    }
                    &:nth-child(4) {
                        height: 4px;
                    }
                    &:nth-child(5) {
                        height: 3px;
                    }
                    &:nth-child(6) {
                        height: 2px;
                    }
                    &:nth-child(7) {
                        height: 1px;
                    }
                }
            }
        }
        .intro__text {
            width: 100%;
            height: 40vh;
            background-color: #2e43ae;
            color: var(--white);
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            position: relative;

            .text {
                font-size: 3vw;
                line-height: 1;
                font-weight: 700;
                text-transform: uppercase;
                text-decoration: underline;
                text-align: center;
                position: relative;
                z-index: 100;
                transition: all 0.3s;
                cursor: all-scroll;
            }
            .img {
                position: absolute;
                left: 50%;
                top: 50%;
                transform: translate(-50%, -50%);
                width: 30vh;
                height: 30vh;
                border-radius: 50%;
                overflow: hidden;
                filter: grayscale(100%);
                transition: all 0.3s;
            }
        }
    }
}
</style>
