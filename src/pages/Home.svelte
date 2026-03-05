<script>
    import resumePdf from "../assets/Francq_Resume_Professional.pdf";

    let formData = $state({
        name: "",
        email: "",
        message: ""
    });

    function handleSubmit(e) {
        e.preventDefault();
        // For now, construct mailto link
        const subject = encodeURIComponent(`Portfolio Contact from ${formData.name}`);
        const body = encodeURIComponent(`From: ${formData.name}\nEmail: ${formData.email}\n\n${formData.message}`);
        window.location.href = `mailto:ash.francq@gmail.com?subject=${subject}&body=${body}`;
    }
</script>

<section class="home">
    <!-- Hero Section -->
    <header class="hero">
        <div class="hero-content">
            <div class="photo-spacer">
                <!-- AF circle is rendered in App.svelte and animates here -->
            </div>
            <div class="hero-text">
                <h1>Ash Francq</h1>
                <p class="title">Software Engineer · ML Researcher</p>
                <p class="tagline">"Creating machines that can truly create"</p>
            </div>
        </div>
        
        <!-- Minimalist Dragon -->
        <svg class="dragon" viewBox="0 0 200 160" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M160 20 Q180 30 175 50 Q170 70 150 80 L140 75 Q155 65 158 50 Q160 35 150 28 Z" stroke="currentColor" stroke-width="1.5" fill="none"/>
            <path d="M150 80 Q130 90 110 85 Q90 80 80 90 Q70 100 75 115 Q80 130 100 135" stroke="currentColor" stroke-width="1.5" fill="none"/>
            <path d="M100 135 Q120 140 140 130 Q160 120 165 100" stroke="currentColor" stroke-width="1.5" fill="none"/>
            <path d="M75 115 L60 125 M75 120 L55 135 M80 125 L65 140" stroke="currentColor" stroke-width="1" fill="none"/>
            <path d="M110 85 Q115 70 130 65 Q145 60 150 70" stroke="currentColor" stroke-width="1" fill="none" opacity="0.6"/>
            <circle cx="162" cy="42" r="2" fill="currentColor"/>
            <path d="M170 35 L185 25 M172 38 L190 32" stroke="currentColor" stroke-width="1" fill="none"/>
        </svg>
    </header>

    <!-- About Section -->
    <section class="about">
        <h2>About</h2>
        <p>
            I'm a Software Engineer with <strong>4 years of experience</strong> building production systems, 
            with deep interests in <em>machine learning</em>, <em>learning theory</em>, and <em>artificial intelligence</em>.
        </p>
        <p>
            My research background spans <strong>Applied Machine Learning</strong> — where I've published work — 
            to current explorations in <strong>Learning Theory</strong> and <strong>Neuromorphic Computing</strong> implementations in Rust.
        </p>
        <p>
            I believe the next frontier lies in understanding how machines can genuinely learn and create, 
            not just pattern-match. That's what drives my work.
        </p>
    </section>

    <!-- Highlights -->
    <section class="highlights">
        <div class="stat">
            <span class="number">4+</span>
            <span class="label">Years Engineering</span>
        </div>
        <div class="stat">
            <span class="number">1</span>
            <span class="label">Published Paper</span>
        </div>
        <div class="stat">
            <span class="number">∞</span>
            <span class="label">Curiosity</span>
        </div>
    </section>

    <!-- Reading List -->
    <section class="reading">
        <h2>Current Reading</h2>
        <p class="reading-intro">Textbooks I'm working through:</p>
        <ul class="reading-list">
            <li>
                <span class="book-title">Understanding Machine Learning: From Theory to Algorithms</span>
                <span class="book-author">Shalev-Shwartz & Ben-David</span>
            </li>
            <li>
                <span class="book-title">Neuromorphic Computing and Engineering</span>
                <span class="book-author">Various</span>
            </li>
            <!-- Add more books as needed -->
        </ul>
    </section>

    <!-- CTA -->
    <section class="cta">
        <p>Explore my work in the sidebar — each language represents a domain of projects.</p>
        <a href={resumePdf} download="Francq_Resume.pdf" class="btn btn-primary">
            Download Resume
        </a>
    </section>

    <!-- Contact Section -->
    <section class="contact" id="contact">
        <h2>Get in Touch</h2>
        <p>Interested in collaboration, research opportunities, or just want to connect?</p>
        
        <div class="contact-methods">
            <a href="https://github.com/AFrancq" target="_blank" rel="noopener" class="contact-link">
                <svg viewBox="0 0 24 24" fill="currentColor" width="24" height="24">
                    <path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0024 12c0-6.63-5.37-12-12-12z"/>
                </svg>
                <span>GitHub</span>
            </a>
            <a href="tel:+1234567890" class="contact-link">
                <svg viewBox="0 0 24 24" fill="currentColor" width="24" height="24">
                    <path d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"/>
                </svg>
                <span>Phone</span>
            </a>
        </div>

        <form class="contact-form" onsubmit={handleSubmit}>
            <div class="form-group">
                <label for="name">Name</label>
                <input type="text" id="name" bind:value={formData.name} required />
            </div>
            <div class="form-group">
                <label for="email">Email</label>
                <input type="email" id="email" bind:value={formData.email} required />
            </div>
            <div class="form-group">
                <label for="message">Message</label>
                <textarea id="message" rows="4" bind:value={formData.message} required></textarea>
            </div>
            <button type="submit" class="btn btn-primary">Send Message</button>
        </form>
    </section>
</section>

<style>
    .home {
        max-width: 800px;
        margin: 0 auto;
        text-align: left;
    }

    /* Hero */
    .hero {
        position: relative;
        padding: 2rem 0 3rem;
        border-bottom: 1px solid rgba(0, 255, 255, 0.2);
        margin-bottom: 3rem;
    }

    .hero-content {
        display: flex;
        align-items: center;
        gap: 2rem;
    }

    .photo-spacer {
        flex-shrink: 0;
        width: 120px;
        height: 120px;
    }

    .hero-text h1 {
        font-size: 2.5rem;
        margin: 0;
        color: #ffffff;
        font-weight: 600;
    }

    .title {
        color: #00ffff;
        font-size: 1.1rem;
        margin: 0.5rem 0;
        font-weight: 500;
    }

    .tagline {
        color: #c0c0c0;
        font-style: italic;
        font-size: 1rem;
        margin: 0.5rem 0 0;
    }

    .dragon {
        position: absolute;
        top: 1rem;
        right: 0;
        width: 140px;
        height: auto;
        color: rgba(0, 255, 255, 0.3);
        transition: color 0.3s ease;
    }

    .dragon:hover {
        color: rgba(0, 255, 255, 0.6);
    }

    /* About */
    .about {
        margin-bottom: 3rem;
    }

    .about h2 {
        color: #00ffff;
        font-size: 1.5rem;
        margin-bottom: 1rem;
        font-weight: 500;
    }

    .about p {
        color: #e0e0e0;
        line-height: 1.8;
        margin-bottom: 1rem;
    }

    .about strong {
        color: #ffffff;
    }

    .about em {
        color: #00ffff;
        font-style: normal;
    }

    /* Highlights */
    .highlights {
        display: flex;
        justify-content: space-around;
        padding: 2rem 0;
        border-top: 1px solid rgba(192, 192, 192, 0.1);
        border-bottom: 1px solid rgba(192, 192, 192, 0.1);
        margin-bottom: 3rem;
    }

    .stat {
        text-align: center;
    }

    .stat .number {
        display: block;
        font-size: 2.5rem;
        font-weight: 700;
        color: #00ffff;
    }

    .stat .label {
        color: #c0c0c0;
        font-size: 0.85rem;
        text-transform: uppercase;
        letter-spacing: 0.1em;
    }

    /* Reading */
    .reading {
        margin-bottom: 3rem;
    }

    .reading h2 {
        color: #00ffff;
        font-size: 1.5rem;
        margin-bottom: 0.5rem;
        font-weight: 500;
    }

    .reading-intro {
        color: #c0c0c0;
        margin-bottom: 1rem;
    }

    .reading-list {
        list-style: none;
        padding: 0;
        margin: 0;
    }

    .reading-list li {
        padding: 1rem;
        background: rgba(0, 255, 255, 0.03);
        border-left: 2px solid #00ffff;
        margin-bottom: 0.5rem;
        transition: background 0.2s ease;
    }

    .reading-list li:hover {
        background: rgba(0, 255, 255, 0.08);
    }

    .book-title {
        display: block;
        color: #ffffff;
        font-weight: 500;
    }

    .book-author {
        color: #808080;
        font-size: 0.9rem;
    }

    /* CTA */
    .cta {
        text-align: center;
        padding: 2rem;
        background: rgba(0, 255, 255, 0.03);
        border-radius: 8px;
        margin-bottom: 3rem;
    }

    .cta p {
        color: #c0c0c0;
        margin-bottom: 1.5rem;
    }

    .btn {
        display: inline-block;
        padding: 0.8rem 2rem;
        border-radius: 4px;
        text-decoration: none;
        font-weight: 500;
        transition: all 0.2s ease;
        cursor: pointer;
        border: none;
        font-size: 1rem;
    }

    .btn-primary {
        background: transparent;
        color: #00ffff;
        border: 1px solid #00ffff;
    }

    .btn-primary:hover {
        background: #00ffff;
        color: #000000;
    }

    /* Contact */
    .contact {
        margin-bottom: 2rem;
    }

    .contact h2 {
        color: #00ffff;
        font-size: 1.5rem;
        margin-bottom: 0.5rem;
        font-weight: 500;
    }

    .contact > p {
        color: #c0c0c0;
        margin-bottom: 1.5rem;
    }

    .contact-methods {
        display: flex;
        gap: 1.5rem;
        margin-bottom: 2rem;
    }

    .contact-link {
        display: flex;
        align-items: center;
        gap: 0.5rem;
        color: #c0c0c0;
        text-decoration: none;
        padding: 0.5rem 1rem;
        border: 1px solid rgba(192, 192, 192, 0.2);
        border-radius: 4px;
        transition: all 0.2s ease;
    }

    .contact-link:hover {
        color: #00ffff;
        border-color: #00ffff;
    }

    .contact-link svg {
        width: 20px;
        height: 20px;
    }

    .contact-form {
        display: flex;
        flex-direction: column;
        gap: 1rem;
    }

    .form-group {
        display: flex;
        flex-direction: column;
        gap: 0.3rem;
    }

    .form-group label {
        color: #c0c0c0;
        font-size: 0.9rem;
    }

    .form-group input,
    .form-group textarea {
        background: #1a1a1a;
        border: 1px solid rgba(192, 192, 192, 0.2);
        border-radius: 4px;
        padding: 0.8rem;
        color: #ffffff;
        font-size: 1rem;
        font-family: inherit;
        transition: border-color 0.2s ease;
    }

    .form-group input:focus,
    .form-group textarea:focus {
        outline: none;
        border-color: #00ffff;
    }

    .form-group textarea {
        resize: vertical;
    }

    .contact-form .btn {
        align-self: flex-start;
        margin-top: 0.5rem;
    }

    /* Responsive */
    @media (max-width: 600px) {
        .hero-content {
            flex-direction: column;
            text-align: center;
        }

        .dragon {
            position: static;
            margin: 1rem auto;
            display: block;
        }

        .highlights {
            flex-direction: column;
            gap: 1.5rem;
        }

        .contact-methods {
            flex-direction: column;
        }
    }
</style>
