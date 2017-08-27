---
title: WordPress Development
description: Tutorial about our WordPress stack and how to develop on it
---

## WordPress Development

This tutorial covers all the standards and the procedures we use to ensure that all the developers working for 9th Circle Games have all the needed tools and a common codebase. This will avoid reinventing the wheel everytime and ensure that all our websites are consistent, all they all share a common baseline

### Components

The Web Architecture we use is based on WordPress MultiSite configuration executing trough a static cache to speed up loading times. These are the main components running on the server:

* __WordPress__, of course. We use a multisite installation which is provisioned in a Vagrant Box. _[Learn more]({% link vagrantbox.md %})_.
* __[WPML](https://wpml.org)__, for multilanguage/localizing websites.
* __[Divi](https://www.elegantthemes.com/gallery/divi)__, by Elegant Themes. This is a premium theme which have a [very advanced page builder](https://www.elegantthemes.com/plugins/divi-builder/) which really speeds up coding. We use it as common features baseline.
* __Products & Brands WordPress Themes__. These themes are built by us in form of Divi child themes. A typical example is [the one we made](https://github.com/9thcirclegames/eden-wp) for our game __Eden: Deception__. See below on how to develop such those themes.
* __[Bloom](https://www.elegantthemes.com/plugins/bloom/)__, by Elegant Themes. This premium plugin is used as lead collecting (ie subscribe to the newsletter) platform.
* __[Monarch](https://www.elegantthemes.com/plugins/monarch/)__, by Elegant Themes. This premium plugin is used as Social Media Sharing platform.
* __[WP Rocket](https://wp-rocket.me)__. This premium plugin is used as Database/OOP Primary Cache. This will ensure that no overloads come to the back-end of the websites (database, webserver).
* __[CloudFlare](https://www.cloudflare.com)__. CloudFlare is used as HTTPS proxy, caching html, css, js and all other kind of static files. This will protect against DDoS attacks and ensure that CDN will serve files from the best location of the Internet, depending of the IP of the users. This will also save a lot of bandwhich.
* __[Amazon S3](https://aws.amazon.com/it/s3/)__. This service is used to store static assets, for example images and videos. Pratically, it is a DAM (Digital Assets Management Platform). As a consequences, this means that we don't use the media library embedded in Wordpress. This for security and performance reasons. In facts, [we have a tool to automatically deploy files on the DAM]({% link digitalassetsmanagement.md %}), so it doesn't have to be done by hands.
* __[Prometheus](https://github.com/9thcirclegames/prometheus)__. Prometheus is a collection of common functions and classes used in all our Wordpress child themes) themes. It is not used directly on production server as a WordPress plugin, but as a git submodule to be included in the aforementioned Wordpress themes (see below). This for performance and security reasons. See below for more details about Prometheus.
* __Various Other Tools__ like Google Tag Manager, MailChimps and so on, AntiSpam and other security tools and so on.