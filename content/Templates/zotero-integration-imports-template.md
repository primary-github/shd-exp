---
authors: "{{authors}}"
zot-link: {{select}}
type: {{itemType}}
bibliography-cite: "{{bibliography}}"
cite: {{citationKey}}
zot-folder: {{collections[0].name}}
tags: [literature-note]
---
{% persist "notes" %}

- [ ] Processed from last import?
Add tags to YAML using [[tag taxonomy]]

> [!example]- Note steps
> - This note should be created using the Citations plugin which links with Zotero to pull in its meta and bibliographic information.
> - If you're making a literature note in obsidian, it's because you've already annotated and read it or you're just about to.
> - Import the annotations you make from Zotero into this literature note.
> - Ensure that all imported annotations have fixed typos and do some minor formatting and sectioning out if necessary.
> - Once in the literature note, use the annotations to create [[tag-taxonomy#^ff04bd|an idea notes]]. Link back in the idea note to this literature note. 
> - Check [[tag-taxonomy|tag-taxonomy]] to see if this could have any topic tags. Give preference to existing tags over creation of new ones.
> - Once complete, click the checkbox above.

# Notes from last import: {{importDate | format("YYYY-MM-DD h:mm a")}}

{% endpersist %}
{% persist "annotations" %}
{%- set newAnnotations = annotations | filterby("date", "dateafter", lastImportDate) %}
{%- if newAnnotations.length > 0 %}

# Imported:: {{importDate | format("YYYY-MM-DD h:mm a")}}

{% for a in newAnnotations %}

---
## Annotation on page {{a.pageLabel}} at {{a.date | format("YYYY-MM-DD hh:mm")}}
> [!quote] 
> *{{a.annotatedText}}*

**Zotero Link**: [click to go to zotero annotation]({{a.desktopURI}})
**Highlight colour**: {{a.colorCategory}}
### Comments
{{a.comment}}
{% endfor -%}
{%- endif -%}
{%- endpersist -%}
