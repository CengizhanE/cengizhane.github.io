```c
/*
./mite --serve
http://localhost:8000/
*/

global.url   = "https://cengizhan.engineer";
global.title = "cengizhan.engineer";
global.description  = "İstikbal göklerdedir";


ADD_PROJECT("bitirme projesi", "bir şeyler yaptım", "/proje/bitirme");
ADD_PROJECT("ikinci proje", "açıklama", "/post/ikinci_proje_postu");

ADD_SOCIAL("github", "https://github.com/Recepefee");
ADD_SOCIAL("linkedin", "https://linkedin.com/recepefe");

page->layout = "home";
```

<? sort_pages(&global.posts); ?>

<section class="content">

<? for (int i = 0; i < global.posts.count; i++) { ?>
<?     SitePage* p = global.posts.items[i]; ?>
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

</section>


