// ==UserScript==
// @name         Ontbindknop verwijderaar
// @version      1.0.0
// @author       Ikzelf
// @include https://nl115.grepolis.com/game/*
// @exclude forum.*.grepolis.*/*
// @exclude wiki.*.grepolis.*/*
// @grant        none
// ==/UserScript==

(async function () {
  console.log('Starting ontbindknop removal')
  $(document).ajaxComplete(function (e, xhr, opt) {
    var url = opt.url.split('?'), action = ''
    if (typeof (url[1]) !== 'undefined' && typeof (url[1].split(/&/)[1]) !== 'undefined') {
      action = url[0].substr(5) + '/' + url[1].split(/&/)[1].substr(7)
    }
    switch (action) {
      case '/alliance/properties':
        setTimeout(deleteOntbind, 50)
    }
  })

  function deleteOntbind() {
    const leaveSectionChildren = $('#ally_leave').children()
    const oprichter = leaveSectionChildren.length > 1
    if (oprichter) {
      leaveSectionChildren[0].remove()
    }
  }

})()
