---
title: "Publications"
permalink: /publications/
layout: page
---

{% for pub in site.data.publications %}
### {{ pub.title }} ({{ pub.year }})
**Authors:** {{ pub.authors }}  
{% if pub.doi %}**DOI:** [{{ pub.doi }}]({{ pub.url }}){% endif %}  
{{ pub.description }}

---
{% endfor %}
