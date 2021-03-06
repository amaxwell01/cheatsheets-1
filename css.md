title: CSS
---

Animations
----------

### Animtaion

    animation-direction: normal | reverse | alternate | alternate-reverse
    animation-iteration-count: infinite | <number>

    animation: <name> <duration> <timing-function> <delay> <count> <direction> <fill-mode>

    animation: bounce 300ms linear infinite

Webkit extensions
-----------------

### Font smoothing

    /* maxvoltar.com/archive/-webkit-font-smoothing */
    * {
      text-rendering: optimizeLegibility !important;
      -webkit-font-smoothing: antialiased !important;
    }

### Heading kerning pairs and ligature

    h1, h2, h3 { text-rendering: optimizeLegibility; }

### Native-like iOS scrolling

    -webkit-overflow-scrolling: touch;
    overflow-y: auto;

### Gradient text

    background: -webkit-gradient(linear, left top, left bottom, from(#eee), to(#333));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;

### Text stroke

    /* http://www.webkit.org/blog/85/introducing-text-stroke/ */
    -webkit-text-stroke: 3px black;

### iOS Scrolling prevention

    document.ontouchstart = (e) ->
      $pane = $(e.target).closest('.scrollable>div')
      if $pane.length is 0 or $pane[0].scrollHeight <= $pane.innerHeight()
        e.preventDefault()

    %ios-scrollable
      &, >div
        -webkit-overflow-scrolling: touch
        overflow: auto

      >div
        position: absolute
        top: 0
        left: 0
        right: 0
        bottom: 0

### UIWebView optimizations

    /* http://www.bitsandpix.com/entry/ios-webkit-uiwebview-remove-tapclick-highlightborder-with-css/ */

    * {
      -webkit-tap-highlight-color: rgba(0,0,0,0);
      -webkit-user-select: none;                /* disable text select */
      -webkit-touch-callout: none;              /* disable callout, image save panel (popup) */
      -webkit-tap-highlight-color: transparent; /* "turn off" link highlight */
    }

    a:focus {
      outline:0; // Firefox (remove border on link click)
    }
