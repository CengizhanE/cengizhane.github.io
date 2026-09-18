```c
/*
./mite --serve
http://localhost:8000/
*/

global.url           = "https://cengizhan.engineer";
global.title         = "cengizhan.engineer";
global.description   = "An Astronautical Engineering Student @Istanbul Technical University <br><br> Been obsessed with rockets since Falcon Heavy's first launch. Built a 3-meter solid rocket called BUMIN. Still not cured.";
global.favicon_path  = "/asset/favicon.png";


ADD_PROJECT("bitirme projesi", "bir şeyler yaptım", "/proje/bitirme");
ADD_PROJECT("ikinci proje", "açıklama", "/post/ikinci_proje_postu");

ADD_SOCIAL("github", "https://github.com/");
ADD_SOCIAL("linkedin", "https://linkedin.com/");

page->layout = "home";
```


<? sort_pages(&global.posts); ?>

<section class="content">

<h2 class="section-heading">technical logs</h2>

<? for (int i = 0; i < global.posts.count; i++) { ?>
<?     SitePage* p = global.posts.items[i]; ?>
<?     if (strcmp(p->url, "/post/2-gezgin/index.html") == 0) { continue; } ?>
<article>
    <h2><a href="<? STR(p->url) ?>"><? STR(p->title) ?></a></h2>
    <div class="meta"><? STR(p->date) ?></div>
    <p><? STR(p->description) ?></p>
    <div class="post-footer">
        <a href="<? STR(p->url) ?>" class="read-more">Read more...</a>
        <span class="tags"><? STR(p->tags) ?></span>
    </div>
</article>
    <? if (i != global.posts.count - 1) { ?>
        <hr style="margin: 1.5rem; width: 65%; border: 0; border-top: 1px solid #f1f1f1;">
    <? } ?>
<? } ?>

<hr style="margin: 1.5rem; width: 65%; border: 0; border-top: 1px solid #f1f1f1;">

<h2 class="section-heading">startup logs</h2>
<article>
    <h2><a href="/post/2-gezgin/index.html">Gezgin - Nanosatellite Launch from the Stratosphere</a></h2>
    <div class="meta"></div>
    <p>How three 20-year-olds tried to build a rockoon — a balloon-assisted nanosatellite launch system — and what we learned from the attempt.</p>
    <div class="post-footer">
        <a href="/post/2-gezgin/index.html" class="read-more">Read more...</a>
        <span class="tags">Rockoon Architecture, ITU Seed, My First Startup</span>
    </div>
</article>

</section>

