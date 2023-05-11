window[btoa('video intelligence start')] || (window[btoa('video intelligence start')] = (function() {
  var source = 'https://s.vi-serve.com/source.js';
  function isNative(fn) {
    return typeof fn === 'function' && (/\{\s*\[native code\]\s*\}/).test('' + fn);
  }
  if(
    window.Promise &&
    window.Promise.prototype &&
    window.Promise.prototype.finally &&
    isNative(window.Promise.prototype.finally) &&
    window.IntersectionObserver &&
    isNative(window.IntersectionObserver) ||
    (window.Zone &&
      window.Zone.prototype &&
      window.Zone.prototype.fork &&
      window.Zone.prototype.run)
  ) {
    source = 'https://s.vi-serve.com/source.m.js';
  }

  return {
    init: function(config) {
      var v = document, i = window, ins, win, scr;
      config.VersionOfTag = 'v3';
      if(config.DivID) {
        if(v.getElementById(config.DivID)) {
          ins = v.getElementById(config.DivID);
          win = i;
        } else if(i.frameElement && i.parent.document.getElementById(config.DivID)) {
          ins = i.parent.document.getElementById(config.DivID);
          win = i.parent;
        }
      }
      if(!ins) {
        if(
          i.frameElement &&
          (i.frameElement.width === '1' || i.frameElement.width === '2' || i.frameElement.width === '3') &&
          (i.frameElement.height === '1' || i.frameElement.height === '2' || i.frameElement.height === '3')
        ) {
          ins = i.frameElement.parentNode.parentNode;
          win = i.parent;
        } else {
          ins = v.body || v.documentElement.appendChild(v.createElement('body'));
          win = i;
        }
      }
      scr = win.document.createElement('script');
      scr.id = 'vi-' + config.PublisherID;
      scr.src = source;
      scr.async = !0;
      scr.onload = function() {
        win[btoa('video intelligence')].run(config, void 0 === v.currentScript ? v.scripts[v.scripts.length - 1] : v.currentScript, source);
      };
      ins.appendChild(scr);
    }
  };
}()));
