---
layout: post
title:  "INSPIRE 2024 Workshop Recap: Building Data Science Pathways Together"
date:   2023-10-20 10:00:00 -0700
categories: events workshop data-science
---

On October 16, 2024, the INSPIRE Conference brought together grantees from the California Learning Lab's Data Science Grand Challenge for an energizing afternoon of connection, collaboration, and shared learning. Designed as an interactive experience, the workshops gave attendees a chance to reflect on the progress of their projects, co-create curriculum ideas, and engage in rich cross-institutional dialogue around building equitable, effective data science pathways.

<style type="text/css">
.gallery-container {
  max-width: 800px;
  margin: 2em auto;
}

.gallery-nav {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-bottom: 1em;
}

.gallery-nav button {
  background: #2a7ae2;
  color: white;
  border: none;
  padding: 8px 15px;
  border-radius: 4px;
  cursor: pointer;
}

.gallery-nav button:hover {
  background: #1756a9;
}

.gallery-image {
  display: none;
  text-align: center;
}

.gallery-image.active {
  display: block;
}

.gallery-image img {
  max-width: 100%;
  height: auto;
  border-radius: 4px;
}

.gallery-caption {
  margin-top: 10px;
  font-style: italic;
  text-align: center;
}

.dots-container {
  display: flex;
  justify-content: center;
  margin-top: 1em;
}

.dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: #bbb;
  margin: 0 5px;
  cursor: pointer;
}

.dot.active {
  background: #2a7ae2;
}
</style>

<div class="gallery-container">
  <div class="gallery-nav">
    <button id="prev-btn">Previous</button>
    <button id="next-btn">Next</button>
  </div>
  
  <div id="gallery">
    <div class="gallery-image active" data-index="1">
      <img src="/assets/images/inspire-2024/IMG_3801.png" alt="INSPIRE Workshop Image 1">
      <div class="gallery-caption">INSPIRE Workshop 2024 - Group Discussion</div>
    </div>
    
    <div class="gallery-image" data-index="2">
      <img src="/assets/images/inspire-2024/IMG_3802.png" alt="INSPIRE Workshop Image 2">
      <div class="gallery-caption">INSPIRE Workshop 2024 - Presentation Session</div>
    </div>
    
    <div class="gallery-image" data-index="3">
      <img src="/assets/images/inspire-2024/IMG_3804_fixed.png" alt="INSPIRE Workshop Image 3">
      <div class="gallery-caption">INSPIRE Workshop 2024 - Collaboration Activity</div>
    </div>
    
    <div class="gallery-image" data-index="4">
      <img src="/assets/images/inspire-2024/IMG_3806.png" alt="INSPIRE Workshop Image 4">
      <div class="gallery-caption">INSPIRE Workshop 2024 - Team Planning</div>
    </div>
    
    <div class="gallery-image" data-index="5">
      <img src="/assets/images/inspire-2024/IMG_3809.png" alt="INSPIRE Workshop Image 5">
      <div class="gallery-caption">INSPIRE Workshop 2024 - Keynote Presentation</div>
    </div>
  </div>
  
  <div class="dots-container">
    <span class="dot active" data-index="1"></span>
    <span class="dot" data-index="2"></span>
    <span class="dot" data-index="3"></span>
    <span class="dot" data-index="4"></span>
    <span class="dot" data-index="5"></span>
  </div>
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const galleryImages = document.querySelectorAll('.gallery-image');
  const dots = document.querySelectorAll('.dot');
  const prevBtn = document.getElementById('prev-btn');
  const nextBtn = document.getElementById('next-btn');
  
  let currentIndex = 1;
  
  // Initialize first image
  showImage(currentIndex);
  
  // Previous button
  prevBtn.addEventListener('click', function() {
    currentIndex = currentIndex === 1 ? galleryImages.length : currentIndex - 1;
    showImage(currentIndex);
  });
  
  // Next button
  nextBtn.addEventListener('click', function() {
    currentIndex = currentIndex === galleryImages.length ? 1 : currentIndex + 1;
    showImage(currentIndex);
  });
  
  // Dot navigation
  dots.forEach(dot => {
    dot.addEventListener('click', function() {
      const index = parseInt(this.getAttribute('data-index'));
      currentIndex = index;
      showImage(currentIndex);
    });
  });
  
  function showImage(index) {
    // Hide all images
    galleryImages.forEach(image => {
      image.classList.remove('active');
    });
    
    // Remove active class from all dots
    dots.forEach(dot => {
      dot.classList.remove('active');
    });
    
    // Show selected image
    document.querySelector(`.gallery-image[data-index="${index}"]`).classList.add('active');
    
    // Highlight selected dot
    document.querySelector(`.dot[data-index="${index}"]`).classList.add('active');
  }
});
</script>

The event began with a keynote by Ray Levy who serves as the Executive Director for Data Science and AI Academy at North Carolina State University. She kicked off the session by inviting participants to reflect on the evolving landscape of data science education. In an interactive activity, attendees contributed to shaping Data Science Higher Education Knowledge Areas, responding to the following thought-provoking questions:

* Why do we teach these topics in data science (or not)?
* Are they really core and common across the foundational disciplines as we create this new interdisciplinary discipline?
* Do you think of these topics as ones that all data science students should take, topics that students might see in a concentration, or topics that would likely be electives?

Here's the document with participant feedback: [Data Science Higher Education Knowledge Areas](#)

Ray's facilitation provided a national perspective on efforts to standardize data science education and invited feedback on how institutions across California are interpreting and implementing foundational content in diverse ways.

Below are highlights from the other three workshop sessions and reflections shared by participants:

## Session 1: Intro to Data Science – Course Outlines and Common Ground

This session kicked off with a discussion on what's currently being taught in introductory data science courses across community colleges, CSUs, and UCs. Participants broke into institutional segments and engaged in conversations about:

* What topics are commonly covered
* Prerequisites and post-class pathways
* What should be "front loaded" in an intro DS course

> "I thought the collaborative project where we designed a data science course was most valuable. It was informative to see how people think about presentation of the subject and what is important to front load or include."

This session helped highlight both shared foundations and the variety of approaches taken across institutions—sparking ideas for better alignment and innovation.

[Session 1 Notes](#)

## Session 2: Metrics and Evaluation – Harmonizing Impact

In this session, participants shifted focus to evaluation, breaking into themed groups to discuss outcomes through the lenses of:

* Students
* Instruction
* Institutions

Using an Alignment Spreadsheet, groups worked to surface common indicators and challenges across projects. This session emphasized the need for shared language and metrics to tell a collective story about the impact of data science education efforts.

> "The session to review outcomes for students, instructors, and institutions was especially useful."

[Session 2 Notes](#)

## Session 3: Showcase Materials – Sharing What Works

The final workshop was a "show and tell" of instructional materials submitted by projects throughout the year. This open session created space to celebrate creativity, excellence, and collaboration among grantees. Attendees discussed:

* What makes a teaching asset stand out
* Materials they're excited to adapt or adopt
* What else they want to see shared in the future

> "The cohort coordination team did a fantastic job designing engaging activities that made the afternoon interactive."

**Session 3: Materials shared:**
* Skyline Slides - with Flyers
* LACC Slides with Flyers 
* CSUEB Syllabus with Design
* Cal Poly Humboldt: Climate Justice Presentation
* CSU Fullerton: PIPELINE Workshops

## Reflections & Next Steps

One of the most powerful takeaways from the day was the sense of community and collaboration in the room. Whether discussing evaluation frameworks or exchanging ideas on what makes a great intro course, participants valued the opportunity to learn from peers across disciplines and institutions.

> "Being in a room with representatives from so many different institutions, learning about project updates, different disciplines' interpretation etc. was truly energizing."

> "I appreciated Ray's perspective and her sharing the work she's doing on a national level re: standardizing DS education and inviting comment."

The energy and insight shared at INSPIRE reaffirmed Learning Lab's commitment to growing data science pathways together by fostering an inclusive, impactful, and deeply collaborative environment.

We look forward to building on this momentum. If you haven't already, check out the shared assets folder, and stay tuned for more opportunities to connect!

**Resources:**
* [Presentation](#)
* [Ray Levy: Data Science Higher Education Knowledge Areas](#)
* [Session 1 Notes](#)
* [Session 2 Notes](#)
* [Session 3: Materials shared folder](#)
  * Skyline Slides - with Flyers
  * LACC Slides with Flyers 
  * CSUEB Syllabus with Design
  * Cal Poly Humboldt: Climate Justice Presentation
  * CSU Fullerton: PIPELINE Workshops