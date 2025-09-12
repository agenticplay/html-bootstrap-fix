**Script for braga mobile temp**

<!-- Script -->
<script>
function hideLoader() {
    const loader = document.getElementById("loader");
    loader.style.opacity = "0";
    setTimeout(() => {
        loader.style.display = "none";
    }, 500);
}

function showLoader() {
    const loader = document.getElementById("loader");
    loader.style.display = "flex";
    setTimeout(() => {
        loader.style.opacity = "1";
    }, 10);
}

// Hide loader on normal load and when returning via back/forward cache
window.addEventListener("DOMContentLoaded", hideLoader);
window.addEventListener("pageshow", (event) => {
    if (event.persisted) { // true if page came from bfcache
        hideLoader();
    }
});

// Handle link clicks
document.querySelectorAll("a").forEach(link => {
    link.addEventListener("click", e => {
        const url = link.getAttribute("href");
        if (!url || url.startsWith("#") || url.startsWith("javascript:")) return;
        showLoader();
    });
});

// Handle form submits
document.querySelectorAll("form").forEach(form => {
    form.addEventListener("submit", e => {
        showLoader();
    });
});

</script>
        
