<template>
    <section class="intro">
        <div class="intro-wrap">
            <div class="descript-wrap">
                <div class="text-intro-group">
                    <h1 class="descript-head">Intro</h1>
                    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ab, dolores enim et deserunt consectetur
                        minus
                        velit incidunt laboriosam quod explicabo. Ut et eius culpa pariatur!</p>
                    <div class="btn-wrap"><button class="btn">show</button></div>
                </div>
            </div>
            <div class="photo-wrap">
                <img :src="sasha"
                 alt="me"
                 class="photo">
            </div>
        </div>
    </section>
</template>
<script>
import sasha from '@/assets/pic/sasha.jpg'
export default {
    name: 'IntroComp',
    data() {
        return {
            sasha
        }
    }
}
</script>
<style>
.intro-wrap {
    width: 100%;
    height: calc(100svh - 80px);
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: auto auto;
}

.photo {
    object-fit: cover;
    height: inherit;
    width: 100%;
}

.photo-wrap {
    width: 50%;
    height: inherit;
    display: flex;
    justify-content: center;
    align-items: center;
}

.btn {
    all: unset;
    cursor: pointer;
    padding: 10px 40px;
    border-radius: 12px;
    background-color: #000;
    color: #fff;
}

.btn-wrap {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 20px;

}

.descript-head {
    font-size: 3rem;
    margin-bottom: 20px;
}

.descript-wrap p {
    text-align: left;
}

.descript-wrap {
    width: 50%;
    height: inherit;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.text-intro-group {
    padding: 0 20px;
    max-width: 550px;
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
}


@media screen and (max-width: 700px) {
    .intro-wrap {
        flex-direction: column;
    }

    .photo-wrap {
        width: 100%;
        height: 300px;
    }

    .descript-wrap {
        width: 100%;
        height: 50%;
    }

}
</style>
