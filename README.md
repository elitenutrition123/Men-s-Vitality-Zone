# Men-s-Vitality-Zone// Simple JavaScript for the landing page
document.addEventListener('DOMContentLoaded', function() {
    // Smooth scrolling for anchor links
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
            e.preventDefault();
            
            const targetId = this.getAttribute('href');
            const targetElement = document.querySelector(targetId);
            
            if (targetElement) {
                window.scrollTo({
                    top: targetElement.offsetTop - 80,
                    behavior: 'smooth'
                });
            }
        });
    });

    // Add active class to nav items on scroll
    const sections = document.querySelectorAll('section[id]');
    
    window.addEventListener('scroll', function() {
        const scrollPosition = window.scrollY + 100;
        
        sections.forEach(section => {
            const sectionTop = section.offsetTop;
            const sectionHeight = section.offsetHeight;
            const sectionId = section.getAttribute('id');
            
            if (scrollPosition >= sectionTop && scrollPosition < sectionTop + sectionHeight) {
                document.querySelector('nav a[href="#' + sectionId + '"]')?.classList.add('active');
            } else {
                document.querySelector('nav a[href="#' + sectionId + '"]')?.classList.remove('active');
            }
        });
    });

    // Add countdown timer for urgency
    const countdownElement = document.createElement('div');
    countdownElement.className = 'countdown';
    countdownElement.innerHTML = '<p><strong>Limited Time Offer Ends In:</strong> <span id="countdown-timer">23:59:59</span></p>';
    
    const ctaBanner = document.querySelector('.cta-banner .container');
    if (ctaBanner) {
        ctaBanner.appendChild(countdownElement);
    }
    
    // Set the countdown timer
    let hours = 23;
    let minutes = 59;
    let seconds = 59;
    
    const countdownTimer = setInterval(function() {
        seconds--;
        
        if (seconds < 0) {
            seconds = 59;
            minutes--;
            
            if (minutes < 0) {
                minutes = 59;
                hours--;
                
                if (hours < 0) {
                    hours = 23;
                }
            }
        }
        
        const formattedTime = 
            (hours < 10 ? '0' + hours : hours) + ':' + 
            (minutes < 10 ? '0' + minutes : minutes) + ':' + 
            (seconds < 10 ? '0' + seconds : seconds);
        
        document.getElementById('countdown-timer').textContent = formattedTime;
    }, 1000);
});
Men's Vitality Zone
	•	Top Products
	•	Benefits
	•	Testimonials
	•	FAQ
Reclaim Your Natural Vitality
Premium Men's Health Supplements That Actually Work
Scientifically formulated natural ingredients to boost energy, enhance performance, and restore confidence.
Explore Top Products
100% Natural Ingredients
Scientifically Tested
Satisfaction Guaranteed
Fast & Discreet Shipping
Top-Rated Men's Health Supplements
Carefully selected premium products with proven results
BEST SELLER

Emperor's Vigor Tonic
(487 reviews)
Premium male enhancement supplement that supports stamina, strength, and vitality. Ancient formula with modern science.
	•	Boosts natural energy levels
	•	Enhances performance & stamina
	•	Supports healthy testosterone
	•	Improves confidence & mood
$97 $67 31% OFF
Get Emperor's Vigor Tonic
60-Day Money Back Guarantee

Aizen Power
(342 reviews)
Scientifically-created male enhancement supplement that increases vitality and performance with natural ingredients.
	•	Enhances male vitality
	•	Boosts energy & endurance
	•	Improves blood circulation
	•	Supports overall wellness
$89 $69 22% OFF
Get Aizen Power
60-Day Money Back Guarantee

Primal Grow Pro
(289 reviews)
Inspired by ancient African rituals, this unique formula helps absorb essential nutrients for male enhancement.
	•	Natural performance boost
	•	Increases confidence
	•	Enhances satisfaction
	•	Supports nutrient absorption
$99 $69 30% OFF
Get Primal Grow Pro
60-Day Money Back Guarantee
Limited Time Offer: Save Up To 31% Today!
Plus get free shipping on all orders over $100
Shop Now
Why Choose Our Supplements?
Premium quality backed by science and thousands of satisfied customers

Scientifically Formulated
Our supplements are developed by leading scientists and health experts to ensure maximum effectiveness.

100% Natural Ingredients
We use only the highest quality natural ingredients, with no harmful chemicals or artificial additives.

Rigorous Testing
Every batch undergoes extensive testing to ensure purity, potency, and safety for optimal results.

Money-Back Guarantee
We stand behind our products with a 60-day money-back guarantee for your complete satisfaction.
What Our Customers Say
Real results from real men just like you

"I've tried many supplements over the years, but Emperor's Vigor Tonic is in a league of its own. Within just 2 weeks, I noticed a significant boost in my energy levels and overall performance. At 52, I feel like I'm in my 30s again!"
Michael R.
Age 52, Verified Customer

"After trying Aizen Power for a month, I can confidently say this product delivers on its promises. My stamina has improved dramatically, and my wife has definitely noticed the difference. The natural ingredients give me peace of mind too."
David T.
Age 45, Verified Customer

"Primal Grow Pro has been a game-changer for me. As someone who was skeptical about supplements, I was pleasantly surprised by the results. Not only has my performance improved, but I also feel more confident and energetic throughout the day."
James L.
Age 38, Verified Customer
How It Works
Simple, effective, and backed by science
1

Choose Your Product
Select the supplement that best addresses your specific needs and goals.
2

Take Daily
Follow the recommended dosage instructions for optimal results.
3

Experience Results
Most men report noticeable improvements within 2-4 weeks of consistent use.
4

(Content truncated due to size limit. Use line ranges to read in chunks)
/* Base Styles */
:root {
    --primary-color: #2c3e50;
    --secondary-color: #e74c3c;
    --accent-color: #3498db;
    --light-color: #ecf0f1;
    --dark-color: #2c3e50;
    --text-color: #333;
    --light-text: #fff;
    --border-radius: 8px;
    --box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    --transition: all 0.3s ease;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: 'Poppins', sans-serif;
    line-height: 1.6;
    color: var(--text-color);
    background-color: #f9f9f9;
}

.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
}

h1, h2, h3, h4, h5, h6 {
    font-family: 'Montserrat', sans-serif;
    font-weight: 700;
    line-height: 1.3;
    margin-bottom: 15px;
}

p {
    margin-bottom: 15px;
}

a {
    text-decoration: none;
    color: var(--accent-color);
    transition: var(--transition);
}

a:hover {
    color: var(--secondary-color);
}

ul {
    list-style: none;
}

img {
    max-width: 100%;
    height: auto;
    display: block;
}

.section-title {
    font-size: 2.5rem;
    text-align: center;
    margin-bottom: 10px;
    color: var(--primary-color);
}

.section-subtitle {
    font-size: 1.1rem;
    text-align: center;
    margin-bottom: 40px;
    color: #666;
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
}

/* Buttons */
.btn {
    display: inline-block;
    padding: 12px 25px;
    border-radius: var(--border-radius);
    font-weight: 600;
    text-align: center;
    cursor: pointer;
    transition: var(--transition);
    border: none;
    font-size: 1rem;
}

.btn-primary {
    background-color: var(--secondary-color);
    color: var(--light-text);
}

.btn-primary:hover {
    background-color: #c0392b;
    color: var(--light-text);
    transform: translateY(-3px);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
}

.btn-secondary {
    background-color: var(--accent-color);
    color: var(--light-text);
}

.btn-secondary:hover {
    background-color: #2980b9;
    color: var(--light-text);
    transform: translateY(-3px);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
}

.btn-light {
    background-color: var(--light-color);
    color: var(--dark-color);
}

.btn-light:hover {
    background-color: #fff;
    color: var(--dark-color);
    transform: translateY(-3px);
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
}

.btn-full {
    width: 100%;
    display: block;
}

.btn-large {
    padding: 15px 30px;
    font-size: 1.1rem;
}

/* Header */
header {
    background-color: var(--primary-color);
    padding: 15px 0;
    position: sticky;
    top: 0;
    z-index: 1000;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}

header .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.logo h1 {
    color: var(--light-text);
    font-size: 1.5rem;
    margin-bottom: 0;
}

nav ul {
    display: flex;
}

nav ul li {
    margin-left: 20px;
}

nav ul li a {
    color: var(--light-text);
    font-weight: 500;
    padding: 5px 10px;
    border-radius: var(--border-radius);
}

nav ul li a:hover {
    background-color: rgba(255, 255, 255, 0.1);
}

/* Hero Section */
.hero {
    background: linear-gradient(rgba(44, 62, 80, 0.8), rgba(44, 62, 80, 0.8)), url('../assets/hero-bg.jpg');
    background-size: cover;
    background-position: center;
    color: var(--light-text);
    padding: 100px 0;
    text-align: center;
}

.hero-content {
    max-width: 800px;
    margin: 0 auto;
}

.hero h1 {
    font-size: 3rem;
    margin-bottom: 15px;
    text-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
}

.hero h2 {
    font-size: 1.8rem;
    margin-bottom: 20px;
    font-weight: 500;
}

.hero p {
    font-size: 1.2rem;
    margin-bottom: 30px;
    opacity: 0.9;
}

/* Trust Badges */
.trust-badges {
    background-color: #fff;
    padding: 30px 0;
    box-shadow: var(--box-shadow);
}

.trust-badges .container {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}

.badge {
    text-align: center;
    flex: 1;
    min-width: 200px;
    padding: 15px;
}

.badge i {
    font-size: 2rem;
    color: var(--accent-color);
    margin-bottom: 10px;
}

.badge p {
    font-weight: 500;
    margin-bottom: 0;
}

/* Products Section */
.products {
    padding: 80px 0;
    background-color: #f9f9f9;
}

.product-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
    margin-top: 40px;
}

.product-card {
    background-color: #fff;
    border-radius: var(--border-radius);
    overflow: hidden;
    box-shadow: var(--box-shadow);
    transition: var(--transition);
    position: relative;
}

.product-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
}

.product-card.featured {
    border: 2px solid var(--secondary-color);
    transform: scale(1.03);
}

.product-card.featured:hover {
    transform: scale(1.03) translateY(-10px);
}

.product-badge {
    position: absolute;
    top: 20px;
    right: -35px;
    background-color: var(--secondary-color);
    color: var(--light-text);
    padding: 8px 40px;
    font-weight: 600;
    transform: rotate(45deg);
    z-index: 1;
    font-size: 0.8rem;
}

.product-image {
    height: 200px;
    overflow: hidden;
    background-color: #f5f5f5;
    display: flex;
    align-items: center;
    justify-content: center;
}

.product-image img {
    max-height: 180px;
    object-fit: contain;
    transition: var(--transition);
}

.product-card:hover .product-image img {
    transform: scale(1.05);
}

.product-details {
    padding: 25px;
}

.product-details h3 {
    font-size: 1.5rem;
    margin-bottom: 10px;
}

.rating {
    color: #f39c12;
    margin-bottom: 15px;
    display: flex;
    align-items: center;
}

.rating span {
    color: #777;
    margin-left: 10px;
    font-size: 0.9rem;
}

.product-description {
    margin-bottom: 20px;
    color: #666;
}

.product-benefits {
    margin-bottom: 20px;
}

.product-benefits li {
    margin-bottom: 8px;
    display: flex;
    align-items: flex-start;
}

.product-benefits li i {
    color: var(--secondary-color);
    margin-right: 10px;
    margin-top: 5px;
}

.product-price {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
    flex-wrap: wrap;
}

.original-price {
    text-decoration: line-through;
    color: #999;
    margin-right: 10px;
    font-size: 1.1rem;
}

.discount-price {
    font-size: 1.8rem;
    font-weight: 700;
    color: var(--secondary-color);
    margin-right: 10px;
}

.discount-label {
    background-color: var(--secondary-color);
    color: var(--light-text);
    padding: 3px 8px;
    border-radius: 4px;
    font-size: 0.8rem;
    font-weight: 600;
}

.guarantee {
    text-align: center;
    margin-top: 15px;
    font-size: 0.9rem;
    color: #666;
}

.guarantee i {
    color: var(--accent-color);
    margin-right: 5px;
}

/* CTA Banner */
.cta-banner {
    background: linear-gradient(to right, var(--secondary-color), #d35400);
    color: var(--light-text);
    padding: 50px 0;
    text-align: center;
}

.cta-banner h2 {
    font-size: 2rem;
    margin-bottom: 10px;
}

.cta-banner p {
    font-size: 1.1rem;
    margin-bottom: 20px;
    opacity: 0.9;
}

/* Benefits Section */
.benefits {
    padding: 80px 0;
    background-color: #fff;
}

.benefits-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 30px;
    margin-top: 40px;
}

.benefit-card {
    text-align: center;
    padding: 30px;
    border-radius: var(--border-radius);
    background-color: #f9f9f9;
    transition: var(--transition);
}

.benefit-card:hover {
    transform: translateY(-10px);
    box-shadow: var(--box-shadow);
}

.benefit-icon {
    width: 80px;
    height: 80px;
    background-color: var(--accent-color);
    color: var(--light-text);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 20px;
}

.benefit-icon i {
    font-size: 2rem;
}

.benefit-card h3 {
    font-size: 1.3rem;
    margin-bottom: 15px;
}

/* Testimonials Section */
.testimonials {
    padding: 80px 0;
    background-color: #f9f9f9;
}

.testimonial-slider {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
    margin-top: 40px;
}

.testimonial {
    background-color: #fff;
    border-radius: var(--border-radius);
    padding: 30px;
    box-shadow: var(--box-shadow);
    transition: var(--transition);
}

.testimonial:hover {
    transform: translateY(-5px);
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
}

.testimonial-rating {
    color: #f39c12;
    margin-bottom: 15px;
}

.testimonial-text {
    font-style: italic;
    margin-bottom: 20px;
    color: #555;
}

.testimonial-author {
    display: flex;
    align-items: center;
}

.testimonial-author img {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    object-fit: cover;
    margin-right: 15px;
}

.testimonial-author h4 {
    margin-bottom: 5px;
    font-size: 1.1rem;
}

.testimonial-author p {
    margin-bottom: 0;
    font-size: 0.9rem;
    color: #777;
}

/* How It Works Section */
.how-it-works {
    padding: 80px 0;
    background-color: #fff;
}

.steps {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    margin-top: 40px;
}

.step {
    flex: 1;
    min-width: 200px;
    text-align: center;
    padding: 20px;
    position: relative;
}

.step:not(:last-child)::after {
    content: '';
    position: absolute;
    top: 30%;
    right: 0;
    width: 50px;
    height: 2px;
    background-color: #ddd;
}

.step-number {
    width: 40px;
    height: 40px;
    background-color: var(--secondary-color);
    color: var(--light-text);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 15px;
    font-weight: 600;
}

.step-icon {
    width: 70px;
    height: 70px;
    background-color: #f5f5f5;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0 auto 15px;
}

.step-icon i {
    font-size: 1.8rem;
    color: var(--accent-color);
}

.step h3 {
    font-size: 1.2rem;
    margin-bottom: 10px;
}

/* FAQ Section */
.faq {
    padding: 80px 0;
    background-color: #f9f9f9;
}

.faq-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(450px, 1fr));
    gap: 30px;
    margin-top: 40px;
}

.faq-item {
    background-color: #fff;
    border-radius: var(--border-radius);
    padding: 25px;
    box-shadow: var(--box-shadow);
}

.faq-item h3 {
    font-size: 1.2rem;
    margin-bottom: 15px;
    color: var(--primary-color);
}

.faq-item p {
    color: #666;
    margin-bottom: 0;
}

/* Final CTA Section */
.final-cta {
    padding: 80px 0;
    background: linear-gradient(rgba(44, 62, 80, 0.9), rgba(44, 62, 80, 0.9)), url('../assets/cta-bg.jpg');
    background-size: cover;
    background-position: center;
    color: var(--light-text);
    text-align: center;
}

.final-cta h2 {
    font-size: 2.5rem;
    margin-bottom: 15px;
}

.final-cta p {
    font-size: 1.2rem;
    margin-bottom: 30px;
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
}

.guarantee-badge {
    display: flex;
    align-items: center;
    justify-content: center;
    margin-top: 30px;
}

.guarantee-badge i {
    font-size: 2rem;
    margin-right: 15px;
    color: var(--accent-color);
}

.guarantee-badge p {
    margin-bottom: 0;
    font-weight: 600;
}

/* Footer */
footer {
    background-color: var(--primary-color);
    color: var(--light-text);
    padding: 60px 0 20px;
}

.footer-content {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 40px;
    margin-bottom: 40px;
}

.footer-logo h2 {
    font-size: 1.8rem;
    margin-bottom: 10px;
}

.footer-logo p {
    opacity: 0.8;
}

.footer-links h3, .footer-contact h3 {
    font-size: 1.3rem;
    margin-bottom: 20px;
    position: relative;
    padding-bottom: 10px;
}

.footer-links h3::after, .footer-contact h3::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 50px;
    height: 2px;
    background-color: var(--secondary-color);
}

.footer-links ul li {
    margin-bottom: 10px;
}

.footer-links ul li a {
    color: #ccc;
}

.footer-links ul li a:hover {
    color: var(--light-text);
}

.footer-contact p {
    margin-bottom: 15px;
    display: flex;
    align-items: center;
}

.footer-contact p i {
    margin-right: 10px;
    color: var(--accent-color);
}

.social-icons {
    display: flex;
    margin-top: 20px;
}

.social-icons a {
    width: 40px;
    height: 40px;
    background-color: rgba(255, 255, 255, 0.1);
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-right: 10px;
    color: var(--light-text);
}

.social-icons a:hover {
    background-color: var(--secondary-color);
    transform: translateY(-3px);
}

.footer-bottom {
    text-align: center;
    padding-top: 20px;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.footer-bottom p {
    margin-bottom: 10px;
    font-size: 0.9rem;
    opacity: 0.8;
}

.footer-bottom a {
    color: #ccc;
}

.footer-bottom a:hover {
    color: var(--light-text);
}

.disclaimer {
    font-size: 0.8rem;
    opacity: 0.6;
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
}

/* Responsive Styles */
@media (max-width: 992px) {
    .section-title {
        font-size: 2rem;
    }
    
    .hero h1 {
        font-size: 2.5rem;
    }
    
    .hero h2 {
        font-size: 1.5rem;
    }
    
    .step:not(:last-child)::after {
        display: none;
    }
    
    .faq-grid {
        grid-template-columns: 1fr;
    }
}

@media (max-width: 768px) {
    header .container {
        flex-direction: column;
    }
    
    nav ul {
        margin-top: 15px;
    }
    
    nav ul li {
        margin: 0 10px;
    }
    
    .hero {
        padding: 60px 0;
    }
    
    .hero h1 {
        font-size: 2rem;
    }
    
    .badge {
        min-width: 150px;
    }
    
    .steps {
        flex-direction: column;
    }
    
    .step {
        margin-bottom: 30px;
    }
}

@media (max-width: 576px) {
    .section-title {
        font-size: 1.8rem;
    }
    
    .section-subtitle {
        font-size: 1rem;
    }
    
    .trust-badges .container {
        flex-direction: column;
    }
    
    .badge {
        margin-bottom: 20px;
    }
    
    .product-grid {
        grid-template-columns: 1fr;
    }
    
    .benefits-grid {
        grid-template-columns: 1fr;
    }
    
    .testimonial-slider {
        grid-template-columns: 1fr;
    }
    
    .final-cta h2 {
        font-size: 1.8rem;
    }
