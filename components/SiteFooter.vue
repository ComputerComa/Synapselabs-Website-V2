<template>
    <footer class="footer">
        <div class="container">
            <div class="footer-content">
           <div class="footer-bottom">
                <p>&copy; 2025 Synapselabs Tech Solutions. All rights reserved.</p>
            </div>
        </div>
        </div>
    </footer>
</template>

<script>
export default {
    name: "Footer",
};
</script>

<style scoped>
.footer {
    background-color: #222;
    color: #fff;
    padding: 20px 0;
}

.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 15px;
}

.footer-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
}

.footer-logo img {
    max-height: 50px;
}

.footer-nav ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    gap: 15px;
}

.footer-nav a {
    color: #fff;
    text-decoration: none;
}



.footer-bottom {
    text-align: center;
    margin-top: 20px;
    font-size: 0.9rem;
    color: #aaa;
}
</style>