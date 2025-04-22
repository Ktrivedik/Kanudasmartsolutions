document.addEventListener("DOMContentLoaded", function() {
    // Smooth scrolling effect for navigation links
    const navLinks = document.querySelectorAll("nav ul li a");
    navLinks.forEach(link => {
        link.addEventListener("click", function(event) {
            event.preventDefault();
            const targetId = this.getAttribute("href").substring(1);
            document.getElementById(targetId).scrollIntoView({ behavior: "smooth" });
        });
    });

    // Product hover effect to expand details
    const productCards = document.querySelectorAll(".product");
    productCards.forEach(card => {
        card.addEventListener("mouseover", function() {
            this.style.boxShadow = "0px 6px 12px rgba(0,0,0,0.3)";
        });
        card.addEventListener("mouseout", function() {
            this.style.boxShadow = "0px 4px 8px rgba(0,0,0,0.2)";
        });
    });

    // Simple form validation for Contact Us section
    const contactForm = document.querySelector("form");
    contactForm.addEventListener("submit", function(event) {
        event.preventDefault();
        const name = document.querySelector('input[type="text"]').value.trim();
        const email = document.querySelector('input[type="email"]').value.trim();
        const message = document.querySelector('textarea').value.trim();

        if (name === "" || email === "" || message === "") {
            alert("Please fill out all fields.");
        } else {
            alert("Thank you for your inquiry! We’ll get back to you soon.");
            contactForm.reset();
        }
    });
});