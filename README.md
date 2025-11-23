<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DriveEasy Rentals | Car & Motorcycle Rentals</title>
    <style>
        /* Reset and Base Styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --primary: #2c3e50;
            --secondary: #3498db;
            --accent: #e74c3c;
            --light: #ecf0f1;
            --dark: #2c3e50;
            --gray: #95a5a6;
        }
        
        body {
            line-height: 1.6;
            color: #333;
            background-color: #f9f9f9;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .btn {
            display: inline-block;
            padding: 12px 24px;
            background-color: var(--secondary);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s ease;
        }
        
        .btn:hover {
            background-color: #2980b9;
            transform: translateY(-2px);
        }
        
        .btn-accent {
            background-color: var(--accent);
        }
        
        .btn-accent:hover {
            background-color: #c0392b;
        }
        
        /* Header Styles */
        header {
            background-color: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 15px 0;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--primary);
        }
        
        .logo span {
            color: var(--secondary);
        }
        
        nav ul {
            display: flex;
            list-style: none;
        }
        
        nav ul li {
            margin-left: 30px;
        }
        
        nav ul li a {
            font-weight: 500;
            transition: color 0.3s ease;
        }
        
        nav ul li a:hover {
            color: var(--secondary);
        }
        
        .mobile-menu {
            display: none;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(44, 62, 80, 0.8), rgba(44, 62, 80, 0.8)), url('https://images.unsplash.com/photo-1486496572940-2bb2341fdbdf?ixlib=rb-1.2.1&auto=format&fit=crop&w=1950&q=80');
            background-size: cover;
            background-position: center;
            color: white;
            padding: 100px 0;
            text-align: center;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 30px;
        }
        
        /* Search Form */
        .search-form {
            background-color: white;
            border-radius: 8px;
            padding: 25px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            margin-top: 30px;
        }
        
        .form-group {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 15px;
        }
        
        .form-control {
            flex: 1;
            min-width: 200px;
            padding: 12px;
            border: 1px solid #ddd;
            border-radius: 4px;
        }
        
        /* Vehicle Categories */
        .categories {
            padding: 80px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }
        
        .section-title h2 {
            font-size: 2.2rem;
            color: var(--primary);
            margin-bottom: 15px;
        }
        
        .section-title p {
            color: var(--gray);
            max-width: 600px;
            margin: 0 auto;
        }
        
        .category-cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .category-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            transition: transform 0.3s ease;
        }
        
        .category-card:hover {
            transform: translateY(-10px);
        }
        
        .category-img {
            height: 200px;
            overflow: hidden;
        }
        
        .category-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s ease;
        }
        
        .category-card:hover .category-img img {
            transform: scale(1.1);
        }
        
        .category-content {
            padding: 20px;
        }
        
        .category-content h3 {
            font-size: 1.5rem;
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        .category-content p {
            color: var(--gray);
            margin-bottom: 15px;
        }
        
        /* Featured Vehicles */
        .featured-vehicles {
            padding: 80px 0;
            background-color: #f5f7fa;
        }
        
        .vehicle-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .vehicle-card {
            background-color: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .vehicle-img {
            height: 180px;
            overflow: hidden;
        }
        
        .vehicle-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .vehicle-details {
            padding: 20px;
        }
        
        .vehicle-details h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        .vehicle-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            color: var(--gray);
            font-size: 0.9rem;
        }
        
        .vehicle-price {
            font-size: 1.2rem;
            font-weight: 700;
            color: var(--secondary);
            margin-bottom: 15px;
        }
        
        /* How It Works */
        .how-it-works {
            padding: 80px 0;
        }
        
        .steps {
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 20px;
        }
        
        .step {
            flex: 1;
            min-width: 200px;
            text-align: center;
            padding: 30px 20px;
        }
        
        .step-icon {
            width: 80px;
            height: 80px;
            background-color: var(--light);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            margin: 0 auto 20px;
            font-size: 1.8rem;
            color: var(--secondary);
        }
        
        .step h3 {
            font-size: 1.3rem;
            margin-bottom: 10px;
            color: var(--primary);
        }
        
        /* Testimonials */
        .testimonials {
            padding: 80px 0;
            background-color: var(--light);
        }
        
        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }
        
        .testimonial-card {
            background-color: white;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .testimonial-text {
            font-style: italic;
            margin-bottom: 20px;
            color: var(--dark);
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
        }
        
        .author-img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            overflow: hidden;
            margin-right: 15px;
        }
        
        .author-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .author-info h4 {
            font-size: 1.1rem;
            margin-bottom: 5px;
        }
        
        .author-info p {
            color: var(--gray);
            font-size: 0.9rem;
        }
        
        /* Footer */
        footer {
            background-color: var(--primary);
            color: white;
            padding: 60px 0 20px;
        }
        
        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }
        
        .footer-column h3 {
            font-size: 1.3rem;
            margin-bottom: 20px;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-column h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 40px;
            height: 2px;
            background-color: var(--secondary);
        }
        
        .footer-column ul {
            list-style: none;
        }
        
        .footer-column ul li {
            margin-bottom: 10px;
        }
        
        .footer-column ul li a {
            transition: color 0.3s ease;
        }
        
        .footer-column ul li a:hover {
            color: var(--secondary);
        }
        
        .footer-bottom {
            text-align: center;
            padding-top: 20px;
            border-top: 1px solid rgba(255,255,255,0.1);
            font-size: 0.9rem;
            color: rgba(255,255,255,0.7);
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                padding: 15px 0;
            }
            
            .logo {
                margin-bottom: 15px;
            }
            
            nav ul {
                flex-direction: column;
                text-align: center;
            }
            
            nav ul li {
                margin: 10px 0;
            }
            
            .mobile-menu {
                display: block;
                position: absolute;
                top: 20px;
                right: 20px;
            }
            
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .form-group {
                flex-direction: column;
            }
            
            .steps {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-container">
            <div class="logo">JayNal <span>Car & Scooter </span> Lombok </span> Rentals</div>
            <nav>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#vehicles">Vehicles</a></li>
                    <li><a href="#how-it-works">How It Works</a></li>
                    <li><a href="#testimonials">Testimonials</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
            <div class="mobile-menu">☰</div>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <h1>Rent Cars & Motorcycles</h1>
            <p>Find the perfect vehicle for your journey at affordable prices. With DriveEasy Rentals, your adventure is just a click away.</p>
            <a href="#vehicles" class="btn">Browse Vehicles</a>
            
            <!-- Search Form -->
            <div class="search-form">
                <div class="form-group">
                    <input type="text" class="form-control" placeholder="Pick-up Location">
                    <input type="text" class="form-control" placeholder="Drop-off Location">
                </div>
                <div class="form-group">
                    <input type="date" class="form-control" placeholder="Pick-up Date">
                    <input type="date" class="form-control" placeholder="Drop-off Date">
                </div>
                <div class="form-group">
                    <select class="form-control">
                        <option value="">Vehicle Type</option>
                        <option value="car">Car</option>
                        <option value="motorcycle">Motorcycle</option>
                    </select>
                    <button class="btn btn-accent">Search Vehicles</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Vehicle Categories -->
    <section class="categories" id="vehicles">
        <div class="container">
            <div class="section-title">
                <h2>Our Vehicle Categories</h2>
                <p>Choose from our wide range of vehicles to suit your needs and budget</p>
            </div>
            
            <div class="category-cards">
                <div class="category-card">
                    <div class="category-img">
                        <img src="https://images.unsplash.com/photo-1549317661-bd32c8ce0db2?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Economy Cars">
                    </div>
                    <div class="category-content">
                        <h3>Economy Cars</h3>
                        <p>Fuel-efficient and affordable options for city driving and short trips.</p>
                        <a href="#" class="btn">View Options</a>
                    </div>
                </div>
                
                <div class="category-card">
                    <div class="category-img">
                        <img src="https://images.unsplash.com/photo-1503376780353-7e6692767b70?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Luxury Cars">
                    </div>
                    <div class="category-content">
                        <h3>Luxury Cars</h3>
                        <p>Premium vehicles for business trips or special occasions.</p>
                        <a href="#" class="btn">View Options</a>
                    </div>
                </div>
                
                <div class="category-card">
                    <div class="category-img">
                        <img src="https://images.unsplash.com/photo-1558618047-3c8c76ca7d13?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Motorcycles">
                    </div>
                    <div class="category-content">
                        <h3>Motorcycles</h3>
                        <p>For those who prefer two wheels, from scooters to sport bikes.</p>
                        <a href="#" class="btn">View Options</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Featured Vehicles -->
    <section class="featured-vehicles">
        <div class="container">
            <div class="section-title">
                <h2>Featured Vehicles</h2>
                <p>Check out our most popular rental options</p>
            </div>
            
            <div class="vehicle-grid">
                <div class="vehicle-card">
                    <div class="vehicle-img">
                        <img src="https://images.unsplash.com/photo-1542362567-b07e54358753?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Toyota Corolla">
                    </div>
                    <div class="vehicle-details">
                        <h3>Toyota Corolla</h3>
                        <div class="vehicle-info">
                            <span>Automatic</span>
                            <span>5 Seats</span>
                            <span>Air Conditioning</span>
                        </div>
                        <div class="vehicle-price">$35/day</div>
                        <a href="#" class="btn">Rent Now</a>
                    </div>
                </div>
                
                <div class="vehicle-card">
                    <div class="vehicle-img">
                        <img src="https://images.unsplash.com/photo-1555215695-3004980ad54e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="BMW 3 Series">
                    </div>
                    <div class="vehicle-details">
                        <h3>BMW 3 Series</h3>
                        <div class="vehicle-info">
                            <span>Automatic</span>
                            <span>5 Seats</span>
                            <span>Premium</span>
                        </div>
                        <div class="vehicle-price">$85/day</div>
                        <a href="#" class="btn">Rent Now</a>
                    </div>
                </div>
                
                <div class="vehicle-card">
                    <div class="vehicle-img">
                        <img src="https://images.unsplash.com/photo-1517677129300-07b130802f46?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Honda Scooter">
                    </div>
                    <div class="vehicle-details">
                        <h3>Honda Scooter</h3>
                        <div class="vehicle-info">
                            <span>Automatic</span>
                            <span>2 Seats</span>
                            <span>Fuel Efficient</span>
                        </div>
                        <div class="vehicle-price">$20/day</div>
                        <a href="#" class="btn">Rent Now</a>
                    </div>
                </div>
                
                <div class="vehicle-card">
                    <div class="vehicle-img">
                        <img src="https://images.unsplash.com/photo-1566474591183-3112b03938d7?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Yamaha Motorcycle">
                    </div>
                    <div class="vehicle-details">
                        <h3>Yamaha Motorcycle</h3>
                        <div class="vehicle-info">
                            <span>Manual</span>
                            <span>2 Seats</span>
                            <span>Adventure</span>
                        </div>
                        <div class="vehicle-price">$45/day</div>
                        <a href="#" class="btn">Rent Now</a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- How It Works -->
    <section class="how-it-works" id="how-it-works">
        <div class="container">
            <div class="section-title">
                <h2>How It Works</h2>
                <p>Renting a vehicle with DriveEasy is simple and straightforward</p>
            </div>
            
            <div class="steps">
                <div class="step">
                    <div class="step-icon">1</div>
                    <h3>Choose Your Vehicle</h3>
                    <p>Browse our selection and pick the perfect vehicle for your needs.</p>
                </div>
                
                <div class="step">
                    <div class="step-icon">2</div>
                    <h3>Book Online</h3>
                    <p>Select your dates and complete the quick booking process.</p>
                </div>
                
                <div class="step">
                    <div class="step-icon">3</div>
                    <h3>Pick Up & Go</h3>
                    <p>Collect your vehicle from our convenient locations and start your journey.</p>
                </div>
                
                <div class="step">
                    <div class="step-icon">4</div>
                    <h3>Return & Review</h3>
                    <p>Return the vehicle and share your experience with us.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Testimonials -->
    <section class="testimonials" id="testimonials">
        <div class="container">
            <div class="section-title">
                <h2>What Our Customers Say</h2>
                <p>Hear from travelers who have experienced DriveEasy Rentals</p>
            </div>
            
            <div class="testimonial-grid">
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "The booking process was so easy, and the car was in perfect condition. Will definitely use DriveEasy again for my next trip!"
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">
                            <img src="bunga.jpg" alt="Sarah Johnson">
                        </div>
                        <div class="author-info">
                            <h4>Sarah Johnson</h4>
                            <p>Business Traveler</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "Renting a motorcycle for our weekend trip was the best decision. The process was smooth and the bike was excellent."
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">
                            <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Michael Chen">
                        </div>
                        <div class="author-info">
                            <h4>Michael Chen</h4>
                            <p>Adventure Seeker</p>
                        </div>
                    </div>
                </div>
                
                <div class="testimonial-card">
                    <div class="testimonial-text">
                        "Great prices and even better service. The team helped me choose the perfect car for my family vacation. Highly recommended!"
                    </div>
                    <div class="testimonial-author">
                        <div class="author-img">
                            <img src="https://randomuser.me/api/portraits/women/68.jpg" alt="Emma Rodriguez">
                        </div>
                        <div class="author-info">
                            <h4>Emma Rodriguez</h4>
                            <p>Family Vacationer</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="container">
            <div class="footer-content">
                <div class="footer-column">
                    <h3>DriveEasy Rentals</h3>
                    <p>Your trusted partner for car and motorcycle rentals. We make your journey comfortable and memorable.</p>
                </div>
                
                <div class="footer-column">
                    <h3>Quick Links</h3>
                    <ul>
                        <li><a href="#home">Home</a></li>
                        <li><a href="#vehicles">Vehicles</a></li>
                        <li><a href="#how-it-works">How It Works</a></li>
                        <li><a href="#testimonials">Testimonials</a></li>
                    </ul>
                </div>
                
                <div class="footer-column">
                    <h3>Contact Us</h3>
                    <ul>
                        <li>Jalan Raden Puguh puyung, Loteng NTB</li>
                        <li>Phone: (+62) 81917721277 whatsap</li>
                        <li>Email: enalcbs@gmail.com</li>
                    </ul>
					
					
					
                </div>
            <div class="footer-bottom">
                <p>&copy; 2025 DriveEasy Rentals. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Simple JavaScript for mobile menu toggle
        document.querySelector('.mobile-menu').addEventListener('click', function() {
            document.querySelector('nav ul').classList.toggle('show');
        });
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>
