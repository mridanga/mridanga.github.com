<data>
{
    "id": "lessonIndex",
    "urlPath": "lessons/",
    "urlName": "index"
}
</data>


<js>
this.posts = _.chain(site.pages)
                .filter(function(page) {
                    return page.type === 'lesson';
                })
                .sortBy(function(page) {
                    return parseInt(page.title);
                })
                .toArray()
                .value();
</js>

{{#posts}}
    <hgroup>
        <a href="/{{urlFull}}">
            <h2>{{title}}</h2>
        </a>
    </hgroup>
    {{#synopsis}}
        <p>{{synopsis}} <a href="{{urlFull}}">Read More.</a></p>
    {{/synopsis}}
{{/posts}}
