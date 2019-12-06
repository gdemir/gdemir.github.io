---
layout: post
title: Bootstrap Hover Dropdown
category: bootstrap
tags: html script hover
---

#### Html
	<li class="dropdown">
		<a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-expanded="false">
		Gökhan Demir
		<span class="caret"></span>
		</a>
		<ul class="dropdown-menu" role="menu">
			<li><a href="#">Hesap</a></li>
			<li class="divider"></li>
			<li><a href="#">Çıkış</a></li>
		</ul>
	</li>

#### Script

	  <!-- dropdown hover -->
	  <script src="../assets/js/bootstrap-hover-dropdown.min.js"></script>
	  <script type="text/javascript">
		$('.dropdown-toggle').dropdownHover();
	  </script>
	  <!-- dropdown hover end -->

#### Kaynak

- [Bootstrap Hover Dropdown](https://cameronspear.com/demos/bootstrap-hover-dropdown/)

- [bootstrap-hover-dropdown.min.js](https://raw.githubusercontent.com/CWSpear/bootstrap-hover-dropdown/master/bootstrap-hover-dropdown.min.js)

