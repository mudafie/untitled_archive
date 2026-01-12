---
layout: default
title: untitled_archive
---

<section class="front-matter">

    This is a notebook first. Some pages contradict others. That is allowed here.
        
    Over time, a few notes may harden into positions. If that happens, you'll be able to trace it.
        
    This site is a personal archive and collection of writings by an individual.
    It is not affiliated with any organization.
</section>

<section class="current-status">
        <p><strong>status:</strong> writing in the dark</p>
        <p><strong>listening to:</strong> silence</p>
        <p><strong>thinking about:</strong> whatever</p>
</section>

<section class="random-fragment">
        <p><em id="fragment-text"></em></p>
</section>

<script>
    const fragments = [
        {% for fragment in site.fragments %}
        {{ fragment.text | jsonify }}{% unless forloop.last %},{% endunless %}
        {% endfor %}
    ];
        
    if (fragments.length > 0) {
        const random = fragments[Math.floor(Math.random() * fragments.length)];
        const element = document.getElementById("fragment-text");
        let i = 0;

        // Typing effect
        function typeWriter() {
            if (i < random.length) {
                element.textContent += random.charAt(i);
                i++;
                setTimeout(typeWriter, 50); // 50ms per character - adjust speed here
            }
        }
        typeWriter();
    }
</script>