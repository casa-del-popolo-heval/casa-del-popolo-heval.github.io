---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
    image:  "cdph-super-banner.jpg"
    pattern:  "green.jpg"
widget1:
  title: "Attività"
  url: '/dove-andiamo/attivita/'
  image: widget-1-302x182.jpg
  text: 'Scopri le attività e gli eventi ospitati dalla casa del popolo Heval'
widget2:
  title: "Biblioteca Heval"
  url: '/biblioteca/'
  image: start-video-feeling-responsive-302x182.jpg
  text: 'Scopri i libri che puoi prendere in prestito dalla Biblioteca Heval'
widget3:
  title: "Realtà"
  url: '/dove-andiamo/realta/'
  image: copertina-realta.jpg
  text: 'Maggiori informazioni sulle realtà che vivono la casa del popolo Heval'
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
callforaction:
  url: '/donacdp/'
  text: Dona alla casa del popolo ›
  style: alert
permalink: /index.html

#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---
