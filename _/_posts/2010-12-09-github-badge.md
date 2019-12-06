---
layout: post
title: GitHub Badge
category: github
tags: badge
---

GitHubdaki projelerinizin, gistlerinizin, grup üyelerinizin, grup görevlerinizin  
ufak görüntüsünü sayfanıza eklemek için öncelikle gerekli github-badge türlerinden  
birini [http://github.com/gdemir/github-badge](http://github.com/gdemir/github-badge)  
sayfasından seçip, sitenize eklemeniz yeterli  
ör. gdemir adlı kişinin repolarını görmek için aşağıdaki js kodu :  


  <div id="github-badge"></div>
  <script type="text/javascript" charset="utf-8">
          GITHUB_USERNAME = "gdemir";
          GITHUB_LIST_LENGTH = 10;
          GITHUB_TITLE = "Projelerim"
          GITHUB_SHOW_ALL = "Hepsini Göster"
  </script>
  <script src="http://gdemir.github.io/github-badge/github-badge-repo.js" type="text/javascript">
  </script>


şeklinde html içine aşağıdaki gibi eklemeniz yeterlidir :


  <html>
  <body>
  <div id="github-badge"></div>
  <script type="text/javascript" charset="utf-8">
          GITHUB_USERNAME = "gdemir";
          GITHUB_LIST_LENGTH = 10;
          GITHUB_TITLE = "Projelerim"
          GITHUB_SHOW_ALL = "Hepsini Göster"
  </script>
  <script src="http://gdemir.github.io/github-badge/github-badge-repo.js" type="text/javascript">
  </script>
  </body>
  </html>


github-badge'nin yerini değiştirmek için css ile oynanabilir, benim sitem'deki
css ayarlarım ("`local.css`"de) şöyle: (ör. repo için)


  #github-badge {
    width: 450px !important;
    float: left !important;
    clear: right !important;
    margin-top: 4em !important;
    margin-left: 25em !important;
    margin-right: 1em !important;
  }


http://github.com/github-badge ile yapdığım çalışmalara örnekler ise :

- [http://gdemir.github.io/github-badge](http://gdemir.github.io/github-badge)

- [http://gdemir.github.io/19badge](http://gdemir.github.io/19badge)

çalışan kod ise şöyledir :


<div id="github-badge"></div>
<script type="text/javascript" charset="utf-8">
	GITHUB_USERNAME = "gdemir";
	GITHUB_LIST_LENGTH = 10;
	GITHUB_TITLE = "Projelerim";
	GITHUB_SHOW_ALL = "Hepsini Göster";
</script>
<script src="http://gdemir.github.io/github-badge/github-badge-repo.js" type="text/javascript">

