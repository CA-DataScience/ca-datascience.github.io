---
layout: page
title: Data Science Resource Page
permalink: /data-science/
---

<div class="view-toggle">
  <button id="student-view-btn" class="active">Student View</button>
  <button id="educator-view-btn">Educator View</button>
</div>

<div id="student-view" class="content-view">
  <h1>What is Data Science?</h1>

  <p>Data science is the study of data to extract meaningful insights for business. It combines statistics, programming, and domain knowledge to analyze large amounts of data.</p>

<h2>Core Components:</h2>
  <ul>
    <li>Statistics and probability</li>
    <li>Programming skills</li>
    <li>Machine learning</li>
    <li>Data visualization</li>
    <li>Domain expertise</li>
  </ul>

<h2>Career Paths:</h2>
  <p>Data science skills can lead to careers as a data scientist, data analyst, machine learning engineer, or data engineer.</p>
</div>

<div id="educator-view" class="content-view" style="display: none;">
  <h1>Teaching Data Science</h1>

  <p>This guide provides resources for introducing data science concepts to students at various educational levels.</p>

<h2>Learning Objectives:</h2>
  <ul>
    <li>Understand multidisciplinary nature of data science</li>
    <li>Develop fundamental technical skills</li>
    <li>Apply data science to real-world problems</li>
    <li>Consider ethical implications of data analysis</li>
  </ul>

<h2>Teaching Approaches:</h2>
  <p>Use real-world examples, hands-on projects, and scaffolded programming exercises to engage students with data science concepts.</p>
</div>

<script>
  document.getElementById('student-view-btn').addEventListener('click', function() {
    document.getElementById('student-view').style.display = 'block';
    document.getElementById('educator-view').style.display = 'none';
    this.classList.add('active');
    document.getElementById('educator-view-btn').classList.remove('active');
  });
  
  document.getElementById('educator-view-btn').addEventListener('click', function() {
    document.getElementById('student-view').style.display = 'none';
    document.getElementById('educator-view').style.display = 'block';
    this.classList.add('active');
    document.getElementById('student-view-btn').classList.remove('active');
  });
  
  // Check for view parameter in URL
  const urlParams = new URLSearchParams(window.location.search);
  if (urlParams.get('view') === 'educator') {
    document.getElementById('educator-view-btn').click();
  }
</script>