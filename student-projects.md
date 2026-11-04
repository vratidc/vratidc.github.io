---
title: Student Projects
excerpt: Projects from all IMXD Lab course showcases
permalink: /student-projects
layout: projectspage
---

<div class="publications">
    <h1 id="page-title" class="page__title">Student Projects</h1>
</div>

<p>Projects from all the course showcases. Select a project to see it in its showcase.</p>

<div class="button-group filter-button-group">
    <a class="filter-button filter-button-active" data-filter="*">All</a>
    <a class="filter-button" data-filter=".AR">AR</a>
    <a class="filter-button" data-filter=".MR">MR</a>
    <a class="filter-button" data-filter=".VR">VR</a>
    <a class="filter-button" data-filter=".VR-Film">VR Film</a>
</div>

<hr style="height:2px;border-width:0;background-color:#008055;">

<div class="all-projects student-projects">
    {% include documents-collection-projects-students.html collection="projects" %}
</div>

<script>
    // Same Isotope filter transition as All Projects on the Projects page.
    var $grid = $('.student-projects').isotope({
        itemSelector: '.project_grid__item',
        percentPosition: true,
        layoutMode: 'fitRows',
        fitRows: {
            gutter: 10
        }
    });
    // Titles can wrap differently once fonts load, so settle the layout again.
    $(window).on('load', function () {
        $grid.isotope('layout');
    });
    $('.filter-button-group').on('click', 'a', function() {
        $grid.isotope({
            filter: $(this).attr('data-filter')
        });
        $('.filter-button-group a').removeClass('filter-button-active');
        $(this).addClass('filter-button-active');
    });
</script>
