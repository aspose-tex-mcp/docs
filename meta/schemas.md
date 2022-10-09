---
translation: true
deploy: false
---

{{<section faq>}}

{
    "@context": "https://schema.org",
    "@type": "FAQPage",
    "mainEntity": [      
      {{#qs}}
      {
        "@type": "Question",
        "name": "{{name}}",
        "acceptedAnswer": {
          "@type": "Answer",
          "text": "{{text}}"
        }
      },     
    {{/qs}}    
    ]
}