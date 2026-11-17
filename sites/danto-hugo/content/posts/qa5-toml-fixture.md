+++
# QA5 TOML front matter fixture. The comment and key order must survive a body edit.
title = 'QA5 TOML fixture'
description = "TOML front matter with \"escaped\" quotes"
date = 2026-11-18T10:00:00+05:30
draft = false
tags = ["qa", 'toml']
author = { name = "QA", role = 'tester' }
+++

Intro paragraph with a reference link [the docs][docs-ref] and a reference image ![logo][logo-img] in the middle.

Second paragraph is one line and ends the intro section.

Plain soft wrap paragraph
on two source lines.

[docs-ref]: https://pinggy.io/docs
[logo-img]: /images/logo.png "Logo title"
