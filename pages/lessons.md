<data>
{
    "urlPath": ""
}
</data>


<js>
this.posts = _.chain(site.posts)
                .sortBy(site.posts, function(i) { return -dateValue(i.date); })
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
