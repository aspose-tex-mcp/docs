---
template: true
title: {{i18n.title}}
description: {{i18n.description}}
url: {{i18n.url}}
feature: merger
---

{{< blocks/products/pf/main-wrap-class isAutogenPage="true">}}
{{< blocks/products/pf/feature-page-wrap >}}
{{< blocks/products/pf/feature-page-header h1="{{i18n.banner.h1}}"  h2="{{i18n.banner.h2}}" >}}

{{% blocks/products/pf/feature-page-section  h2="{{i18n.overview.h2}}" %}}

{{i18n.overview}}

<div class="row">
	<div class="col-md-3">
		<ul>
			<li><a href="/html/{{lang.url-fragment}}net/merger/html/">HTML Merger</a></li>										
		</ul>
	</div>
	<div class="col-md-3">
		<ul>
			<li><a href="/html/{{lang.url-fragment}}net/merger/mhtml/">MHTML Merger</a></li>		
		</ul>
	</div>
	<div class="col-md-3">
		<ul>
			<li><a href="/html/{{lang.url-fragment}}net/merger/epub/">EPUB Merger</a></li>					
		</ul>
	</div>
	<div class="col-md-3">
		<ul>
			<li><a href="/html/{{lang.url-fragment}}net/merger/md/">MD Merger</a></li>	
		</ul>
	</div>
</div>

<h2>{{i18n.demos.h2}}</h2>

{{i18n.demos}}

{{% /blocks/products/pf/feature-page-section %}}

{{i18n.app-pluging}}

{{% blocks/products/pf/feature-page-section  h2="{{i18n.installing.h2}}" %}}

{{i18n.installing}}

<h2>{{i18n.other-aspose.h2}}</h2>

{{i18n.other-aspose}}

{{<import path="/{{lang}}/partials/_othersupported.md" section="aspose">}}

{{% /blocks/products/pf/feature-page-section %}}
{{< /blocks/products/pf/feature-page-wrap >}}
{{< /blocks/products/pf/main-wrap-class >}}