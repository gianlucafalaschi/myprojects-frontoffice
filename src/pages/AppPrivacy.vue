<script>
export default {
    name: 'AppPrivacy'
}
</script>

<template>
    <section class="ms-hero d-flex justify-content-center align-items-center">
        <div class="ms-inside-hero">
            <h1>PRIVACY POLICY</h1>
        </div>
    </section>
    
    <section class="ms-privacy-text">
        <div class="container">
            <div class="row">
                <div class="col">
                    <div class="py-5 border-bottom border-3">
                        <p>Dear User,</p>
                        <p>Thank you for visiting our site!</p>
                    </div>
                    <div class="py-5 border-bottom border-3">
                        <p>This policy (the “Policy”) describes how we process your personal data, in compliance with Regulation (EU) 2016/679 (the “GDPR”), Italian Legislative Decree 196/2003, as amended (the “Privacy Code”), the provisions and guidelines issued by national and European data protection authorities, as well as applicable national and European law (jointly, the “Applicable Law”).</p>
                        <p>Some of our services may be subject to specific policies (such as, for example, the services offered through our dedicated portals), in which case we will provide you with all the relevant information as and when required, making it available in each dedicated section.</p>
                        <p>For further information on how this Website uses cookies, see our Cookie Policy.</p>
                        <p>Last updated: October 2024</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped lang="scss">
/* * {
    border: 1px solid pink;
} */

.ms-hero {
    width: 100%;
    height: 400px;
    background-image: url(../assets/omar-prestwich-0HAPFlyy9o4-unsplash.jpg);
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
}

.ms-inside-hero {
    color: white;
    font-style: italic;
    display: flex;
    justify-content: center;

    h1 {
        font-size: 12vw;

    }
}

.ms-privacy-text {
    background-color: #111111;
    color: white;
}



/* MEDIA QUERIES */

/*----------------
    COLUMNS per XS > 0px
-----------------*/


/*----------------
    COLUMNS per SM >= 576px
-----------------*/
@media screen and (min-width: 576px) {}

/*----------------
COLUMNS per MD >= 768px
-----------------*/
@media screen and (min-width: 768px) {}

/*----------------
COLUMNS per LG >= 992px
-----------------*/
@media screen and (min-width: 992px) {}

/*----------------
COLUMNS per XL >= 1200px
-----------------*/
@media screen and (min-width: 1200px) {
    .ms-inside-hero {
        h1 {
            font-size: 10vw;

        }
    }
}

/*----------------
COLUMNS per XXL >= 1400px
-----------------*/
@media screen and (min-width: 1400px) {
    .ms-inside-hero {
        h1 {
            font-size: 8vw;

        }
    }
}
</style>
