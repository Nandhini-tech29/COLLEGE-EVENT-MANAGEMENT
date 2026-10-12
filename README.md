<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>CampusConnect | College Events</title>

<style>
:root {
    --primary: #4f46e5;
    --primary-dark: #3730a3;
    --background: #f6f7fb;
    --white: #ffffff;
    --text: #1e293b;
    --muted: #64748b;
    --border: #e5e7eb;
    --success: #15803d;
}

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, Helvetica, sans-serif;
    background: var(--background);
    color: var(--text);
    line-height: 1.6;
}

button, input, select {
    font: inherit;
}

button {
    cursor: pointer;
}

header {
    background: var(--white);
    border-bottom: 1px solid var(--border);
    position: sticky;
    top: 0;
    z-index: 100;
}

.navbar {
    max-width: 1250px;
    margin: auto;
    padding: 16px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 24px;
}

.logo {
    font-size: 24px;
    font-weight: 800;
    color: var(--primary);
    white-space: nowrap;
}

.logo span {
    color: var(--text);
}

.nav-links {
    display: flex;
    gap: 10px;
    list-style: none;
}

.nav-links button {
    border: none;
    background: transparent;
    padding: 10px 14px;
    color: var(--muted);
    border-radius: 8px;
    font-weight: 600;
}

.nav-links button:hover,
.nav-links button.active {
    color: var(--primary);
    background: #eef2ff;
}

.profile-button {
    background: var(--primary);
    color: white;
    padding: 10px 16px;
    border: none;
    border-radius: 8px;
    font-weight: 600;
}

main {
    max-width: 1250px;
    margin: auto;
    padding: 32px 24px 60px;
}

.page {
    display: none;
}

.page.active {
    display: block;
}

.hero {
    background: linear-gradient(120deg, #3730a3, #6366f1);
    color: white;
    border-radius: 20px;
    padding: 48px;
    display: grid;
    grid-template-columns: 1.4fr 1fr;
    align-items: center;
    gap: 30px;
    margin-bottom: 36px;
    overflow: hidden;
}

.hero-label {
    display: inline-block;
    background: rgba(255,255,255,0.15);
    padding: 7px 13px;
    border-radius: 30px;
    margin-bottom: 16px;
    font-size: 13px;
}

.hero h1 {
    font-size: clamp(30px, 4vw, 46px);
    line-height: 1.2;
    margin-bottom: 16px;
}

.hero p {
    color: #e0e7ff;
    max-width: 540px;
    margin-bottom: 24px;
}

.hero-button {
    background: white;
    color: var(--primary-dark);
    border: none;
    padding: 13px 20px;
    border-radius: 9px;
    font-weight: 700;
}

.hero-art {
    text-align: center;
    font-size: 110px;
    background: rgba(255,255,255,0.1);
    padding: 28px;
    border-radius: 20px;
}

.stats {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 18px;
    margin-bottom: 40px;
}

.stat-card {
    background: white;
    border: 1px solid var(--border);
    padding: 22px;
    border-radius: 14px;
}

.stat-card p {
    color: var(--muted);
    font-size: 14px;
}

.stat-card h2 {
    font-size: 30px;
    margin-top: 5px;
}

.section-heading {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 15px;
    margin-bottom: 22px;
}

.section-heading h2 {
    font-size: 25px;
}

.text-button {
    color: var(--primary);
    border: none;
    background: transparent;
    font-weight: 700;
}

.toolbar {
    display: flex;
    gap: 12px;
    margin-bottom: 26px;
    flex-wrap: wrap;
}

.search-box {
    flex: 1;
    min-width: 220px;
}

.search-box input,
.toolbar select,
.form-group input,
.form-group select {
    width: 100%;
    padding: 12px 14px;
    border: 1px solid #d1d5db;
    border-radius: 9px;
    background: white;
    outline: none;
}

.search-box input:focus,
.form-group input:focus,
.form-group select:focus {
    border-color: var(--primary);
}

.toolbar select {
    width: 200px;
}

.event-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 22px;
}

.event-card {
    background: white;
    border: 1px solid var(--border);
    border-radius: 15px;
    overflow: hidden;
    transition: transform 0.2s, box-shadow 0.2s;
}

.event-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 12px 28px rgba(15, 23, 42, 0.08);
}

.event-cover {
    min-height: 155px;
    padding: 20px;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    color: white;
}

.cover-tech {
    background: linear-gradient(135deg, #312e81, #818cf8);
}

.cover-culture {
    background: linear-gradient(135deg, #9d174d, #fb7185);
}

.cover-sports {
    background: linear-gradient(135deg, #065f46, #34d399);
}

.cover-workshop {
    background: linear-gradient(135deg, #9a3412, #fb923c);
}

.cover-entrepreneurship {
    background: linear-gradient(135deg, #164e63, #22d3ee);
}

.cover-arts {
    background: linear-gradient(135deg, #581c87, #c084fc);
}

.event-emoji {
    font-size: 48px;
    align-self: center;
}

.category-badge {
    background: rgba(255,255,255,0.2);
    padding: 5px 10px;
    border-radius: 30px;
    font-size: 12px;
    font-weight: 700;
}

.event-body {
    padding: 20px;
}

.event-body h3 {
    font-size: 19px;
    margin-bottom: 10px;
}

.event-description {
    color: var(--muted);
    font-size: 14px;
    margin-bottom: 18px;
    min-height: 44px;
}

.event-detail {
    color: #475569;
    font-size: 13px;
    margin-bottom: 8px;
}

.event-footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
    margin-top: 18px;
}

.seats {
    color: var(--muted);
    font-size: 12px;
}

.primary-button {
    background: var(--primary);
    color: white;
    border: none;
    border-radius: 8px;
    padding: 11px 16px;
    font-weight: 700;
}

.primary-button:hover {
    background: var(--primary-dark);
}

.primary-button:disabled {
    background: #9ca3af;
    cursor: not-allowed;
}

.secondary-button {
    background: white;
    color: var(--text);
    border: 1px solid var(--border);
    padding: 10px 15px;
    border-radius: 8px;
}

.empty-state {
    text-align: center;
    padding: 55px 20px;
    background: white;
    border-radius: 14px;
    border: 1px solid var(--border);
}

.empty-state h3 {
    margin-bottom: 10px;
}

.empty-state p {
    color: var(--muted);
    margin-bottom: 18px;
}

.registration-card {
    background: white;
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px;
    margin-bottom: 15px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
}

.registration-card p {
    color: var(--muted);
    font-size: 14px;
}

.status-badge {
    display: inline-block;
    color: var(--success);
    background: #dcfce7;
    padding: 5px 10px;
    border-radius: 30px;
    font-size: 12px;
    font-weight: 700;
    margin-top: 8px;
}

.danger-button {
    border: 1px solid #fecaca;
    color: #b91c1c;
    background: #fff;
    padding: 9px 12px;
    border-radius: 8px;
}

.profile-panel {
    max-width: 600px;
    background: white;
    padding: 28px;
    border: 1px solid var(--border);
    border-radius: 15px;
}

.profile-panel h2 {
    margin-bottom: 8px;
}

.profile-panel > p {
    color: var(--muted);
    margin-bottom: 24px;
}

.form-group {
    margin-bottom: 18px;
}

.form-group label {
    display: block;
    margin-bottom: 7px;
    font-weight: 600;
    font-size: 14px;
}

.form-group input[readonly] {
    background: #f3f4f6;
}

footer {
    background: white;
    border-top: 1px solid var(--border);
    padding: 25px;
    text-align: center;
    color: var(--muted);
    font-size: 13px;
}

/* Registration modal */

.modal {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(15, 23, 42, 0.6);
    z-index: 200;
    padding: 20px;
    align-items: center;
    justify-content: center;
    overflow-y: auto;
}

.modal.show {
    display: flex;
}

.modal-content {
    width: 100%;
    max-width: 480px;
    background: white;
    border-radius: 16px;
    padding: 28px;
    margin: auto;
}

.modal-header {
    display: flex;
    justify-content: space-between;
    gap: 15px;
    margin-bottom: 8px;
}

.close-button {
    border: none;
    background: transparent;
    font-size: 26px;
    color: var(--muted);
    align-self: flex-start;
}

.modal-description {
    color: var(--muted);
    margin-bottom: 22px;
    font-size: 14px;
}

.form-actions {
    display: flex;
    gap: 10px;
    margin-top: 24px;
}

.form-actions button {
    flex: 1;
}

.toast {
    display: none;
    position: fixed;
    bottom: 25px;
    right: 25px;
    background: #166534;
    color: white;
    padding: 15px 22px;
    border-radius: 10px;
    z-index: 300;
    box-shadow: 0 8px 20px rgba(0,0,0,0.15);
    max-width: calc(100% - 40px);
}

.toast.show {
    display: block;
    animation: fadeIn 0.3s ease;
}

@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(8px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

@media (max-width: 950px) {
    .event-grid {
        grid-template-columns: repeat(2, minmax(0, 1fr));
    }

    .hero {
        padding: 32px;
    }
}

@media (max-width: 650px) {
    .navbar {
        flex-wrap: wrap;
        padding: 14px 16px;
    }

    .nav-links {
        order: 3;
        width: 100%;
        overflow-x: auto;
        justify-content: flex-start;
    }

    .nav-links button {
        white-space: nowrap;
    }

    .logo {
        font-size: 21px;
    }

    main {
        padding: 22px 16px 40px;
    }

    .hero {
        grid-template-columns: 1fr;
        padding: 27px;
    }

    .hero-art {
        display: none;
    }

    .stats {
        grid-template-columns: 1fr;
        gap: 12px;
    }

    .event-grid {
        grid-template-columns: 1fr;
    }

    .toolbar select {
        width: 100%;
    }

    .registration-card {
        align-items: flex-start;
        flex-direction: column;
    }

    .section-heading {
        align-items: flex-start;
    }
}
</style>
</head>

<body>

<header>
    <nav class="navbar">

        <div class="logo">Campus<span>Connect</span></div>

        <ul class="nav-links">
            <li>
                <button class="active" data-page="home">Home</button>
            </li>
            <li>
                <button data-page="events">Events</button>
            </li>
            <li>
                <button data-page="registrations">My Registration</button>
            </li>
            <li>
                <button data-page="profile">Profile</button>
            </li>
        </ul>

        <button class="profile-button" id="navProfile">
            My Profile
        </button>

    </nav>
</header>

<main>

    <!-- HOME PAGE -->

    <section id="home" class="page active">

        <div class="hero">

            <div>
                <span class="hero-label">YOUR CAMPUS, YOUR COMMUNITY</span>

                <h1>Discover events.<br>Make memories.</h1>

                <p>
                    Explore technical symposiums, cultural fests,
                    workshops, sports and more. Find your next
                    campus experience and register in minutes.
                </p>

                <button class="hero-button" id="exploreEvents">
                    Explore Events →
                </button>
            </div>

            <div class="hero-art" aria-hidden="true">
                🎓
            </div>

        </div>

        <div class="stats">

            <div class="stat-card">
                <p>Upcoming Events</p>
                <h2 id="eventCount">0</h2>
            </div>

            <div class="stat-card">
                <p>My Registrations</p>
                <h2 id="registrationCount">0</h2>
            </div>

            <div class="stat-card">
                <p>Event Categories</p>
                <h2 id="categoryCount">0</h2>
            </div>

        </div>

        <div class="section-heading">
            <h2>Upcoming Events</h2>

            <button class="text-button" id="viewAllEvents">
                View all events →
            </button>
        </div>

        <div class="event-grid" id="featuredEvents"></div>

    </section>


    <!-- EVENTS PAGE -->

    <section id="events" class="page">

        <div class="section-heading">
            <div>
                <h2>College Events</h2>
                <p style="color:#64748b">
                    Find an event that matches your interests.
                </p>
            </div>
        </div>

        <div class="toolbar">

            <div class="search-box">
                <input
                    type="search"
                    id="searchInput"
                    placeholder="Search for events..."
                    aria-label="Search events"
                >
            </div>

            <select id="categoryFilter" aria-label="Filter by category">
                <option value="All">All Categories</option>
                <option value="Technical">Technical</option>
                <option value="Cultural">Cultural</option>
                <option value="Sports">Sports</option>
                <option value="Workshop">Workshop</option>
                <option value="Entrepreneurship">Entrepreneurship</option>
                <option value="Arts">Arts</option>
            </select>

            <select id="sortFilter" aria-label="Sort events">
                <option value="date">Sort by Date</option>
                <option value="name">Sort by Name</option>
            </select>

        </div>

        <div class="event-grid" id="allEvents"></div>

    </section>


    <!-- MY REGISTRATIONS PAGE -->

    <section id="registrations" class="page">

        <div class="section-heading">
            <div>
                <h2>My Registrations</h2>
                <p style="color:#64748b">
                    Keep track of the events you've registered for.
                </p>
            </div>
        </div>

        <div id="registrationList"></div>

    </section>


    <!-- PROFILE PAGE -->

    <section id="profile" class="page">

        <div class="profile-panel">

            <h2>My Profile</h2>

            <p>
                Enter your details to use them when registering
                for college events.
            </p>

            <form id="profileForm">

                <div class="form-group">
                    <label for="studentName">Full Name</label>
                    <input
                        type="text"
                        id="studentName"
                        placeholder="Enter your name"
                        required
                    >
                </div>

                <div class="form-group">
                    <label for="studentEmail">College Email</label>
                    <input
                        type="email"
                        id="studentEmail"
                        placeholder="Enter your email"
                        required
                    >
                </div>

                <div class="form-group">
                    <label for="studentId">Student ID</label>
                    <input
                        type="text"
                        id="studentId"
                        placeholder="Enter your student ID"
                        required
                    >
                </div>

                <div class="form-group">
                    <label for="studentDepartment">Department</label>

                    <select id="studentDepartment" required>
                        <option value="">Select department</option>
                        <option value="CSE">Computer Science</option>
                        <option value="CSBS">Computer Science and Business Systems</option>
                        <option value="IT">Information Technology</option>
                        <option value="ECE">Electronics and Communication</option>
                        <option value="EEE">Electrical and Electronics</option>
                        <option value="MECH">Mechanical Engineering</option>
                        <option value="CIVIL">Civil Engineering</option>
                        <option value="OTHER">Other</option>
                    </select>
                </div>

                <button type="submit" class="primary-button">
                    Save Profile
                </button>

            </form>

        </div>

    </section>

</main>


<footer>
    <p>CampusConnect — Your college life, all in one place.</p>
    <p style="margin-top:5px">
        Student Event Portal | College Management Project
    </p>
</footer>


<!-- REGISTRATION MODAL -->

<div
    class="modal"
    id="registrationModal"
    role="dialog"
    aria-modal="true"
    aria-labelledby="modalTitle"
>

    <div class="modal-content">

        <div class="modal-header">
            <h2 id="modalTitle">Register for Event</h2>

            <button
                class="close-button"
                id="closeModal"
                aria-label="Close registration form"
            >
                &times;
            </button>
        </div>

        <p class="modal-description" id="modalEventInfo">
            Enter your details to register.
        </p>

        <form id="registrationForm">

            <input type="hidden" id="selectedEventId">

            <div class="form-group">
                <label for="regName">Full Name</label>
                <input type="text" id="regName" required>
            </div>

            <div class="form-group">
                <label for="regEmail">Email Address</label>
                <input type="email" id="regEmail" required>
            </div>

            <div class="form-group">
                <label for="regStudentId">Student ID</label>
                <input type="text" id="regStudentId" required>
            </div>

            <div class="form-group">
                <label for="regDepartment">Department</label>
                <select id="regDepartment" required>
                    <option value="">Select department</option>
                    <option value="CSE">Computer Science</option>
                    <option value="CSBS">Computer Science and Business Systems</option>
                    <option value="IT">Information Technology</option>
                    <option value="ECE">Electronics and Communication</option>
                    <option value="EEE">Electrical and Electronics</option>
                    <option value="MECH">Mechanical Engineering</option>
                    <option value="CIVIL">Civil Engineering</option>
                    <option value="OTHER">Other</option>
                </select>
            </div>

            <div class="form-actions">

                <button type="button" class="secondary-button" id="cancelModal">
                    Cancel
                </button>

                <button type="submit" class="primary-button">
                    Confirm Registration
                </button>

            </div>

        </form>

    </div>

</div>


<div class="toast" id="toast" role="status" aria-live="polite"></div>


<script>

/* ===================================
   EVENT DATA
=================================== */

// Sample events based on your wireframe.
// Replace these with your actual college events.

const events = [
    {
        id: 1,
        name: "Technical Symposium",
        category: "Technical",
        date: "2026-10-12",
        time: "10:00 AM",
        venue: "Main Block",
        description: "Showcase your technical skills and participate in exciting competitions.",
        icon: "💻",
        cover: "cover-tech",
        seats: 100
    },

    {
        id: 2,
        name: "Cultural Fest",
        category: "Cultural",
        date: "2026-10-18",
        time: "5:00 PM",
        venue: "Open Air Theatre",
        description: "Celebrate music, dance, art and the spirit of campus life.",
        icon: "🎭",
        cover: "cover-culture",
        seats: 250
    },

    {
        id: 3,
        name: "Intercollege Sports Meet",
        category: "Sports",
        date: "2026-10-24",
        time: "8:00 AM",
        venue: "College Sports Ground",
        description: "Compete with fellow students in exciting sporting events.",
        icon: "🏆",
        cover: "cover-sports",
        seats: 150
    },

    {
        id: 4,
        name: "Web Development Workshop",
        category: "Workshop",
        date: "2026-11-02",
        time: "9:30 AM",
        venue: "Computer Lab 2",
        description: "Learn the fundamentals of building modern websites.",
        icon: "🌐",
        cover: "cover-workshop",
        seats: 60
    },

    {
        id: 5,
        name: "Startup and Innovation Summit",
        category: "Entrepreneurship",
        date: "2026-11-10",
        time: "10:30 AM",
        venue: "Seminar Hall",
        description: "Explore startup ideas, innovation and entrepreneurship.",
        icon: "🚀",
        cover: "cover-entrepreneurship",
        seats: 120
    },

    {
        id: 6,
        name: "Photography and Arts Exhibition",
        category: "Arts",
        date: "2026-11-18",
        time: "2:00 PM",
        venue: "Library Auditorium",
        description: "Discover student creativity through photography and art.",
        icon: "🎨",
        cover: "cover-arts",
        seats: 80
    }
];


/* ===================================
   LOCAL STORAGE
=================================== */

function loadStorage(key, fallback) {
    try {
        const value = localStorage.getItem(key);
        return value ? JSON.parse(value) : fallback;
    } catch (error) {
        return fallback;
    }
}

function saveStorage(key, value) {
    localStorage.setItem(key, JSON.stringify(value));
}

let registrations = loadStorage("campusRegistrations", []);
let profile = loadStorage("campusProfile", {});


/* ===================================
   HELPER FUNCTIONS
=================================== */

function formatDate(dateString) {
    const date = new Date(dateString + "T00:00:00");

    return date.toLocaleDateString("en-IN", {
        day: "numeric",
        month: "short",
        year: "numeric"
    });
}

function getEvent(id) {
    return events.find(event => event.id === Number(id));
}

function isPast(event) {
    const eventDate = new Date(event.date + "T23:59:59");
    return eventDate < new Date();
}

function getRemainingSeats(event) {
    const count = registrations.filter(
        registration => registration.eventId === event.id
    ).length;

    return Math.max(0, event.seats - count);
}

function isRegistered(eventId) {
    return registrations.some(
        registration => registration.eventId === Number(eventId)
    );
}

function showToast(message) {
    const toast = document.getElementById("toast");

    toast.textContent = message;
    toast.classList.add("show");

    clearTimeout(showToast.timeout);

    showToast.timeout = setTimeout(() => {
        toast.classList.remove("show");
    }, 3000);
}


/* ===================================
   EVENT CARD
=================================== */

function createEventCard(event) {
    const registered = isRegistered(event.id);
    const past = isPast(event);
    const remaining = getRemainingSeats(event);

    let buttonText = "Register Now";
    let disabled = false;

    if (registered) {
        buttonText = "Registered";
        disabled = true;
    } else if (past) {
        buttonText = "Event Ended";
        disabled = true;
    } else if (remaining === 0) {
        buttonText = "Fully Booked";
        disabled = true;
    }

    return `
        <article class="event-card">

            <div class="event-cover ${event.cover}">

                <span class="category-badge">
                    ${event.category}
                </span>

                <span class="event-emoji" aria-hidden="true">
                    ${event.icon}
                </span>

            </div>

            <div class="event-body">

                <h3>${event.name}</h3>

                <p class="event-description">
                    ${event.description}
                </p>

                <p class="event-detail">
                    📅 ${formatDate(event.date)}
                </p>

                <p class="event-detail">
                    🕒 ${event.time}
                </p>

                <p class="event-detail">
                    📍 ${event.venue}
                </p>

                <div class="event-footer">

                    <span class="seats">
                        ${remaining} seats left
                    </span>

                    <button
                        class="primary-button"
                        data-register="${event.id}"
                        ${disabled ? "disabled" : ""}
                    >
                        ${buttonText}
                    </button>

                </div>

            </div>

        </article>
    `;
}


/* ===================================
   RENDER EVENTS
=================================== */

function renderEvents() {

    // Featured events on the home page.
    const upcomingEvents = events
        .filter(event => !isPast(event))
        .sort((a, b) => a.date.localeCompare(b.date));

    document.getElementById("featuredEvents").innerHTML =
        upcomingEvents.length
            ? upcomingEvents.slice(0, 3).map(createEventCard).join("")
            : `<div class="empty-state">
                   <h3>No upcoming events</h3>
                   <p>Check back later for new college events.</p>
               </div>`;

    // Search and filter on the Events page.
    const search = document
        .getElementById("searchInput")
        .value.trim().toLowerCase();

    const category = document
        .getElementById("categoryFilter")
        .value;

    const sort = document
        .getElementById("sortFilter")
        .value;

    let filteredEvents = upcomingEvents.filter(event => {

        const matchesSearch =
            event.name.toLowerCase().includes(search) ||
            event.category.toLowerCase().includes(search) ||
            event.venue.toLowerCase().includes(search);

        const matchesCategory =
            category === "All" || event.category === category;

        return matchesSearch && matchesCategory;
    });

    if (sort === "name") {
        filteredEvents.sort((a, b) => a.name.localeCompare(b.name));
    }

    document.getElementById("allEvents").innerHTML =
        filteredEvents.length
            ? filteredEvents.map(createEventCard).join("")
            : `<div class="empty-state">
                   <h3>No events found</h3>
                   <p>Try another search or select a different category.</p>
               </div>`;

    // Dashboard statistics.
    document.getElementById("eventCount").textContent =
        upcomingEvents.length;

    document.getElementById("registrationCount").textContent =
        registrations.length;

    document.getElementById("categoryCount").textContent =
        new Set(upcomingEvents.map(event => event.category)).size;
}


/* ===================================
   PAGE NAVIGATION
=================================== */

function showPage(pageId) {

    document.querySelectorAll(".page").forEach(page => {
        page.classList.remove("active");
    });

    document.getElementById(pageId).classList.add("active");

    document.querySelectorAll("[data-page]").forEach(button => {
        button.classList.toggle(
            "active",
            button.dataset.page === pageId
        );
    });

    if (pageId === "registrations") {
        renderRegistrations();
    }

    if (pageId === "profile") {
        fillProfile();
    }

    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });
}

document.querySelectorAll("[data-page]").forEach(button => {
    button.addEventListener("click", () => {
        showPage(button.dataset.page);
    });
});

document.getElementById("navProfile").addEventListener("click", () => {
    showPage("profile");
});

document.getElementById("exploreEvents").addEventListener("click", () => {
    showPage("events");
});

document.getElementById("viewAllEvents").addEventListener("click", () => {
    showPage("events");
});


/* ===================================
   SEARCH AND FILTER
=================================== */

document.getElementById("searchInput").addEventListener(
    "input",
    renderEvents
);

document.getElementById("categoryFilter").addEventListener(
    "change",
    renderEvents
);

document.getElementById("sortFilter").addEventListener(
    "change",
    renderEvents
);


/* ===================================
   OPEN REGISTRATION FORM
=================================== */

const modal = document.getElementById("registrationModal");

function openRegistration(eventId) {

    const event = getEvent(eventId);

    if (!event) {
        return;
    }

    if (isPast(event)) {
        showToast("This event has already ended.");
        return;
    }

    if (isRegistered(event.id)) {
        showToast("You have already registered for this event.");
        return;
    }

    if (getRemainingSeats(event) <= 0) {
        showToast("Sorry, this event is fully booked.");
        return;
    }

    document.getElementById("selectedEventId").value = event.id;

    document.getElementById("modalTitle").textContent =
        "Register for " + event.name;

    document.getElementById("modalEventInfo").textContent =
        `${formatDate(event.date)} · ${event.time} · ${event.venue}`;

    fillRegistrationForm();

    modal.classList.add("show");

    document.getElementById("regName").focus();
}

function closeRegistration() {
    modal.classList.remove("show");
}

document.getElementById("closeModal").addEventListener(
    "click",
    closeRegistration
);

document.getElementById("cancelModal").addEventListener(
    "click",
    closeRegistration
);

modal.addEventListener("click", event => {
    if (event.target === modal) {
        closeRegistration();
    }
});

document.addEventListener("keydown", event => {
    if (event.key === "Escape") {
        closeRegistration();
    }
});

// Event delegation makes buttons work after rendering.
document.addEventListener("click", event => {

    const button = event.target.closest("[data-register]");

    if (button && !button.disabled) {
        openRegistration(button.dataset.register);
    }
});


/* ===================================
   PROFILE
=================================== */

function fillProfile() {

    document.getElementById("studentName").value =
        profile.name || "";

    document.getElementById("studentEmail").value =
        profile.email || "";

    document.getElementById("studentId").value =
        profile.studentId || "";

    document.getElementById("studentDepartment").value =
        profile.department || "";
}

function fillRegistrationForm() {

    document.getElementById("regName").value =
        profile.name || "";

    document.getElementById("regEmail").value =
        profile.email || "";

    document.getElementById("regStudentId").value =
        profile.studentId || "";

    document.getElementById("regDepartment").value =
        profile.department || "";
}

document.getElementById("profileForm").addEventListener(
    "submit",
    event => {

        event.preventDefault();

        profile = {
            name: document.getElementById("studentName").value.trim(),
            email: document.getElementById("studentEmail").value.trim(),
            studentId: document.getElementById("studentId").value.trim(),
            department: document.getElementById("studentDepartment").value
        };

        saveStorage("campusProfile", profile);

        showToast("Profile saved successfully.");
    }
);


/* ===================================
   CONFIRM REGISTRATION
=================================== */

document.getElementById("registrationForm").addEventListener(
    "submit",
    event => {

        event.preventDefault();

        const eventId = Number(
            document.getElementById("selectedEventId").value
        );

        const selectedEvent = getEvent(eventId);

        if (!selectedEvent) {
            showToast("Event not found.");
            return;
        }

        if (isPast(selectedEvent)) {
            showToast("Registration is closed for this event.");
            closeRegistration();
            renderEvents();
            return;
        }

        if (isRegistered(eventId)) {
            showToast("You are already registered.");
            closeRegistration();
            return;
        }

        if (getRemainingSeats(selectedEvent) <= 0) {
            showToast("Sorry, this event is fully booked.");
            closeRegistration();
            renderEvents();
            return;
        }

        const registration = {
            registrationId: Date.now(),
            eventId: eventId,
            name: document.getElementById("regName").value.trim(),
            email: document.getElementById("regEmail").value.trim(),
            studentId: document.getElementById("regStudentId").value.trim(),
            department: document.getElementById("regDepartment").value,
            registeredAt: new Date().toISOString()
        };

        registrations.push(registration);

        saveStorage("campusRegistrations", registrations);

        // Keep the profile available for future registrations.
        profile = {
            name: registration.name,
            email: registration.email,
            studentId: registration.studentId,
            department: registration.department
        };

        saveStorage("campusProfile", profile);

        closeRegistration();

        document.getElementById("registrationForm").reset();

        renderEvents();

        renderRegistrations();

        showPage("registrations");

        showToast("Registration completed successfully.");
    }
);


/* ===================================
   MY REGISTRATIONS
=================================== */

function renderRegistrations() {

    const container = document.getElementById("registrationList");

    document.getElementById("registrationCount").textContent =
        registrations.length;

    if (registrations.length === 0) {

        container.innerHTML = `
            <div class="empty-state">

                <h3>No registrations yet</h3>

                <p>
                    Explore upcoming college events and register
                    for the ones you like.
                </p>

                <button class="primary-button" id="browseEvents">
                    Browse Events
                </button>

            </div>
        `;

        document.getElementById("browseEvents").addEventListener(
            "click",
            () => showPage("events")
        );

        return;
    }

    container.innerHTML = registrations.map(registration => {

        const event = getEvent(registration.eventId);

        if (!event) {
            return "";
        }

        const eventEnded = isPast(event);

        return `
            <div class="registration-card">

                <div>

                    <h3>${event.name}</h3>

                    <p>📅 ${formatDate(event.date)} · ${event.time}</p>

                    <p>📍 ${event.venue}</p>

                    <p>Registration ID: ${registration.registrationId}</p>

                    <p>Registered as: ${registration.name}</p>

                    <span class="status-badge">
                        ${eventEnded ? "Event Ended" : "Registered"}
                    </span>

                </div>

                <button
                    class="danger-button"
                    data-cancel="${registration.registrationId}"
                >
                    Cancel Registration
                </button>

            </div>
        `;

    }).join("");
}


// Cancel a registration.
document.addEventListener("click", event => {

    const button = event.target.closest("[data-cancel]");

    if (!button) {
        return;
    }

    const registrationId = Number(button.dataset.cancel);

    const confirmed = window.confirm(
        "Are you sure you want to cancel this registration?"
    );

    if (!confirmed) {
        return;
    }

    registrations = registrations.filter(
        registration =>
            registration.registrationId !== registrationId
    );

    saveStorage("campusRegistrations", registrations);

    renderRegistrations();
    renderEvents();

    showToast("Registration cancelled.");
});


/* ===================================
   INITIALIZE WEBSITE
=================================== */

renderEvents();
renderRegistrations();
fillProfile();

</script>

</body>
</html>
