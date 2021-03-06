<html>
<head><meta charset="utf-8" />

<title>03-13-latent-variable-models</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/require.js/2.1.10/require.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/2.0.3/jquery.min.js"></script>



<style type="text/css">
    /*!
*
* Twitter Bootstrap
*
*/
/*!
 * Bootstrap v3.3.7 (http://getbootstrap.com)
 * Copyright 2011-2016 Twitter, Inc.
 * Licensed under MIT (https://github.com/twbs/bootstrap/blob/master/LICENSE)
 */
/*! normalize.css v3.0.3 | MIT License | github.com/necolas/normalize.css */
html {
  font-family: sans-serif;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
}
body {
  margin: 0;
}
article,
aside,
details,
figcaption,
figure,
footer,
header,
hgroup,
main,
menu,
nav,
section,
summary {
  display: block;
}
audio,
canvas,
progress,
video {
  display: inline-block;
  vertical-align: baseline;
}
audio:not([controls]) {
  display: none;
  height: 0;
}
[hidden],
template {
  display: none;
}
a {
  background-color: transparent;
}
a:active,
a:hover {
  outline: 0;
}
abbr[title] {
  border-bottom: 1px dotted;
}
b,
strong {
  font-weight: bold;
}
dfn {
  font-style: italic;
}
h1 {
  font-size: 2em;
  margin: 0.67em 0;
}
mark {
  background: #ff0;
  color: #000;
}
small {
  font-size: 80%;
}
sub,
sup {
  font-size: 75%;
  line-height: 0;
  position: relative;
  vertical-align: baseline;
}
sup {
  top: -0.5em;
}
sub {
  bottom: -0.25em;
}
img {
  border: 0;
}
svg:not(:root) {
  overflow: hidden;
}
figure {
  margin: 1em 40px;
}
hr {
  box-sizing: content-box;
  height: 0;
}
pre {
  overflow: auto;
}
code,
kbd,
pre,
samp {
  font-family: monospace, monospace;
  font-size: 1em;
}
button,
input,
optgroup,
select,
textarea {
  color: inherit;
  font: inherit;
  margin: 0;
}
button {
  overflow: visible;
}
button,
select {
  text-transform: none;
}
button,
html input[type="button"],
input[type="reset"],
input[type="submit"] {
  -webkit-appearance: button;
  cursor: pointer;
}
button[disabled],
html input[disabled] {
  cursor: default;
}
button::-moz-focus-inner,
input::-moz-focus-inner {
  border: 0;
  padding: 0;
}
input {
  line-height: normal;
}
input[type="checkbox"],
input[type="radio"] {
  box-sizing: border-box;
  padding: 0;
}
input[type="number"]::-webkit-inner-spin-button,
input[type="number"]::-webkit-outer-spin-button {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: textfield;
  box-sizing: content-box;
}
input[type="search"]::-webkit-search-cancel-button,
input[type="search"]::-webkit-search-decoration {
  -webkit-appearance: none;
}
fieldset {
  border: 1px solid #c0c0c0;
  margin: 0 2px;
  padding: 0.35em 0.625em 0.75em;
}
legend {
  border: 0;
  padding: 0;
}
textarea {
  overflow: auto;
}
optgroup {
  font-weight: bold;
}
table {
  border-collapse: collapse;
  border-spacing: 0;
}
td,
th {
  padding: 0;
}
/*! Source: https://github.com/h5bp/html5-boilerplate/blob/master/src/css/main.css */
@media print {
  *,
  *:before,
  *:after {
    background: transparent !important;
    box-shadow: none !important;
    text-shadow: none !important;
  }
  a,
  a:visited {
    text-decoration: underline;
  }
  a[href]:after {
    content: " (" attr(href) ")";
  }
  abbr[title]:after {
    content: " (" attr(title) ")";
  }
  a[href^="#"]:after,
  a[href^="javascript:"]:after {
    content: "";
  }
  pre,
  blockquote {
    border: 1px solid #999;
    page-break-inside: avoid;
  }
  thead {
    display: table-header-group;
  }
  tr,
  img {
    page-break-inside: avoid;
  }
  img {
    max-width: 100% !important;
  }
  p,
  h2,
  h3 {
    orphans: 3;
    widows: 3;
  }
  h2,
  h3 {
    page-break-after: avoid;
  }
  .navbar {
    display: none;
  }
  .btn > .caret,
  .dropup > .btn > .caret {
    border-top-color: #000 !important;
  }
  .label {
    border: 1px solid #000;
  }
  .table {
    border-collapse: collapse !important;
  }
  .table td,
  .table th {
    background-color: #fff !important;
  }
  .table-bordered th,
  .table-bordered td {
    border: 1px solid #ddd !important;
  }
}
@font-face {
  font-family: 'Glyphicons Halflings';
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot');
  src: url('../components/bootstrap/fonts/glyphicons-halflings-regular.eot?#iefix') format('embedded-opentype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff2') format('woff2'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.woff') format('woff'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.ttf') format('truetype'), url('../components/bootstrap/fonts/glyphicons-halflings-regular.svg#glyphicons_halflingsregular') format('svg');
}
.glyphicon {
  position: relative;
  top: 1px;
  display: inline-block;
  font-family: 'Glyphicons Halflings';
  font-style: normal;
  font-weight: normal;
  line-height: 1;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.glyphicon-asterisk:before {
  content: "\002a";
}
.glyphicon-plus:before {
  content: "\002b";
}
.glyphicon-euro:before,
.glyphicon-eur:before {
  content: "\20ac";
}
.glyphicon-minus:before {
  content: "\2212";
}
.glyphicon-cloud:before {
  content: "\2601";
}
.glyphicon-envelope:before {
  content: "\2709";
}
.glyphicon-pencil:before {
  content: "\270f";
}
.glyphicon-glass:before {
  content: "\e001";
}
.glyphicon-music:before {
  content: "\e002";
}
.glyphicon-search:before {
  content: "\e003";
}
.glyphicon-heart:before {
  content: "\e005";
}
.glyphicon-star:before {
  content: "\e006";
}
.glyphicon-star-empty:before {
  content: "\e007";
}
.glyphicon-user:before {
  content: "\e008";
}
.glyphicon-film:before {
  content: "\e009";
}
.glyphicon-th-large:before {
  content: "\e010";
}
.glyphicon-th:before {
  content: "\e011";
}
.glyphicon-th-list:before {
  content: "\e012";
}
.glyphicon-ok:before {
  content: "\e013";
}
.glyphicon-remove:before {
  content: "\e014";
}
.glyphicon-zoom-in:before {
  content: "\e015";
}
.glyphicon-zoom-out:before {
  content: "\e016";
}
.glyphicon-off:before {
  content: "\e017";
}
.glyphicon-signal:before {
  content: "\e018";
}
.glyphicon-cog:before {
  content: "\e019";
}
.glyphicon-trash:before {
  content: "\e020";
}
.glyphicon-home:before {
  content: "\e021";
}
.glyphicon-file:before {
  content: "\e022";
}
.glyphicon-time:before {
  content: "\e023";
}
.glyphicon-road:before {
  content: "\e024";
}
.glyphicon-download-alt:before {
  content: "\e025";
}
.glyphicon-download:before {
  content: "\e026";
}
.glyphicon-upload:before {
  content: "\e027";
}
.glyphicon-inbox:before {
  content: "\e028";
}
.glyphicon-play-circle:before {
  content: "\e029";
}
.glyphicon-repeat:before {
  content: "\e030";
}
.glyphicon-refresh:before {
  content: "\e031";
}
.glyphicon-list-alt:before {
  content: "\e032";
}
.glyphicon-lock:before {
  content: "\e033";
}
.glyphicon-flag:before {
  content: "\e034";
}
.glyphicon-headphones:before {
  content: "\e035";
}
.glyphicon-volume-off:before {
  content: "\e036";
}
.glyphicon-volume-down:before {
  content: "\e037";
}
.glyphicon-volume-up:before {
  content: "\e038";
}
.glyphicon-qrcode:before {
  content: "\e039";
}
.glyphicon-barcode:before {
  content: "\e040";
}
.glyphicon-tag:before {
  content: "\e041";
}
.glyphicon-tags:before {
  content: "\e042";
}
.glyphicon-book:before {
  content: "\e043";
}
.glyphicon-bookmark:before {
  content: "\e044";
}
.glyphicon-print:before {
  content: "\e045";
}
.glyphicon-camera:before {
  content: "\e046";
}
.glyphicon-font:before {
  content: "\e047";
}
.glyphicon-bold:before {
  content: "\e048";
}
.glyphicon-italic:before {
  content: "\e049";
}
.glyphicon-text-height:before {
  content: "\e050";
}
.glyphicon-text-width:before {
  content: "\e051";
}
.glyphicon-align-left:before {
  content: "\e052";
}
.glyphicon-align-center:before {
  content: "\e053";
}
.glyphicon-align-right:before {
  content: "\e054";
}
.glyphicon-align-justify:before {
  content: "\e055";
}
.glyphicon-list:before {
  content: "\e056";
}
.glyphicon-indent-left:before {
  content: "\e057";
}
.glyphicon-indent-right:before {
  content: "\e058";
}
.glyphicon-facetime-video:before {
  content: "\e059";
}
.glyphicon-picture:before {
  content: "\e060";
}
.glyphicon-map-marker:before {
  content: "\e062";
}
.glyphicon-adjust:before {
  content: "\e063";
}
.glyphicon-tint:before {
  content: "\e064";
}
.glyphicon-edit:before {
  content: "\e065";
}
.glyphicon-share:before {
  content: "\e066";
}
.glyphicon-check:before {
  content: "\e067";
}
.glyphicon-move:before {
  content: "\e068";
}
.glyphicon-step-backward:before {
  content: "\e069";
}
.glyphicon-fast-backward:before {
  content: "\e070";
}
.glyphicon-backward:before {
  content: "\e071";
}
.glyphicon-play:before {
  content: "\e072";
}
.glyphicon-pause:before {
  content: "\e073";
}
.glyphicon-stop:before {
  content: "\e074";
}
.glyphicon-forward:before {
  content: "\e075";
}
.glyphicon-fast-forward:before {
  content: "\e076";
}
.glyphicon-step-forward:before {
  content: "\e077";
}
.glyphicon-eject:before {
  content: "\e078";
}
.glyphicon-chevron-left:before {
  content: "\e079";
}
.glyphicon-chevron-right:before {
  content: "\e080";
}
.glyphicon-plus-sign:before {
  content: "\e081";
}
.glyphicon-minus-sign:before {
  content: "\e082";
}
.glyphicon-remove-sign:before {
  content: "\e083";
}
.glyphicon-ok-sign:before {
  content: "\e084";
}
.glyphicon-question-sign:before {
  content: "\e085";
}
.glyphicon-info-sign:before {
  content: "\e086";
}
.glyphicon-screenshot:before {
  content: "\e087";
}
.glyphicon-remove-circle:before {
  content: "\e088";
}
.glyphicon-ok-circle:before {
  content: "\e089";
}
.glyphicon-ban-circle:before {
  content: "\e090";
}
.glyphicon-arrow-left:before {
  content: "\e091";
}
.glyphicon-arrow-right:before {
  content: "\e092";
}
.glyphicon-arrow-up:before {
  content: "\e093";
}
.glyphicon-arrow-down:before {
  content: "\e094";
}
.glyphicon-share-alt:before {
  content: "\e095";
}
.glyphicon-resize-full:before {
  content: "\e096";
}
.glyphicon-resize-small:before {
  content: "\e097";
}
.glyphicon-exclamation-sign:before {
  content: "\e101";
}
.glyphicon-gift:before {
  content: "\e102";
}
.glyphicon-leaf:before {
  content: "\e103";
}
.glyphicon-fire:before {
  content: "\e104";
}
.glyphicon-eye-open:before {
  content: "\e105";
}
.glyphicon-eye-close:before {
  content: "\e106";
}
.glyphicon-warning-sign:before {
  content: "\e107";
}
.glyphicon-plane:before {
  content: "\e108";
}
.glyphicon-calendar:before {
  content: "\e109";
}
.glyphicon-random:before {
  content: "\e110";
}
.glyphicon-comment:before {
  content: "\e111";
}
.glyphicon-magnet:before {
  content: "\e112";
}
.glyphicon-chevron-up:before {
  content: "\e113";
}
.glyphicon-chevron-down:before {
  content: "\e114";
}
.glyphicon-retweet:before {
  content: "\e115";
}
.glyphicon-shopping-cart:before {
  content: "\e116";
}
.glyphicon-folder-close:before {
  content: "\e117";
}
.glyphicon-folder-open:before {
  content: "\e118";
}
.glyphicon-resize-vertical:before {
  content: "\e119";
}
.glyphicon-resize-horizontal:before {
  content: "\e120";
}
.glyphicon-hdd:before {
  content: "\e121";
}
.glyphicon-bullhorn:before {
  content: "\e122";
}
.glyphicon-bell:before {
  content: "\e123";
}
.glyphicon-certificate:before {
  content: "\e124";
}
.glyphicon-thumbs-up:before {
  content: "\e125";
}
.glyphicon-thumbs-down:before {
  content: "\e126";
}
.glyphicon-hand-right:before {
  content: "\e127";
}
.glyphicon-hand-left:before {
  content: "\e128";
}
.glyphicon-hand-up:before {
  content: "\e129";
}
.glyphicon-hand-down:before {
  content: "\e130";
}
.glyphicon-circle-arrow-right:before {
  content: "\e131";
}
.glyphicon-circle-arrow-left:before {
  content: "\e132";
}
.glyphicon-circle-arrow-up:before {
  content: "\e133";
}
.glyphicon-circle-arrow-down:before {
  content: "\e134";
}
.glyphicon-globe:before {
  content: "\e135";
}
.glyphicon-wrench:before {
  content: "\e136";
}
.glyphicon-tasks:before {
  content: "\e137";
}
.glyphicon-filter:before {
  content: "\e138";
}
.glyphicon-briefcase:before {
  content: "\e139";
}
.glyphicon-fullscreen:before {
  content: "\e140";
}
.glyphicon-dashboard:before {
  content: "\e141";
}
.glyphicon-paperclip:before {
  content: "\e142";
}
.glyphicon-heart-empty:before {
  content: "\e143";
}
.glyphicon-link:before {
  content: "\e144";
}
.glyphicon-phone:before {
  content: "\e145";
}
.glyphicon-pushpin:before {
  content: "\e146";
}
.glyphicon-usd:before {
  content: "\e148";
}
.glyphicon-gbp:before {
  content: "\e149";
}
.glyphicon-sort:before {
  content: "\e150";
}
.glyphicon-sort-by-alphabet:before {
  content: "\e151";
}
.glyphicon-sort-by-alphabet-alt:before {
  content: "\e152";
}
.glyphicon-sort-by-order:before {
  content: "\e153";
}
.glyphicon-sort-by-order-alt:before {
  content: "\e154";
}
.glyphicon-sort-by-attributes:before {
  content: "\e155";
}
.glyphicon-sort-by-attributes-alt:before {
  content: "\e156";
}
.glyphicon-unchecked:before {
  content: "\e157";
}
.glyphicon-expand:before {
  content: "\e158";
}
.glyphicon-collapse-down:before {
  content: "\e159";
}
.glyphicon-collapse-up:before {
  content: "\e160";
}
.glyphicon-log-in:before {
  content: "\e161";
}
.glyphicon-flash:before {
  content: "\e162";
}
.glyphicon-log-out:before {
  content: "\e163";
}
.glyphicon-new-window:before {
  content: "\e164";
}
.glyphicon-record:before {
  content: "\e165";
}
.glyphicon-save:before {
  content: "\e166";
}
.glyphicon-open:before {
  content: "\e167";
}
.glyphicon-saved:before {
  content: "\e168";
}
.glyphicon-import:before {
  content: "\e169";
}
.glyphicon-export:before {
  content: "\e170";
}
.glyphicon-send:before {
  content: "\e171";
}
.glyphicon-floppy-disk:before {
  content: "\e172";
}
.glyphicon-floppy-saved:before {
  content: "\e173";
}
.glyphicon-floppy-remove:before {
  content: "\e174";
}
.glyphicon-floppy-save:before {
  content: "\e175";
}
.glyphicon-floppy-open:before {
  content: "\e176";
}
.glyphicon-credit-card:before {
  content: "\e177";
}
.glyphicon-transfer:before {
  content: "\e178";
}
.glyphicon-cutlery:before {
  content: "\e179";
}
.glyphicon-header:before {
  content: "\e180";
}
.glyphicon-compressed:before {
  content: "\e181";
}
.glyphicon-earphone:before {
  content: "\e182";
}
.glyphicon-phone-alt:before {
  content: "\e183";
}
.glyphicon-tower:before {
  content: "\e184";
}
.glyphicon-stats:before {
  content: "\e185";
}
.glyphicon-sd-video:before {
  content: "\e186";
}
.glyphicon-hd-video:before {
  content: "\e187";
}
.glyphicon-subtitles:before {
  content: "\e188";
}
.glyphicon-sound-stereo:before {
  content: "\e189";
}
.glyphicon-sound-dolby:before {
  content: "\e190";
}
.glyphicon-sound-5-1:before {
  content: "\e191";
}
.glyphicon-sound-6-1:before {
  content: "\e192";
}
.glyphicon-sound-7-1:before {
  content: "\e193";
}
.glyphicon-copyright-mark:before {
  content: "\e194";
}
.glyphicon-registration-mark:before {
  content: "\e195";
}
.glyphicon-cloud-download:before {
  content: "\e197";
}
.glyphicon-cloud-upload:before {
  content: "\e198";
}
.glyphicon-tree-conifer:before {
  content: "\e199";
}
.glyphicon-tree-deciduous:before {
  content: "\e200";
}
.glyphicon-cd:before {
  content: "\e201";
}
.glyphicon-save-file:before {
  content: "\e202";
}
.glyphicon-open-file:before {
  content: "\e203";
}
.glyphicon-level-up:before {
  content: "\e204";
}
.glyphicon-copy:before {
  content: "\e205";
}
.glyphicon-paste:before {
  content: "\e206";
}
.glyphicon-alert:before {
  content: "\e209";
}
.glyphicon-equalizer:before {
  content: "\e210";
}
.glyphicon-king:before {
  content: "\e211";
}
.glyphicon-queen:before {
  content: "\e212";
}
.glyphicon-pawn:before {
  content: "\e213";
}
.glyphicon-bishop:before {
  content: "\e214";
}
.glyphicon-knight:before {
  content: "\e215";
}
.glyphicon-baby-formula:before {
  content: "\e216";
}
.glyphicon-tent:before {
  content: "\26fa";
}
.glyphicon-blackboard:before {
  content: "\e218";
}
.glyphicon-bed:before {
  content: "\e219";
}
.glyphicon-apple:before {
  content: "\f8ff";
}
.glyphicon-erase:before {
  content: "\e221";
}
.glyphicon-hourglass:before {
  content: "\231b";
}
.glyphicon-lamp:before {
  content: "\e223";
}
.glyphicon-duplicate:before {
  content: "\e224";
}
.glyphicon-piggy-bank:before {
  content: "\e225";
}
.glyphicon-scissors:before {
  content: "\e226";
}
.glyphicon-bitcoin:before {
  content: "\e227";
}
.glyphicon-btc:before {
  content: "\e227";
}
.glyphicon-xbt:before {
  content: "\e227";
}
.glyphicon-yen:before {
  content: "\00a5";
}
.glyphicon-jpy:before {
  content: "\00a5";
}
.glyphicon-ruble:before {
  content: "\20bd";
}
.glyphicon-rub:before {
  content: "\20bd";
}
.glyphicon-scale:before {
  content: "\e230";
}
.glyphicon-ice-lolly:before {
  content: "\e231";
}
.glyphicon-ice-lolly-tasted:before {
  content: "\e232";
}
.glyphicon-education:before {
  content: "\e233";
}
.glyphicon-option-horizontal:before {
  content: "\e234";
}
.glyphicon-option-vertical:before {
  content: "\e235";
}
.glyphicon-menu-hamburger:before {
  content: "\e236";
}
.glyphicon-modal-window:before {
  content: "\e237";
}
.glyphicon-oil:before {
  content: "\e238";
}
.glyphicon-grain:before {
  content: "\e239";
}
.glyphicon-sunglasses:before {
  content: "\e240";
}
.glyphicon-text-size:before {
  content: "\e241";
}
.glyphicon-text-color:before {
  content: "\e242";
}
.glyphicon-text-background:before {
  content: "\e243";
}
.glyphicon-object-align-top:before {
  content: "\e244";
}
.glyphicon-object-align-bottom:before {
  content: "\e245";
}
.glyphicon-object-align-horizontal:before {
  content: "\e246";
}
.glyphicon-object-align-left:before {
  content: "\e247";
}
.glyphicon-object-align-vertical:before {
  content: "\e248";
}
.glyphicon-object-align-right:before {
  content: "\e249";
}
.glyphicon-triangle-right:before {
  content: "\e250";
}
.glyphicon-triangle-left:before {
  content: "\e251";
}
.glyphicon-triangle-bottom:before {
  content: "\e252";
}
.glyphicon-triangle-top:before {
  content: "\e253";
}
.glyphicon-console:before {
  content: "\e254";
}
.glyphicon-superscript:before {
  content: "\e255";
}
.glyphicon-subscript:before {
  content: "\e256";
}
.glyphicon-menu-left:before {
  content: "\e257";
}
.glyphicon-menu-right:before {
  content: "\e258";
}
.glyphicon-menu-down:before {
  content: "\e259";
}
.glyphicon-menu-up:before {
  content: "\e260";
}
* {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
*:before,
*:after {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
html {
  font-size: 10px;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 13px;
  line-height: 1.42857143;
  color: #000;
  background-color: #fff;
}
input,
button,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}
a {
  color: #337ab7;
  text-decoration: none;
}
a:hover,
a:focus {
  color: #23527c;
  text-decoration: underline;
}
a:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
figure {
  margin: 0;
}
img {
  vertical-align: middle;
}
.img-responsive,
.thumbnail > img,
.thumbnail a > img,
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  display: block;
  max-width: 100%;
  height: auto;
}
.img-rounded {
  border-radius: 3px;
}
.img-thumbnail {
  padding: 4px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: all 0.2s ease-in-out;
  -o-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  max-width: 100%;
  height: auto;
}
.img-circle {
  border-radius: 50%;
}
hr {
  margin-top: 18px;
  margin-bottom: 18px;
  border: 0;
  border-top: 1px solid #eeeeee;
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
[role="button"] {
  cursor: pointer;
}
h1,
h2,
h3,
h4,
h5,
h6,
.h1,
.h2,
.h3,
.h4,
.h5,
.h6 {
  font-family: inherit;
  font-weight: 500;
  line-height: 1.1;
  color: inherit;
}
h1 small,
h2 small,
h3 small,
h4 small,
h5 small,
h6 small,
.h1 small,
.h2 small,
.h3 small,
.h4 small,
.h5 small,
.h6 small,
h1 .small,
h2 .small,
h3 .small,
h4 .small,
h5 .small,
h6 .small,
.h1 .small,
.h2 .small,
.h3 .small,
.h4 .small,
.h5 .small,
.h6 .small {
  font-weight: normal;
  line-height: 1;
  color: #777777;
}
h1,
.h1,
h2,
.h2,
h3,
.h3 {
  margin-top: 18px;
  margin-bottom: 9px;
}
h1 small,
.h1 small,
h2 small,
.h2 small,
h3 small,
.h3 small,
h1 .small,
.h1 .small,
h2 .small,
.h2 .small,
h3 .small,
.h3 .small {
  font-size: 65%;
}
h4,
.h4,
h5,
.h5,
h6,
.h6 {
  margin-top: 9px;
  margin-bottom: 9px;
}
h4 small,
.h4 small,
h5 small,
.h5 small,
h6 small,
.h6 small,
h4 .small,
.h4 .small,
h5 .small,
.h5 .small,
h6 .small,
.h6 .small {
  font-size: 75%;
}
h1,
.h1 {
  font-size: 33px;
}
h2,
.h2 {
  font-size: 27px;
}
h3,
.h3 {
  font-size: 23px;
}
h4,
.h4 {
  font-size: 17px;
}
h5,
.h5 {
  font-size: 13px;
}
h6,
.h6 {
  font-size: 12px;
}
p {
  margin: 0 0 9px;
}
.lead {
  margin-bottom: 18px;
  font-size: 14px;
  font-weight: 300;
  line-height: 1.4;
}
@media (min-width: 768px) {
  .lead {
    font-size: 19.5px;
  }
}
small,
.small {
  font-size: 92%;
}
mark,
.mark {
  background-color: #fcf8e3;
  padding: .2em;
}
.text-left {
  text-align: left;
}
.text-right {
  text-align: right;
}
.text-center {
  text-align: center;
}
.text-justify {
  text-align: justify;
}
.text-nowrap {
  white-space: nowrap;
}
.text-lowercase {
  text-transform: lowercase;
}
.text-uppercase {
  text-transform: uppercase;
}
.text-capitalize {
  text-transform: capitalize;
}
.text-muted {
  color: #777777;
}
.text-primary {
  color: #337ab7;
}
a.text-primary:hover,
a.text-primary:focus {
  color: #286090;
}
.text-success {
  color: #3c763d;
}
a.text-success:hover,
a.text-success:focus {
  color: #2b542c;
}
.text-info {
  color: #31708f;
}
a.text-info:hover,
a.text-info:focus {
  color: #245269;
}
.text-warning {
  color: #8a6d3b;
}
a.text-warning:hover,
a.text-warning:focus {
  color: #66512c;
}
.text-danger {
  color: #a94442;
}
a.text-danger:hover,
a.text-danger:focus {
  color: #843534;
}
.bg-primary {
  color: #fff;
  background-color: #337ab7;
}
a.bg-primary:hover,
a.bg-primary:focus {
  background-color: #286090;
}
.bg-success {
  background-color: #dff0d8;
}
a.bg-success:hover,
a.bg-success:focus {
  background-color: #c1e2b3;
}
.bg-info {
  background-color: #d9edf7;
}
a.bg-info:hover,
a.bg-info:focus {
  background-color: #afd9ee;
}
.bg-warning {
  background-color: #fcf8e3;
}
a.bg-warning:hover,
a.bg-warning:focus {
  background-color: #f7ecb5;
}
.bg-danger {
  background-color: #f2dede;
}
a.bg-danger:hover,
a.bg-danger:focus {
  background-color: #e4b9b9;
}
.page-header {
  padding-bottom: 8px;
  margin: 36px 0 18px;
  border-bottom: 1px solid #eeeeee;
}
ul,
ol {
  margin-top: 0;
  margin-bottom: 9px;
}
ul ul,
ol ul,
ul ol,
ol ol {
  margin-bottom: 0;
}
.list-unstyled {
  padding-left: 0;
  list-style: none;
}
.list-inline {
  padding-left: 0;
  list-style: none;
  margin-left: -5px;
}
.list-inline > li {
  display: inline-block;
  padding-left: 5px;
  padding-right: 5px;
}
dl {
  margin-top: 0;
  margin-bottom: 18px;
}
dt,
dd {
  line-height: 1.42857143;
}
dt {
  font-weight: bold;
}
dd {
  margin-left: 0;
}
@media (min-width: 541px) {
  .dl-horizontal dt {
    float: left;
    width: 160px;
    clear: left;
    text-align: right;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
  .dl-horizontal dd {
    margin-left: 180px;
  }
}
abbr[title],
abbr[data-original-title] {
  cursor: help;
  border-bottom: 1px dotted #777777;
}
.initialism {
  font-size: 90%;
  text-transform: uppercase;
}
blockquote {
  padding: 9px 18px;
  margin: 0 0 18px;
  font-size: inherit;
  border-left: 5px solid #eeeeee;
}
blockquote p:last-child,
blockquote ul:last-child,
blockquote ol:last-child {
  margin-bottom: 0;
}
blockquote footer,
blockquote small,
blockquote .small {
  display: block;
  font-size: 80%;
  line-height: 1.42857143;
  color: #777777;
}
blockquote footer:before,
blockquote small:before,
blockquote .small:before {
  content: '\2014 \00A0';
}
.blockquote-reverse,
blockquote.pull-right {
  padding-right: 15px;
  padding-left: 0;
  border-right: 5px solid #eeeeee;
  border-left: 0;
  text-align: right;
}
.blockquote-reverse footer:before,
blockquote.pull-right footer:before,
.blockquote-reverse small:before,
blockquote.pull-right small:before,
.blockquote-reverse .small:before,
blockquote.pull-right .small:before {
  content: '';
}
.blockquote-reverse footer:after,
blockquote.pull-right footer:after,
.blockquote-reverse small:after,
blockquote.pull-right small:after,
.blockquote-reverse .small:after,
blockquote.pull-right .small:after {
  content: '\00A0 \2014';
}
address {
  margin-bottom: 18px;
  font-style: normal;
  line-height: 1.42857143;
}
code,
kbd,
pre,
samp {
  font-family: monospace;
}
code {
  padding: 2px 4px;
  font-size: 90%;
  color: #c7254e;
  background-color: #f9f2f4;
  border-radius: 2px;
}
kbd {
  padding: 2px 4px;
  font-size: 90%;
  color: #888;
  background-color: transparent;
  border-radius: 1px;
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.25);
}
kbd kbd {
  padding: 0;
  font-size: 100%;
  font-weight: bold;
  box-shadow: none;
}
pre {
  display: block;
  padding: 8.5px;
  margin: 0 0 9px;
  font-size: 12px;
  line-height: 1.42857143;
  word-break: break-all;
  word-wrap: break-word;
  color: #333333;
  background-color: #f5f5f5;
  border: 1px solid #ccc;
  border-radius: 2px;
}
pre code {
  padding: 0;
  font-size: inherit;
  color: inherit;
  white-space: pre-wrap;
  background-color: transparent;
  border-radius: 0;
}
.pre-scrollable {
  max-height: 340px;
  overflow-y: scroll;
}
.container {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
@media (min-width: 768px) {
  .container {
    width: 768px;
  }
}
@media (min-width: 992px) {
  .container {
    width: 940px;
  }
}
@media (min-width: 1200px) {
  .container {
    width: 1140px;
  }
}
.container-fluid {
  margin-right: auto;
  margin-left: auto;
  padding-left: 0px;
  padding-right: 0px;
}
.row {
  margin-left: 0px;
  margin-right: 0px;
}
.col-xs-1, .col-sm-1, .col-md-1, .col-lg-1, .col-xs-2, .col-sm-2, .col-md-2, .col-lg-2, .col-xs-3, .col-sm-3, .col-md-3, .col-lg-3, .col-xs-4, .col-sm-4, .col-md-4, .col-lg-4, .col-xs-5, .col-sm-5, .col-md-5, .col-lg-5, .col-xs-6, .col-sm-6, .col-md-6, .col-lg-6, .col-xs-7, .col-sm-7, .col-md-7, .col-lg-7, .col-xs-8, .col-sm-8, .col-md-8, .col-lg-8, .col-xs-9, .col-sm-9, .col-md-9, .col-lg-9, .col-xs-10, .col-sm-10, .col-md-10, .col-lg-10, .col-xs-11, .col-sm-11, .col-md-11, .col-lg-11, .col-xs-12, .col-sm-12, .col-md-12, .col-lg-12 {
  position: relative;
  min-height: 1px;
  padding-left: 0px;
  padding-right: 0px;
}
.col-xs-1, .col-xs-2, .col-xs-3, .col-xs-4, .col-xs-5, .col-xs-6, .col-xs-7, .col-xs-8, .col-xs-9, .col-xs-10, .col-xs-11, .col-xs-12 {
  float: left;
}
.col-xs-12 {
  width: 100%;
}
.col-xs-11 {
  width: 91.66666667%;
}
.col-xs-10 {
  width: 83.33333333%;
}
.col-xs-9 {
  width: 75%;
}
.col-xs-8 {
  width: 66.66666667%;
}
.col-xs-7 {
  width: 58.33333333%;
}
.col-xs-6 {
  width: 50%;
}
.col-xs-5 {
  width: 41.66666667%;
}
.col-xs-4 {
  width: 33.33333333%;
}
.col-xs-3 {
  width: 25%;
}
.col-xs-2 {
  width: 16.66666667%;
}
.col-xs-1 {
  width: 8.33333333%;
}
.col-xs-pull-12 {
  right: 100%;
}
.col-xs-pull-11 {
  right: 91.66666667%;
}
.col-xs-pull-10 {
  right: 83.33333333%;
}
.col-xs-pull-9 {
  right: 75%;
}
.col-xs-pull-8 {
  right: 66.66666667%;
}
.col-xs-pull-7 {
  right: 58.33333333%;
}
.col-xs-pull-6 {
  right: 50%;
}
.col-xs-pull-5 {
  right: 41.66666667%;
}
.col-xs-pull-4 {
  right: 33.33333333%;
}
.col-xs-pull-3 {
  right: 25%;
}
.col-xs-pull-2 {
  right: 16.66666667%;
}
.col-xs-pull-1 {
  right: 8.33333333%;
}
.col-xs-pull-0 {
  right: auto;
}
.col-xs-push-12 {
  left: 100%;
}
.col-xs-push-11 {
  left: 91.66666667%;
}
.col-xs-push-10 {
  left: 83.33333333%;
}
.col-xs-push-9 {
  left: 75%;
}
.col-xs-push-8 {
  left: 66.66666667%;
}
.col-xs-push-7 {
  left: 58.33333333%;
}
.col-xs-push-6 {
  left: 50%;
}
.col-xs-push-5 {
  left: 41.66666667%;
}
.col-xs-push-4 {
  left: 33.33333333%;
}
.col-xs-push-3 {
  left: 25%;
}
.col-xs-push-2 {
  left: 16.66666667%;
}
.col-xs-push-1 {
  left: 8.33333333%;
}
.col-xs-push-0 {
  left: auto;
}
.col-xs-offset-12 {
  margin-left: 100%;
}
.col-xs-offset-11 {
  margin-left: 91.66666667%;
}
.col-xs-offset-10 {
  margin-left: 83.33333333%;
}
.col-xs-offset-9 {
  margin-left: 75%;
}
.col-xs-offset-8 {
  margin-left: 66.66666667%;
}
.col-xs-offset-7 {
  margin-left: 58.33333333%;
}
.col-xs-offset-6 {
  margin-left: 50%;
}
.col-xs-offset-5 {
  margin-left: 41.66666667%;
}
.col-xs-offset-4 {
  margin-left: 33.33333333%;
}
.col-xs-offset-3 {
  margin-left: 25%;
}
.col-xs-offset-2 {
  margin-left: 16.66666667%;
}
.col-xs-offset-1 {
  margin-left: 8.33333333%;
}
.col-xs-offset-0 {
  margin-left: 0%;
}
@media (min-width: 768px) {
  .col-sm-1, .col-sm-2, .col-sm-3, .col-sm-4, .col-sm-5, .col-sm-6, .col-sm-7, .col-sm-8, .col-sm-9, .col-sm-10, .col-sm-11, .col-sm-12 {
    float: left;
  }
  .col-sm-12 {
    width: 100%;
  }
  .col-sm-11 {
    width: 91.66666667%;
  }
  .col-sm-10 {
    width: 83.33333333%;
  }
  .col-sm-9 {
    width: 75%;
  }
  .col-sm-8 {
    width: 66.66666667%;
  }
  .col-sm-7 {
    width: 58.33333333%;
  }
  .col-sm-6 {
    width: 50%;
  }
  .col-sm-5 {
    width: 41.66666667%;
  }
  .col-sm-4 {
    width: 33.33333333%;
  }
  .col-sm-3 {
    width: 25%;
  }
  .col-sm-2 {
    width: 16.66666667%;
  }
  .col-sm-1 {
    width: 8.33333333%;
  }
  .col-sm-pull-12 {
    right: 100%;
  }
  .col-sm-pull-11 {
    right: 91.66666667%;
  }
  .col-sm-pull-10 {
    right: 83.33333333%;
  }
  .col-sm-pull-9 {
    right: 75%;
  }
  .col-sm-pull-8 {
    right: 66.66666667%;
  }
  .col-sm-pull-7 {
    right: 58.33333333%;
  }
  .col-sm-pull-6 {
    right: 50%;
  }
  .col-sm-pull-5 {
    right: 41.66666667%;
  }
  .col-sm-pull-4 {
    right: 33.33333333%;
  }
  .col-sm-pull-3 {
    right: 25%;
  }
  .col-sm-pull-2 {
    right: 16.66666667%;
  }
  .col-sm-pull-1 {
    right: 8.33333333%;
  }
  .col-sm-pull-0 {
    right: auto;
  }
  .col-sm-push-12 {
    left: 100%;
  }
  .col-sm-push-11 {
    left: 91.66666667%;
  }
  .col-sm-push-10 {
    left: 83.33333333%;
  }
  .col-sm-push-9 {
    left: 75%;
  }
  .col-sm-push-8 {
    left: 66.66666667%;
  }
  .col-sm-push-7 {
    left: 58.33333333%;
  }
  .col-sm-push-6 {
    left: 50%;
  }
  .col-sm-push-5 {
    left: 41.66666667%;
  }
  .col-sm-push-4 {
    left: 33.33333333%;
  }
  .col-sm-push-3 {
    left: 25%;
  }
  .col-sm-push-2 {
    left: 16.66666667%;
  }
  .col-sm-push-1 {
    left: 8.33333333%;
  }
  .col-sm-push-0 {
    left: auto;
  }
  .col-sm-offset-12 {
    margin-left: 100%;
  }
  .col-sm-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-sm-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-sm-offset-9 {
    margin-left: 75%;
  }
  .col-sm-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-sm-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-sm-offset-6 {
    margin-left: 50%;
  }
  .col-sm-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-sm-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-sm-offset-3 {
    margin-left: 25%;
  }
  .col-sm-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-sm-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-sm-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 992px) {
  .col-md-1, .col-md-2, .col-md-3, .col-md-4, .col-md-5, .col-md-6, .col-md-7, .col-md-8, .col-md-9, .col-md-10, .col-md-11, .col-md-12 {
    float: left;
  }
  .col-md-12 {
    width: 100%;
  }
  .col-md-11 {
    width: 91.66666667%;
  }
  .col-md-10 {
    width: 83.33333333%;
  }
  .col-md-9 {
    width: 75%;
  }
  .col-md-8 {
    width: 66.66666667%;
  }
  .col-md-7 {
    width: 58.33333333%;
  }
  .col-md-6 {
    width: 50%;
  }
  .col-md-5 {
    width: 41.66666667%;
  }
  .col-md-4 {
    width: 33.33333333%;
  }
  .col-md-3 {
    width: 25%;
  }
  .col-md-2 {
    width: 16.66666667%;
  }
  .col-md-1 {
    width: 8.33333333%;
  }
  .col-md-pull-12 {
    right: 100%;
  }
  .col-md-pull-11 {
    right: 91.66666667%;
  }
  .col-md-pull-10 {
    right: 83.33333333%;
  }
  .col-md-pull-9 {
    right: 75%;
  }
  .col-md-pull-8 {
    right: 66.66666667%;
  }
  .col-md-pull-7 {
    right: 58.33333333%;
  }
  .col-md-pull-6 {
    right: 50%;
  }
  .col-md-pull-5 {
    right: 41.66666667%;
  }
  .col-md-pull-4 {
    right: 33.33333333%;
  }
  .col-md-pull-3 {
    right: 25%;
  }
  .col-md-pull-2 {
    right: 16.66666667%;
  }
  .col-md-pull-1 {
    right: 8.33333333%;
  }
  .col-md-pull-0 {
    right: auto;
  }
  .col-md-push-12 {
    left: 100%;
  }
  .col-md-push-11 {
    left: 91.66666667%;
  }
  .col-md-push-10 {
    left: 83.33333333%;
  }
  .col-md-push-9 {
    left: 75%;
  }
  .col-md-push-8 {
    left: 66.66666667%;
  }
  .col-md-push-7 {
    left: 58.33333333%;
  }
  .col-md-push-6 {
    left: 50%;
  }
  .col-md-push-5 {
    left: 41.66666667%;
  }
  .col-md-push-4 {
    left: 33.33333333%;
  }
  .col-md-push-3 {
    left: 25%;
  }
  .col-md-push-2 {
    left: 16.66666667%;
  }
  .col-md-push-1 {
    left: 8.33333333%;
  }
  .col-md-push-0 {
    left: auto;
  }
  .col-md-offset-12 {
    margin-left: 100%;
  }
  .col-md-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-md-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-md-offset-9 {
    margin-left: 75%;
  }
  .col-md-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-md-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-md-offset-6 {
    margin-left: 50%;
  }
  .col-md-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-md-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-md-offset-3 {
    margin-left: 25%;
  }
  .col-md-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-md-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-md-offset-0 {
    margin-left: 0%;
  }
}
@media (min-width: 1200px) {
  .col-lg-1, .col-lg-2, .col-lg-3, .col-lg-4, .col-lg-5, .col-lg-6, .col-lg-7, .col-lg-8, .col-lg-9, .col-lg-10, .col-lg-11, .col-lg-12 {
    float: left;
  }
  .col-lg-12 {
    width: 100%;
  }
  .col-lg-11 {
    width: 91.66666667%;
  }
  .col-lg-10 {
    width: 83.33333333%;
  }
  .col-lg-9 {
    width: 75%;
  }
  .col-lg-8 {
    width: 66.66666667%;
  }
  .col-lg-7 {
    width: 58.33333333%;
  }
  .col-lg-6 {
    width: 50%;
  }
  .col-lg-5 {
    width: 41.66666667%;
  }
  .col-lg-4 {
    width: 33.33333333%;
  }
  .col-lg-3 {
    width: 25%;
  }
  .col-lg-2 {
    width: 16.66666667%;
  }
  .col-lg-1 {
    width: 8.33333333%;
  }
  .col-lg-pull-12 {
    right: 100%;
  }
  .col-lg-pull-11 {
    right: 91.66666667%;
  }
  .col-lg-pull-10 {
    right: 83.33333333%;
  }
  .col-lg-pull-9 {
    right: 75%;
  }
  .col-lg-pull-8 {
    right: 66.66666667%;
  }
  .col-lg-pull-7 {
    right: 58.33333333%;
  }
  .col-lg-pull-6 {
    right: 50%;
  }
  .col-lg-pull-5 {
    right: 41.66666667%;
  }
  .col-lg-pull-4 {
    right: 33.33333333%;
  }
  .col-lg-pull-3 {
    right: 25%;
  }
  .col-lg-pull-2 {
    right: 16.66666667%;
  }
  .col-lg-pull-1 {
    right: 8.33333333%;
  }
  .col-lg-pull-0 {
    right: auto;
  }
  .col-lg-push-12 {
    left: 100%;
  }
  .col-lg-push-11 {
    left: 91.66666667%;
  }
  .col-lg-push-10 {
    left: 83.33333333%;
  }
  .col-lg-push-9 {
    left: 75%;
  }
  .col-lg-push-8 {
    left: 66.66666667%;
  }
  .col-lg-push-7 {
    left: 58.33333333%;
  }
  .col-lg-push-6 {
    left: 50%;
  }
  .col-lg-push-5 {
    left: 41.66666667%;
  }
  .col-lg-push-4 {
    left: 33.33333333%;
  }
  .col-lg-push-3 {
    left: 25%;
  }
  .col-lg-push-2 {
    left: 16.66666667%;
  }
  .col-lg-push-1 {
    left: 8.33333333%;
  }
  .col-lg-push-0 {
    left: auto;
  }
  .col-lg-offset-12 {
    margin-left: 100%;
  }
  .col-lg-offset-11 {
    margin-left: 91.66666667%;
  }
  .col-lg-offset-10 {
    margin-left: 83.33333333%;
  }
  .col-lg-offset-9 {
    margin-left: 75%;
  }
  .col-lg-offset-8 {
    margin-left: 66.66666667%;
  }
  .col-lg-offset-7 {
    margin-left: 58.33333333%;
  }
  .col-lg-offset-6 {
    margin-left: 50%;
  }
  .col-lg-offset-5 {
    margin-left: 41.66666667%;
  }
  .col-lg-offset-4 {
    margin-left: 33.33333333%;
  }
  .col-lg-offset-3 {
    margin-left: 25%;
  }
  .col-lg-offset-2 {
    margin-left: 16.66666667%;
  }
  .col-lg-offset-1 {
    margin-left: 8.33333333%;
  }
  .col-lg-offset-0 {
    margin-left: 0%;
  }
}
table {
  background-color: transparent;
}
caption {
  padding-top: 8px;
  padding-bottom: 8px;
  color: #777777;
  text-align: left;
}
th {
  text-align: left;
}
.table {
  width: 100%;
  max-width: 100%;
  margin-bottom: 18px;
}
.table > thead > tr > th,
.table > tbody > tr > th,
.table > tfoot > tr > th,
.table > thead > tr > td,
.table > tbody > tr > td,
.table > tfoot > tr > td {
  padding: 8px;
  line-height: 1.42857143;
  vertical-align: top;
  border-top: 1px solid #ddd;
}
.table > thead > tr > th {
  vertical-align: bottom;
  border-bottom: 2px solid #ddd;
}
.table > caption + thead > tr:first-child > th,
.table > colgroup + thead > tr:first-child > th,
.table > thead:first-child > tr:first-child > th,
.table > caption + thead > tr:first-child > td,
.table > colgroup + thead > tr:first-child > td,
.table > thead:first-child > tr:first-child > td {
  border-top: 0;
}
.table > tbody + tbody {
  border-top: 2px solid #ddd;
}
.table .table {
  background-color: #fff;
}
.table-condensed > thead > tr > th,
.table-condensed > tbody > tr > th,
.table-condensed > tfoot > tr > th,
.table-condensed > thead > tr > td,
.table-condensed > tbody > tr > td,
.table-condensed > tfoot > tr > td {
  padding: 5px;
}
.table-bordered {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > tbody > tr > th,
.table-bordered > tfoot > tr > th,
.table-bordered > thead > tr > td,
.table-bordered > tbody > tr > td,
.table-bordered > tfoot > tr > td {
  border: 1px solid #ddd;
}
.table-bordered > thead > tr > th,
.table-bordered > thead > tr > td {
  border-bottom-width: 2px;
}
.table-striped > tbody > tr:nth-of-type(odd) {
  background-color: #f9f9f9;
}
.table-hover > tbody > tr:hover {
  background-color: #f5f5f5;
}
table col[class*="col-"] {
  position: static;
  float: none;
  display: table-column;
}
table td[class*="col-"],
table th[class*="col-"] {
  position: static;
  float: none;
  display: table-cell;
}
.table > thead > tr > td.active,
.table > tbody > tr > td.active,
.table > tfoot > tr > td.active,
.table > thead > tr > th.active,
.table > tbody > tr > th.active,
.table > tfoot > tr > th.active,
.table > thead > tr.active > td,
.table > tbody > tr.active > td,
.table > tfoot > tr.active > td,
.table > thead > tr.active > th,
.table > tbody > tr.active > th,
.table > tfoot > tr.active > th {
  background-color: #f5f5f5;
}
.table-hover > tbody > tr > td.active:hover,
.table-hover > tbody > tr > th.active:hover,
.table-hover > tbody > tr.active:hover > td,
.table-hover > tbody > tr:hover > .active,
.table-hover > tbody > tr.active:hover > th {
  background-color: #e8e8e8;
}
.table > thead > tr > td.success,
.table > tbody > tr > td.success,
.table > tfoot > tr > td.success,
.table > thead > tr > th.success,
.table > tbody > tr > th.success,
.table > tfoot > tr > th.success,
.table > thead > tr.success > td,
.table > tbody > tr.success > td,
.table > tfoot > tr.success > td,
.table > thead > tr.success > th,
.table > tbody > tr.success > th,
.table > tfoot > tr.success > th {
  background-color: #dff0d8;
}
.table-hover > tbody > tr > td.success:hover,
.table-hover > tbody > tr > th.success:hover,
.table-hover > tbody > tr.success:hover > td,
.table-hover > tbody > tr:hover > .success,
.table-hover > tbody > tr.success:hover > th {
  background-color: #d0e9c6;
}
.table > thead > tr > td.info,
.table > tbody > tr > td.info,
.table > tfoot > tr > td.info,
.table > thead > tr > th.info,
.table > tbody > tr > th.info,
.table > tfoot > tr > th.info,
.table > thead > tr.info > td,
.table > tbody > tr.info > td,
.table > tfoot > tr.info > td,
.table > thead > tr.info > th,
.table > tbody > tr.info > th,
.table > tfoot > tr.info > th {
  background-color: #d9edf7;
}
.table-hover > tbody > tr > td.info:hover,
.table-hover > tbody > tr > th.info:hover,
.table-hover > tbody > tr.info:hover > td,
.table-hover > tbody > tr:hover > .info,
.table-hover > tbody > tr.info:hover > th {
  background-color: #c4e3f3;
}
.table > thead > tr > td.warning,
.table > tbody > tr > td.warning,
.table > tfoot > tr > td.warning,
.table > thead > tr > th.warning,
.table > tbody > tr > th.warning,
.table > tfoot > tr > th.warning,
.table > thead > tr.warning > td,
.table > tbody > tr.warning > td,
.table > tfoot > tr.warning > td,
.table > thead > tr.warning > th,
.table > tbody > tr.warning > th,
.table > tfoot > tr.warning > th {
  background-color: #fcf8e3;
}
.table-hover > tbody > tr > td.warning:hover,
.table-hover > tbody > tr > th.warning:hover,
.table-hover > tbody > tr.warning:hover > td,
.table-hover > tbody > tr:hover > .warning,
.table-hover > tbody > tr.warning:hover > th {
  background-color: #faf2cc;
}
.table > thead > tr > td.danger,
.table > tbody > tr > td.danger,
.table > tfoot > tr > td.danger,
.table > thead > tr > th.danger,
.table > tbody > tr > th.danger,
.table > tfoot > tr > th.danger,
.table > thead > tr.danger > td,
.table > tbody > tr.danger > td,
.table > tfoot > tr.danger > td,
.table > thead > tr.danger > th,
.table > tbody > tr.danger > th,
.table > tfoot > tr.danger > th {
  background-color: #f2dede;
}
.table-hover > tbody > tr > td.danger:hover,
.table-hover > tbody > tr > th.danger:hover,
.table-hover > tbody > tr.danger:hover > td,
.table-hover > tbody > tr:hover > .danger,
.table-hover > tbody > tr.danger:hover > th {
  background-color: #ebcccc;
}
.table-responsive {
  overflow-x: auto;
  min-height: 0.01%;
}
@media screen and (max-width: 767px) {
  .table-responsive {
    width: 100%;
    margin-bottom: 13.5px;
    overflow-y: hidden;
    -ms-overflow-style: -ms-autohiding-scrollbar;
    border: 1px solid #ddd;
  }
  .table-responsive > .table {
    margin-bottom: 0;
  }
  .table-responsive > .table > thead > tr > th,
  .table-responsive > .table > tbody > tr > th,
  .table-responsive > .table > tfoot > tr > th,
  .table-responsive > .table > thead > tr > td,
  .table-responsive > .table > tbody > tr > td,
  .table-responsive > .table > tfoot > tr > td {
    white-space: nowrap;
  }
  .table-responsive > .table-bordered {
    border: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:first-child,
  .table-responsive > .table-bordered > tbody > tr > th:first-child,
  .table-responsive > .table-bordered > tfoot > tr > th:first-child,
  .table-responsive > .table-bordered > thead > tr > td:first-child,
  .table-responsive > .table-bordered > tbody > tr > td:first-child,
  .table-responsive > .table-bordered > tfoot > tr > td:first-child {
    border-left: 0;
  }
  .table-responsive > .table-bordered > thead > tr > th:last-child,
  .table-responsive > .table-bordered > tbody > tr > th:last-child,
  .table-responsive > .table-bordered > tfoot > tr > th:last-child,
  .table-responsive > .table-bordered > thead > tr > td:last-child,
  .table-responsive > .table-bordered > tbody > tr > td:last-child,
  .table-responsive > .table-bordered > tfoot > tr > td:last-child {
    border-right: 0;
  }
  .table-responsive > .table-bordered > tbody > tr:last-child > th,
  .table-responsive > .table-bordered > tfoot > tr:last-child > th,
  .table-responsive > .table-bordered > tbody > tr:last-child > td,
  .table-responsive > .table-bordered > tfoot > tr:last-child > td {
    border-bottom: 0;
  }
}
fieldset {
  padding: 0;
  margin: 0;
  border: 0;
  min-width: 0;
}
legend {
  display: block;
  width: 100%;
  padding: 0;
  margin-bottom: 18px;
  font-size: 19.5px;
  line-height: inherit;
  color: #333333;
  border: 0;
  border-bottom: 1px solid #e5e5e5;
}
label {
  display: inline-block;
  max-width: 100%;
  margin-bottom: 5px;
  font-weight: bold;
}
input[type="search"] {
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}
input[type="radio"],
input[type="checkbox"] {
  margin: 4px 0 0;
  margin-top: 1px \9;
  line-height: normal;
}
input[type="file"] {
  display: block;
}
input[type="range"] {
  display: block;
  width: 100%;
}
select[multiple],
select[size] {
  height: auto;
}
input[type="file"]:focus,
input[type="radio"]:focus,
input[type="checkbox"]:focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
output {
  display: block;
  padding-top: 7px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
}
.form-control {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
}
.form-control:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.form-control::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.form-control:-ms-input-placeholder {
  color: #999;
}
.form-control::-webkit-input-placeholder {
  color: #999;
}
.form-control::-ms-expand {
  border: 0;
  background-color: transparent;
}
.form-control[disabled],
.form-control[readonly],
fieldset[disabled] .form-control {
  background-color: #eeeeee;
  opacity: 1;
}
.form-control[disabled],
fieldset[disabled] .form-control {
  cursor: not-allowed;
}
textarea.form-control {
  height: auto;
}
input[type="search"] {
  -webkit-appearance: none;
}
@media screen and (-webkit-min-device-pixel-ratio: 0) {
  input[type="date"].form-control,
  input[type="time"].form-control,
  input[type="datetime-local"].form-control,
  input[type="month"].form-control {
    line-height: 32px;
  }
  input[type="date"].input-sm,
  input[type="time"].input-sm,
  input[type="datetime-local"].input-sm,
  input[type="month"].input-sm,
  .input-group-sm input[type="date"],
  .input-group-sm input[type="time"],
  .input-group-sm input[type="datetime-local"],
  .input-group-sm input[type="month"] {
    line-height: 30px;
  }
  input[type="date"].input-lg,
  input[type="time"].input-lg,
  input[type="datetime-local"].input-lg,
  input[type="month"].input-lg,
  .input-group-lg input[type="date"],
  .input-group-lg input[type="time"],
  .input-group-lg input[type="datetime-local"],
  .input-group-lg input[type="month"] {
    line-height: 45px;
  }
}
.form-group {
  margin-bottom: 15px;
}
.radio,
.checkbox {
  position: relative;
  display: block;
  margin-top: 10px;
  margin-bottom: 10px;
}
.radio label,
.checkbox label {
  min-height: 18px;
  padding-left: 20px;
  margin-bottom: 0;
  font-weight: normal;
  cursor: pointer;
}
.radio input[type="radio"],
.radio-inline input[type="radio"],
.checkbox input[type="checkbox"],
.checkbox-inline input[type="checkbox"] {
  position: absolute;
  margin-left: -20px;
  margin-top: 4px \9;
}
.radio + .radio,
.checkbox + .checkbox {
  margin-top: -5px;
}
.radio-inline,
.checkbox-inline {
  position: relative;
  display: inline-block;
  padding-left: 20px;
  margin-bottom: 0;
  vertical-align: middle;
  font-weight: normal;
  cursor: pointer;
}
.radio-inline + .radio-inline,
.checkbox-inline + .checkbox-inline {
  margin-top: 0;
  margin-left: 10px;
}
input[type="radio"][disabled],
input[type="checkbox"][disabled],
input[type="radio"].disabled,
input[type="checkbox"].disabled,
fieldset[disabled] input[type="radio"],
fieldset[disabled] input[type="checkbox"] {
  cursor: not-allowed;
}
.radio-inline.disabled,
.checkbox-inline.disabled,
fieldset[disabled] .radio-inline,
fieldset[disabled] .checkbox-inline {
  cursor: not-allowed;
}
.radio.disabled label,
.checkbox.disabled label,
fieldset[disabled] .radio label,
fieldset[disabled] .checkbox label {
  cursor: not-allowed;
}
.form-control-static {
  padding-top: 7px;
  padding-bottom: 7px;
  margin-bottom: 0;
  min-height: 31px;
}
.form-control-static.input-lg,
.form-control-static.input-sm {
  padding-left: 0;
  padding-right: 0;
}
.input-sm {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-sm {
  height: 30px;
  line-height: 30px;
}
textarea.input-sm,
select[multiple].input-sm {
  height: auto;
}
.form-group-sm .form-control {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.form-group-sm select.form-control {
  height: 30px;
  line-height: 30px;
}
.form-group-sm textarea.form-control,
.form-group-sm select[multiple].form-control {
  height: auto;
}
.form-group-sm .form-control-static {
  height: 30px;
  min-height: 30px;
  padding: 6px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.input-lg {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-lg {
  height: 45px;
  line-height: 45px;
}
textarea.input-lg,
select[multiple].input-lg {
  height: auto;
}
.form-group-lg .form-control {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.form-group-lg select.form-control {
  height: 45px;
  line-height: 45px;
}
.form-group-lg textarea.form-control,
.form-group-lg select[multiple].form-control {
  height: auto;
}
.form-group-lg .form-control-static {
  height: 45px;
  min-height: 35px;
  padding: 11px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.has-feedback {
  position: relative;
}
.has-feedback .form-control {
  padding-right: 40px;
}
.form-control-feedback {
  position: absolute;
  top: 0;
  right: 0;
  z-index: 2;
  display: block;
  width: 32px;
  height: 32px;
  line-height: 32px;
  text-align: center;
  pointer-events: none;
}
.input-lg + .form-control-feedback,
.input-group-lg + .form-control-feedback,
.form-group-lg .form-control + .form-control-feedback {
  width: 45px;
  height: 45px;
  line-height: 45px;
}
.input-sm + .form-control-feedback,
.input-group-sm + .form-control-feedback,
.form-group-sm .form-control + .form-control-feedback {
  width: 30px;
  height: 30px;
  line-height: 30px;
}
.has-success .help-block,
.has-success .control-label,
.has-success .radio,
.has-success .checkbox,
.has-success .radio-inline,
.has-success .checkbox-inline,
.has-success.radio label,
.has-success.checkbox label,
.has-success.radio-inline label,
.has-success.checkbox-inline label {
  color: #3c763d;
}
.has-success .form-control {
  border-color: #3c763d;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-success .form-control:focus {
  border-color: #2b542c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #67b168;
}
.has-success .input-group-addon {
  color: #3c763d;
  border-color: #3c763d;
  background-color: #dff0d8;
}
.has-success .form-control-feedback {
  color: #3c763d;
}
.has-warning .help-block,
.has-warning .control-label,
.has-warning .radio,
.has-warning .checkbox,
.has-warning .radio-inline,
.has-warning .checkbox-inline,
.has-warning.radio label,
.has-warning.checkbox label,
.has-warning.radio-inline label,
.has-warning.checkbox-inline label {
  color: #8a6d3b;
}
.has-warning .form-control {
  border-color: #8a6d3b;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-warning .form-control:focus {
  border-color: #66512c;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #c0a16b;
}
.has-warning .input-group-addon {
  color: #8a6d3b;
  border-color: #8a6d3b;
  background-color: #fcf8e3;
}
.has-warning .form-control-feedback {
  color: #8a6d3b;
}
.has-error .help-block,
.has-error .control-label,
.has-error .radio,
.has-error .checkbox,
.has-error .radio-inline,
.has-error .checkbox-inline,
.has-error.radio label,
.has-error.checkbox label,
.has-error.radio-inline label,
.has-error.checkbox-inline label {
  color: #a94442;
}
.has-error .form-control {
  border-color: #a94442;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
}
.has-error .form-control:focus {
  border-color: #843534;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075), 0 0 6px #ce8483;
}
.has-error .input-group-addon {
  color: #a94442;
  border-color: #a94442;
  background-color: #f2dede;
}
.has-error .form-control-feedback {
  color: #a94442;
}
.has-feedback label ~ .form-control-feedback {
  top: 23px;
}
.has-feedback label.sr-only ~ .form-control-feedback {
  top: 0;
}
.help-block {
  display: block;
  margin-top: 5px;
  margin-bottom: 10px;
  color: #404040;
}
@media (min-width: 768px) {
  .form-inline .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .form-inline .form-control-static {
    display: inline-block;
  }
  .form-inline .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .form-inline .input-group .input-group-addon,
  .form-inline .input-group .input-group-btn,
  .form-inline .input-group .form-control {
    width: auto;
  }
  .form-inline .input-group > .form-control {
    width: 100%;
  }
  .form-inline .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio,
  .form-inline .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .form-inline .radio label,
  .form-inline .checkbox label {
    padding-left: 0;
  }
  .form-inline .radio input[type="radio"],
  .form-inline .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .form-inline .has-feedback .form-control-feedback {
    top: 0;
  }
}
.form-horizontal .radio,
.form-horizontal .checkbox,
.form-horizontal .radio-inline,
.form-horizontal .checkbox-inline {
  margin-top: 0;
  margin-bottom: 0;
  padding-top: 7px;
}
.form-horizontal .radio,
.form-horizontal .checkbox {
  min-height: 25px;
}
.form-horizontal .form-group {
  margin-left: 0px;
  margin-right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .control-label {
    text-align: right;
    margin-bottom: 0;
    padding-top: 7px;
  }
}
.form-horizontal .has-feedback .form-control-feedback {
  right: 0px;
}
@media (min-width: 768px) {
  .form-horizontal .form-group-lg .control-label {
    padding-top: 11px;
    font-size: 17px;
  }
}
@media (min-width: 768px) {
  .form-horizontal .form-group-sm .control-label {
    padding-top: 6px;
    font-size: 12px;
  }
}
.btn {
  display: inline-block;
  margin-bottom: 0;
  font-weight: normal;
  text-align: center;
  vertical-align: middle;
  touch-action: manipulation;
  cursor: pointer;
  background-image: none;
  border: 1px solid transparent;
  white-space: nowrap;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  border-radius: 2px;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.btn:focus,
.btn:active:focus,
.btn.active:focus,
.btn.focus,
.btn:active.focus,
.btn.active.focus {
  outline: 5px auto -webkit-focus-ring-color;
  outline-offset: -2px;
}
.btn:hover,
.btn:focus,
.btn.focus {
  color: #333;
  text-decoration: none;
}
.btn:active,
.btn.active {
  outline: 0;
  background-image: none;
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn.disabled,
.btn[disabled],
fieldset[disabled] .btn {
  cursor: not-allowed;
  opacity: 0.65;
  filter: alpha(opacity=65);
  -webkit-box-shadow: none;
  box-shadow: none;
}
a.btn.disabled,
fieldset[disabled] a.btn {
  pointer-events: none;
}
.btn-default {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.btn-default:focus,
.btn-default.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.btn-default:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.btn-default:active:hover,
.btn-default.active:hover,
.open > .dropdown-toggle.btn-default:hover,
.btn-default:active:focus,
.btn-default.active:focus,
.open > .dropdown-toggle.btn-default:focus,
.btn-default:active.focus,
.btn-default.active.focus,
.open > .dropdown-toggle.btn-default.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.btn-default:active,
.btn-default.active,
.open > .dropdown-toggle.btn-default {
  background-image: none;
}
.btn-default.disabled:hover,
.btn-default[disabled]:hover,
fieldset[disabled] .btn-default:hover,
.btn-default.disabled:focus,
.btn-default[disabled]:focus,
fieldset[disabled] .btn-default:focus,
.btn-default.disabled.focus,
.btn-default[disabled].focus,
fieldset[disabled] .btn-default.focus {
  background-color: #fff;
  border-color: #ccc;
}
.btn-default .badge {
  color: #fff;
  background-color: #333;
}
.btn-primary {
  color: #fff;
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary:focus,
.btn-primary.focus {
  color: #fff;
  background-color: #286090;
  border-color: #122b40;
}
.btn-primary:hover {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  color: #fff;
  background-color: #286090;
  border-color: #204d74;
}
.btn-primary:active:hover,
.btn-primary.active:hover,
.open > .dropdown-toggle.btn-primary:hover,
.btn-primary:active:focus,
.btn-primary.active:focus,
.open > .dropdown-toggle.btn-primary:focus,
.btn-primary:active.focus,
.btn-primary.active.focus,
.open > .dropdown-toggle.btn-primary.focus {
  color: #fff;
  background-color: #204d74;
  border-color: #122b40;
}
.btn-primary:active,
.btn-primary.active,
.open > .dropdown-toggle.btn-primary {
  background-image: none;
}
.btn-primary.disabled:hover,
.btn-primary[disabled]:hover,
fieldset[disabled] .btn-primary:hover,
.btn-primary.disabled:focus,
.btn-primary[disabled]:focus,
fieldset[disabled] .btn-primary:focus,
.btn-primary.disabled.focus,
.btn-primary[disabled].focus,
fieldset[disabled] .btn-primary.focus {
  background-color: #337ab7;
  border-color: #2e6da4;
}
.btn-primary .badge {
  color: #337ab7;
  background-color: #fff;
}
.btn-success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success:focus,
.btn-success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.btn-success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.btn-success:active:hover,
.btn-success.active:hover,
.open > .dropdown-toggle.btn-success:hover,
.btn-success:active:focus,
.btn-success.active:focus,
.open > .dropdown-toggle.btn-success:focus,
.btn-success:active.focus,
.btn-success.active.focus,
.open > .dropdown-toggle.btn-success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.btn-success:active,
.btn-success.active,
.open > .dropdown-toggle.btn-success {
  background-image: none;
}
.btn-success.disabled:hover,
.btn-success[disabled]:hover,
fieldset[disabled] .btn-success:hover,
.btn-success.disabled:focus,
.btn-success[disabled]:focus,
fieldset[disabled] .btn-success:focus,
.btn-success.disabled.focus,
.btn-success[disabled].focus,
fieldset[disabled] .btn-success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.btn-success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.btn-info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info:focus,
.btn-info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.btn-info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.btn-info:active:hover,
.btn-info.active:hover,
.open > .dropdown-toggle.btn-info:hover,
.btn-info:active:focus,
.btn-info.active:focus,
.open > .dropdown-toggle.btn-info:focus,
.btn-info:active.focus,
.btn-info.active.focus,
.open > .dropdown-toggle.btn-info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.btn-info:active,
.btn-info.active,
.open > .dropdown-toggle.btn-info {
  background-image: none;
}
.btn-info.disabled:hover,
.btn-info[disabled]:hover,
fieldset[disabled] .btn-info:hover,
.btn-info.disabled:focus,
.btn-info[disabled]:focus,
fieldset[disabled] .btn-info:focus,
.btn-info.disabled.focus,
.btn-info[disabled].focus,
fieldset[disabled] .btn-info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.btn-info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.btn-warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning:focus,
.btn-warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.btn-warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.btn-warning:active:hover,
.btn-warning.active:hover,
.open > .dropdown-toggle.btn-warning:hover,
.btn-warning:active:focus,
.btn-warning.active:focus,
.open > .dropdown-toggle.btn-warning:focus,
.btn-warning:active.focus,
.btn-warning.active.focus,
.open > .dropdown-toggle.btn-warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.btn-warning:active,
.btn-warning.active,
.open > .dropdown-toggle.btn-warning {
  background-image: none;
}
.btn-warning.disabled:hover,
.btn-warning[disabled]:hover,
fieldset[disabled] .btn-warning:hover,
.btn-warning.disabled:focus,
.btn-warning[disabled]:focus,
fieldset[disabled] .btn-warning:focus,
.btn-warning.disabled.focus,
.btn-warning[disabled].focus,
fieldset[disabled] .btn-warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.btn-warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.btn-danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger:focus,
.btn-danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.btn-danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.btn-danger:active:hover,
.btn-danger.active:hover,
.open > .dropdown-toggle.btn-danger:hover,
.btn-danger:active:focus,
.btn-danger.active:focus,
.open > .dropdown-toggle.btn-danger:focus,
.btn-danger:active.focus,
.btn-danger.active.focus,
.open > .dropdown-toggle.btn-danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.btn-danger:active,
.btn-danger.active,
.open > .dropdown-toggle.btn-danger {
  background-image: none;
}
.btn-danger.disabled:hover,
.btn-danger[disabled]:hover,
fieldset[disabled] .btn-danger:hover,
.btn-danger.disabled:focus,
.btn-danger[disabled]:focus,
fieldset[disabled] .btn-danger:focus,
.btn-danger.disabled.focus,
.btn-danger[disabled].focus,
fieldset[disabled] .btn-danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.btn-danger .badge {
  color: #d9534f;
  background-color: #fff;
}
.btn-link {
  color: #337ab7;
  font-weight: normal;
  border-radius: 0;
}
.btn-link,
.btn-link:active,
.btn-link.active,
.btn-link[disabled],
fieldset[disabled] .btn-link {
  background-color: transparent;
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn-link,
.btn-link:hover,
.btn-link:focus,
.btn-link:active {
  border-color: transparent;
}
.btn-link:hover,
.btn-link:focus {
  color: #23527c;
  text-decoration: underline;
  background-color: transparent;
}
.btn-link[disabled]:hover,
fieldset[disabled] .btn-link:hover,
.btn-link[disabled]:focus,
fieldset[disabled] .btn-link:focus {
  color: #777777;
  text-decoration: none;
}
.btn-lg,
.btn-group-lg > .btn {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
.btn-sm,
.btn-group-sm > .btn {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-xs,
.btn-group-xs > .btn {
  padding: 1px 5px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
.btn-block {
  display: block;
  width: 100%;
}
.btn-block + .btn-block {
  margin-top: 5px;
}
input[type="submit"].btn-block,
input[type="reset"].btn-block,
input[type="button"].btn-block {
  width: 100%;
}
.fade {
  opacity: 0;
  -webkit-transition: opacity 0.15s linear;
  -o-transition: opacity 0.15s linear;
  transition: opacity 0.15s linear;
}
.fade.in {
  opacity: 1;
}
.collapse {
  display: none;
}
.collapse.in {
  display: block;
}
tr.collapse.in {
  display: table-row;
}
tbody.collapse.in {
  display: table-row-group;
}
.collapsing {
  position: relative;
  height: 0;
  overflow: hidden;
  -webkit-transition-property: height, visibility;
  transition-property: height, visibility;
  -webkit-transition-duration: 0.35s;
  transition-duration: 0.35s;
  -webkit-transition-timing-function: ease;
  transition-timing-function: ease;
}
.caret {
  display: inline-block;
  width: 0;
  height: 0;
  margin-left: 2px;
  vertical-align: middle;
  border-top: 4px dashed;
  border-top: 4px solid \9;
  border-right: 4px solid transparent;
  border-left: 4px solid transparent;
}
.dropup,
.dropdown {
  position: relative;
}
.dropdown-toggle:focus {
  outline: 0;
}
.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  z-index: 1000;
  display: none;
  float: left;
  min-width: 160px;
  padding: 5px 0;
  margin: 2px 0 0;
  list-style: none;
  font-size: 13px;
  text-align: left;
  background-color: #fff;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.15);
  border-radius: 2px;
  -webkit-box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.175);
  background-clip: padding-box;
}
.dropdown-menu.pull-right {
  right: 0;
  left: auto;
}
.dropdown-menu .divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.dropdown-menu > li > a {
  display: block;
  padding: 3px 20px;
  clear: both;
  font-weight: normal;
  line-height: 1.42857143;
  color: #333333;
  white-space: nowrap;
}
.dropdown-menu > li > a:hover,
.dropdown-menu > li > a:focus {
  text-decoration: none;
  color: #262626;
  background-color: #f5f5f5;
}
.dropdown-menu > .active > a,
.dropdown-menu > .active > a:hover,
.dropdown-menu > .active > a:focus {
  color: #fff;
  text-decoration: none;
  outline: 0;
  background-color: #337ab7;
}
.dropdown-menu > .disabled > a,
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  color: #777777;
}
.dropdown-menu > .disabled > a:hover,
.dropdown-menu > .disabled > a:focus {
  text-decoration: none;
  background-color: transparent;
  background-image: none;
  filter: progid:DXImageTransform.Microsoft.gradient(enabled = false);
  cursor: not-allowed;
}
.open > .dropdown-menu {
  display: block;
}
.open > a {
  outline: 0;
}
.dropdown-menu-right {
  left: auto;
  right: 0;
}
.dropdown-menu-left {
  left: 0;
  right: auto;
}
.dropdown-header {
  display: block;
  padding: 3px 20px;
  font-size: 12px;
  line-height: 1.42857143;
  color: #777777;
  white-space: nowrap;
}
.dropdown-backdrop {
  position: fixed;
  left: 0;
  right: 0;
  bottom: 0;
  top: 0;
  z-index: 990;
}
.pull-right > .dropdown-menu {
  right: 0;
  left: auto;
}
.dropup .caret,
.navbar-fixed-bottom .dropdown .caret {
  border-top: 0;
  border-bottom: 4px dashed;
  border-bottom: 4px solid \9;
  content: "";
}
.dropup .dropdown-menu,
.navbar-fixed-bottom .dropdown .dropdown-menu {
  top: auto;
  bottom: 100%;
  margin-bottom: 2px;
}
@media (min-width: 541px) {
  .navbar-right .dropdown-menu {
    left: auto;
    right: 0;
  }
  .navbar-right .dropdown-menu-left {
    left: 0;
    right: auto;
  }
}
.btn-group,
.btn-group-vertical {
  position: relative;
  display: inline-block;
  vertical-align: middle;
}
.btn-group > .btn,
.btn-group-vertical > .btn {
  position: relative;
  float: left;
}
.btn-group > .btn:hover,
.btn-group-vertical > .btn:hover,
.btn-group > .btn:focus,
.btn-group-vertical > .btn:focus,
.btn-group > .btn:active,
.btn-group-vertical > .btn:active,
.btn-group > .btn.active,
.btn-group-vertical > .btn.active {
  z-index: 2;
}
.btn-group .btn + .btn,
.btn-group .btn + .btn-group,
.btn-group .btn-group + .btn,
.btn-group .btn-group + .btn-group {
  margin-left: -1px;
}
.btn-toolbar {
  margin-left: -5px;
}
.btn-toolbar .btn,
.btn-toolbar .btn-group,
.btn-toolbar .input-group {
  float: left;
}
.btn-toolbar > .btn,
.btn-toolbar > .btn-group,
.btn-toolbar > .input-group {
  margin-left: 5px;
}
.btn-group > .btn:not(:first-child):not(:last-child):not(.dropdown-toggle) {
  border-radius: 0;
}
.btn-group > .btn:first-child {
  margin-left: 0;
}
.btn-group > .btn:first-child:not(:last-child):not(.dropdown-toggle) {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn:last-child:not(:first-child),
.btn-group > .dropdown-toggle:not(:first-child) {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group > .btn-group {
  float: left;
}
.btn-group > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.btn-group > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.btn-group .dropdown-toggle:active,
.btn-group.open .dropdown-toggle {
  outline: 0;
}
.btn-group > .btn + .dropdown-toggle {
  padding-left: 8px;
  padding-right: 8px;
}
.btn-group > .btn-lg + .dropdown-toggle {
  padding-left: 12px;
  padding-right: 12px;
}
.btn-group.open .dropdown-toggle {
  -webkit-box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
  box-shadow: inset 0 3px 5px rgba(0, 0, 0, 0.125);
}
.btn-group.open .dropdown-toggle.btn-link {
  -webkit-box-shadow: none;
  box-shadow: none;
}
.btn .caret {
  margin-left: 0;
}
.btn-lg .caret {
  border-width: 5px 5px 0;
  border-bottom-width: 0;
}
.dropup .btn-lg .caret {
  border-width: 0 5px 5px;
}
.btn-group-vertical > .btn,
.btn-group-vertical > .btn-group,
.btn-group-vertical > .btn-group > .btn {
  display: block;
  float: none;
  width: 100%;
  max-width: 100%;
}
.btn-group-vertical > .btn-group > .btn {
  float: none;
}
.btn-group-vertical > .btn + .btn,
.btn-group-vertical > .btn + .btn-group,
.btn-group-vertical > .btn-group + .btn,
.btn-group-vertical > .btn-group + .btn-group {
  margin-top: -1px;
  margin-left: 0;
}
.btn-group-vertical > .btn:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.btn-group-vertical > .btn:first-child:not(:last-child) {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn:last-child:not(:first-child) {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
.btn-group-vertical > .btn-group:not(:first-child):not(:last-child) > .btn {
  border-radius: 0;
}
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .btn:last-child,
.btn-group-vertical > .btn-group:first-child:not(:last-child) > .dropdown-toggle {
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.btn-group-vertical > .btn-group:last-child:not(:first-child) > .btn:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.btn-group-justified {
  display: table;
  width: 100%;
  table-layout: fixed;
  border-collapse: separate;
}
.btn-group-justified > .btn,
.btn-group-justified > .btn-group {
  float: none;
  display: table-cell;
  width: 1%;
}
.btn-group-justified > .btn-group .btn {
  width: 100%;
}
.btn-group-justified > .btn-group .dropdown-menu {
  left: auto;
}
[data-toggle="buttons"] > .btn input[type="radio"],
[data-toggle="buttons"] > .btn-group > .btn input[type="radio"],
[data-toggle="buttons"] > .btn input[type="checkbox"],
[data-toggle="buttons"] > .btn-group > .btn input[type="checkbox"] {
  position: absolute;
  clip: rect(0, 0, 0, 0);
  pointer-events: none;
}
.input-group {
  position: relative;
  display: table;
  border-collapse: separate;
}
.input-group[class*="col-"] {
  float: none;
  padding-left: 0;
  padding-right: 0;
}
.input-group .form-control {
  position: relative;
  z-index: 2;
  float: left;
  width: 100%;
  margin-bottom: 0;
}
.input-group .form-control:focus {
  z-index: 3;
}
.input-group-lg > .form-control,
.input-group-lg > .input-group-addon,
.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
  border-radius: 3px;
}
select.input-group-lg > .form-control,
select.input-group-lg > .input-group-addon,
select.input-group-lg > .input-group-btn > .btn {
  height: 45px;
  line-height: 45px;
}
textarea.input-group-lg > .form-control,
textarea.input-group-lg > .input-group-addon,
textarea.input-group-lg > .input-group-btn > .btn,
select[multiple].input-group-lg > .form-control,
select[multiple].input-group-lg > .input-group-addon,
select[multiple].input-group-lg > .input-group-btn > .btn {
  height: auto;
}
.input-group-sm > .form-control,
.input-group-sm > .input-group-addon,
.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
}
select.input-group-sm > .form-control,
select.input-group-sm > .input-group-addon,
select.input-group-sm > .input-group-btn > .btn {
  height: 30px;
  line-height: 30px;
}
textarea.input-group-sm > .form-control,
textarea.input-group-sm > .input-group-addon,
textarea.input-group-sm > .input-group-btn > .btn,
select[multiple].input-group-sm > .form-control,
select[multiple].input-group-sm > .input-group-addon,
select[multiple].input-group-sm > .input-group-btn > .btn {
  height: auto;
}
.input-group-addon,
.input-group-btn,
.input-group .form-control {
  display: table-cell;
}
.input-group-addon:not(:first-child):not(:last-child),
.input-group-btn:not(:first-child):not(:last-child),
.input-group .form-control:not(:first-child):not(:last-child) {
  border-radius: 0;
}
.input-group-addon,
.input-group-btn {
  width: 1%;
  white-space: nowrap;
  vertical-align: middle;
}
.input-group-addon {
  padding: 6px 12px;
  font-size: 13px;
  font-weight: normal;
  line-height: 1;
  color: #555555;
  text-align: center;
  background-color: #eeeeee;
  border: 1px solid #ccc;
  border-radius: 2px;
}
.input-group-addon.input-sm {
  padding: 5px 10px;
  font-size: 12px;
  border-radius: 1px;
}
.input-group-addon.input-lg {
  padding: 10px 16px;
  font-size: 17px;
  border-radius: 3px;
}
.input-group-addon input[type="radio"],
.input-group-addon input[type="checkbox"] {
  margin-top: 0;
}
.input-group .form-control:first-child,
.input-group-addon:first-child,
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group > .btn,
.input-group-btn:first-child > .dropdown-toggle,
.input-group-btn:last-child > .btn:not(:last-child):not(.dropdown-toggle),
.input-group-btn:last-child > .btn-group:not(:last-child) > .btn {
  border-bottom-right-radius: 0;
  border-top-right-radius: 0;
}
.input-group-addon:first-child {
  border-right: 0;
}
.input-group .form-control:last-child,
.input-group-addon:last-child,
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group > .btn,
.input-group-btn:last-child > .dropdown-toggle,
.input-group-btn:first-child > .btn:not(:first-child),
.input-group-btn:first-child > .btn-group:not(:first-child) > .btn {
  border-bottom-left-radius: 0;
  border-top-left-radius: 0;
}
.input-group-addon:last-child {
  border-left: 0;
}
.input-group-btn {
  position: relative;
  font-size: 0;
  white-space: nowrap;
}
.input-group-btn > .btn {
  position: relative;
}
.input-group-btn > .btn + .btn {
  margin-left: -1px;
}
.input-group-btn > .btn:hover,
.input-group-btn > .btn:focus,
.input-group-btn > .btn:active {
  z-index: 2;
}
.input-group-btn:first-child > .btn,
.input-group-btn:first-child > .btn-group {
  margin-right: -1px;
}
.input-group-btn:last-child > .btn,
.input-group-btn:last-child > .btn-group {
  z-index: 2;
  margin-left: -1px;
}
.nav {
  margin-bottom: 0;
  padding-left: 0;
  list-style: none;
}
.nav > li {
  position: relative;
  display: block;
}
.nav > li > a {
  position: relative;
  display: block;
  padding: 10px 15px;
}
.nav > li > a:hover,
.nav > li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.nav > li.disabled > a {
  color: #777777;
}
.nav > li.disabled > a:hover,
.nav > li.disabled > a:focus {
  color: #777777;
  text-decoration: none;
  background-color: transparent;
  cursor: not-allowed;
}
.nav .open > a,
.nav .open > a:hover,
.nav .open > a:focus {
  background-color: #eeeeee;
  border-color: #337ab7;
}
.nav .nav-divider {
  height: 1px;
  margin: 8px 0;
  overflow: hidden;
  background-color: #e5e5e5;
}
.nav > li > a > img {
  max-width: none;
}
.nav-tabs {
  border-bottom: 1px solid #ddd;
}
.nav-tabs > li {
  float: left;
  margin-bottom: -1px;
}
.nav-tabs > li > a {
  margin-right: 2px;
  line-height: 1.42857143;
  border: 1px solid transparent;
  border-radius: 2px 2px 0 0;
}
.nav-tabs > li > a:hover {
  border-color: #eeeeee #eeeeee #ddd;
}
.nav-tabs > li.active > a,
.nav-tabs > li.active > a:hover,
.nav-tabs > li.active > a:focus {
  color: #555555;
  background-color: #fff;
  border: 1px solid #ddd;
  border-bottom-color: transparent;
  cursor: default;
}
.nav-tabs.nav-justified {
  width: 100%;
  border-bottom: 0;
}
.nav-tabs.nav-justified > li {
  float: none;
}
.nav-tabs.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-tabs.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-tabs.nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs.nav-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs.nav-justified > .active > a,
.nav-tabs.nav-justified > .active > a:hover,
.nav-tabs.nav-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs.nav-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs.nav-justified > .active > a,
  .nav-tabs.nav-justified > .active > a:hover,
  .nav-tabs.nav-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.nav-pills > li {
  float: left;
}
.nav-pills > li > a {
  border-radius: 2px;
}
.nav-pills > li + li {
  margin-left: 2px;
}
.nav-pills > li.active > a,
.nav-pills > li.active > a:hover,
.nav-pills > li.active > a:focus {
  color: #fff;
  background-color: #337ab7;
}
.nav-stacked > li {
  float: none;
}
.nav-stacked > li + li {
  margin-top: 2px;
  margin-left: 0;
}
.nav-justified {
  width: 100%;
}
.nav-justified > li {
  float: none;
}
.nav-justified > li > a {
  text-align: center;
  margin-bottom: 5px;
}
.nav-justified > .dropdown .dropdown-menu {
  top: auto;
  left: auto;
}
@media (min-width: 768px) {
  .nav-justified > li {
    display: table-cell;
    width: 1%;
  }
  .nav-justified > li > a {
    margin-bottom: 0;
  }
}
.nav-tabs-justified {
  border-bottom: 0;
}
.nav-tabs-justified > li > a {
  margin-right: 0;
  border-radius: 2px;
}
.nav-tabs-justified > .active > a,
.nav-tabs-justified > .active > a:hover,
.nav-tabs-justified > .active > a:focus {
  border: 1px solid #ddd;
}
@media (min-width: 768px) {
  .nav-tabs-justified > li > a {
    border-bottom: 1px solid #ddd;
    border-radius: 2px 2px 0 0;
  }
  .nav-tabs-justified > .active > a,
  .nav-tabs-justified > .active > a:hover,
  .nav-tabs-justified > .active > a:focus {
    border-bottom-color: #fff;
  }
}
.tab-content > .tab-pane {
  display: none;
}
.tab-content > .active {
  display: block;
}
.nav-tabs .dropdown-menu {
  margin-top: -1px;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar {
  position: relative;
  min-height: 30px;
  margin-bottom: 18px;
  border: 1px solid transparent;
}
@media (min-width: 541px) {
  .navbar {
    border-radius: 2px;
  }
}
@media (min-width: 541px) {
  .navbar-header {
    float: left;
  }
}
.navbar-collapse {
  overflow-x: visible;
  padding-right: 0px;
  padding-left: 0px;
  border-top: 1px solid transparent;
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1);
  -webkit-overflow-scrolling: touch;
}
.navbar-collapse.in {
  overflow-y: auto;
}
@media (min-width: 541px) {
  .navbar-collapse {
    width: auto;
    border-top: 0;
    box-shadow: none;
  }
  .navbar-collapse.collapse {
    display: block !important;
    height: auto !important;
    padding-bottom: 0;
    overflow: visible !important;
  }
  .navbar-collapse.in {
    overflow-y: visible;
  }
  .navbar-fixed-top .navbar-collapse,
  .navbar-static-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    padding-left: 0;
    padding-right: 0;
  }
}
.navbar-fixed-top .navbar-collapse,
.navbar-fixed-bottom .navbar-collapse {
  max-height: 340px;
}
@media (max-device-width: 540px) and (orientation: landscape) {
  .navbar-fixed-top .navbar-collapse,
  .navbar-fixed-bottom .navbar-collapse {
    max-height: 200px;
  }
}
.container > .navbar-header,
.container-fluid > .navbar-header,
.container > .navbar-collapse,
.container-fluid > .navbar-collapse {
  margin-right: 0px;
  margin-left: 0px;
}
@media (min-width: 541px) {
  .container > .navbar-header,
  .container-fluid > .navbar-header,
  .container > .navbar-collapse,
  .container-fluid > .navbar-collapse {
    margin-right: 0;
    margin-left: 0;
  }
}
.navbar-static-top {
  z-index: 1000;
  border-width: 0 0 1px;
}
@media (min-width: 541px) {
  .navbar-static-top {
    border-radius: 0;
  }
}
.navbar-fixed-top,
.navbar-fixed-bottom {
  position: fixed;
  right: 0;
  left: 0;
  z-index: 1030;
}
@media (min-width: 541px) {
  .navbar-fixed-top,
  .navbar-fixed-bottom {
    border-radius: 0;
  }
}
.navbar-fixed-top {
  top: 0;
  border-width: 0 0 1px;
}
.navbar-fixed-bottom {
  bottom: 0;
  margin-bottom: 0;
  border-width: 1px 0 0;
}
.navbar-brand {
  float: left;
  padding: 6px 0px;
  font-size: 17px;
  line-height: 18px;
  height: 30px;
}
.navbar-brand:hover,
.navbar-brand:focus {
  text-decoration: none;
}
.navbar-brand > img {
  display: block;
}
@media (min-width: 541px) {
  .navbar > .container .navbar-brand,
  .navbar > .container-fluid .navbar-brand {
    margin-left: 0px;
  }
}
.navbar-toggle {
  position: relative;
  float: right;
  margin-right: 0px;
  padding: 9px 10px;
  margin-top: -2px;
  margin-bottom: -2px;
  background-color: transparent;
  background-image: none;
  border: 1px solid transparent;
  border-radius: 2px;
}
.navbar-toggle:focus {
  outline: 0;
}
.navbar-toggle .icon-bar {
  display: block;
  width: 22px;
  height: 2px;
  border-radius: 1px;
}
.navbar-toggle .icon-bar + .icon-bar {
  margin-top: 4px;
}
@media (min-width: 541px) {
  .navbar-toggle {
    display: none;
  }
}
.navbar-nav {
  margin: 3px 0px;
}
.navbar-nav > li > a {
  padding-top: 10px;
  padding-bottom: 10px;
  line-height: 18px;
}
@media (max-width: 540px) {
  .navbar-nav .open .dropdown-menu {
    position: static;
    float: none;
    width: auto;
    margin-top: 0;
    background-color: transparent;
    border: 0;
    box-shadow: none;
  }
  .navbar-nav .open .dropdown-menu > li > a,
  .navbar-nav .open .dropdown-menu .dropdown-header {
    padding: 5px 15px 5px 25px;
  }
  .navbar-nav .open .dropdown-menu > li > a {
    line-height: 18px;
  }
  .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-nav .open .dropdown-menu > li > a:focus {
    background-image: none;
  }
}
@media (min-width: 541px) {
  .navbar-nav {
    float: left;
    margin: 0;
  }
  .navbar-nav > li {
    float: left;
  }
  .navbar-nav > li > a {
    padding-top: 6px;
    padding-bottom: 6px;
  }
}
.navbar-form {
  margin-left: 0px;
  margin-right: 0px;
  padding: 10px 0px;
  border-top: 1px solid transparent;
  border-bottom: 1px solid transparent;
  -webkit-box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.1), 0 1px 0 rgba(255, 255, 255, 0.1);
  margin-top: -1px;
  margin-bottom: -1px;
}
@media (min-width: 768px) {
  .navbar-form .form-group {
    display: inline-block;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .form-control {
    display: inline-block;
    width: auto;
    vertical-align: middle;
  }
  .navbar-form .form-control-static {
    display: inline-block;
  }
  .navbar-form .input-group {
    display: inline-table;
    vertical-align: middle;
  }
  .navbar-form .input-group .input-group-addon,
  .navbar-form .input-group .input-group-btn,
  .navbar-form .input-group .form-control {
    width: auto;
  }
  .navbar-form .input-group > .form-control {
    width: 100%;
  }
  .navbar-form .control-label {
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio,
  .navbar-form .checkbox {
    display: inline-block;
    margin-top: 0;
    margin-bottom: 0;
    vertical-align: middle;
  }
  .navbar-form .radio label,
  .navbar-form .checkbox label {
    padding-left: 0;
  }
  .navbar-form .radio input[type="radio"],
  .navbar-form .checkbox input[type="checkbox"] {
    position: relative;
    margin-left: 0;
  }
  .navbar-form .has-feedback .form-control-feedback {
    top: 0;
  }
}
@media (max-width: 540px) {
  .navbar-form .form-group {
    margin-bottom: 5px;
  }
  .navbar-form .form-group:last-child {
    margin-bottom: 0;
  }
}
@media (min-width: 541px) {
  .navbar-form {
    width: auto;
    border: 0;
    margin-left: 0;
    margin-right: 0;
    padding-top: 0;
    padding-bottom: 0;
    -webkit-box-shadow: none;
    box-shadow: none;
  }
}
.navbar-nav > li > .dropdown-menu {
  margin-top: 0;
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.navbar-fixed-bottom .navbar-nav > li > .dropdown-menu {
  margin-bottom: 0;
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
  border-bottom-right-radius: 0;
  border-bottom-left-radius: 0;
}
.navbar-btn {
  margin-top: -1px;
  margin-bottom: -1px;
}
.navbar-btn.btn-sm {
  margin-top: 0px;
  margin-bottom: 0px;
}
.navbar-btn.btn-xs {
  margin-top: 4px;
  margin-bottom: 4px;
}
.navbar-text {
  margin-top: 6px;
  margin-bottom: 6px;
}
@media (min-width: 541px) {
  .navbar-text {
    float: left;
    margin-left: 0px;
    margin-right: 0px;
  }
}
@media (min-width: 541px) {
  .navbar-left {
    float: left !important;
    float: left;
  }
  .navbar-right {
    float: right !important;
    float: right;
    margin-right: 0px;
  }
  .navbar-right ~ .navbar-right {
    margin-right: 0;
  }
}
.navbar-default {
  background-color: #f8f8f8;
  border-color: #e7e7e7;
}
.navbar-default .navbar-brand {
  color: #777;
}
.navbar-default .navbar-brand:hover,
.navbar-default .navbar-brand:focus {
  color: #5e5e5e;
  background-color: transparent;
}
.navbar-default .navbar-text {
  color: #777;
}
.navbar-default .navbar-nav > li > a {
  color: #777;
}
.navbar-default .navbar-nav > li > a:hover,
.navbar-default .navbar-nav > li > a:focus {
  color: #333;
  background-color: transparent;
}
.navbar-default .navbar-nav > .active > a,
.navbar-default .navbar-nav > .active > a:hover,
.navbar-default .navbar-nav > .active > a:focus {
  color: #555;
  background-color: #e7e7e7;
}
.navbar-default .navbar-nav > .disabled > a,
.navbar-default .navbar-nav > .disabled > a:hover,
.navbar-default .navbar-nav > .disabled > a:focus {
  color: #ccc;
  background-color: transparent;
}
.navbar-default .navbar-toggle {
  border-color: #ddd;
}
.navbar-default .navbar-toggle:hover,
.navbar-default .navbar-toggle:focus {
  background-color: #ddd;
}
.navbar-default .navbar-toggle .icon-bar {
  background-color: #888;
}
.navbar-default .navbar-collapse,
.navbar-default .navbar-form {
  border-color: #e7e7e7;
}
.navbar-default .navbar-nav > .open > a,
.navbar-default .navbar-nav > .open > a:hover,
.navbar-default .navbar-nav > .open > a:focus {
  background-color: #e7e7e7;
  color: #555;
}
@media (max-width: 540px) {
  .navbar-default .navbar-nav .open .dropdown-menu > li > a {
    color: #777;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #333;
    background-color: transparent;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #555;
    background-color: #e7e7e7;
  }
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-default .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #ccc;
    background-color: transparent;
  }
}
.navbar-default .navbar-link {
  color: #777;
}
.navbar-default .navbar-link:hover {
  color: #333;
}
.navbar-default .btn-link {
  color: #777;
}
.navbar-default .btn-link:hover,
.navbar-default .btn-link:focus {
  color: #333;
}
.navbar-default .btn-link[disabled]:hover,
fieldset[disabled] .navbar-default .btn-link:hover,
.navbar-default .btn-link[disabled]:focus,
fieldset[disabled] .navbar-default .btn-link:focus {
  color: #ccc;
}
.navbar-inverse {
  background-color: #222;
  border-color: #080808;
}
.navbar-inverse .navbar-brand {
  color: #9d9d9d;
}
.navbar-inverse .navbar-brand:hover,
.navbar-inverse .navbar-brand:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-text {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a {
  color: #9d9d9d;
}
.navbar-inverse .navbar-nav > li > a:hover,
.navbar-inverse .navbar-nav > li > a:focus {
  color: #fff;
  background-color: transparent;
}
.navbar-inverse .navbar-nav > .active > a,
.navbar-inverse .navbar-nav > .active > a:hover,
.navbar-inverse .navbar-nav > .active > a:focus {
  color: #fff;
  background-color: #080808;
}
.navbar-inverse .navbar-nav > .disabled > a,
.navbar-inverse .navbar-nav > .disabled > a:hover,
.navbar-inverse .navbar-nav > .disabled > a:focus {
  color: #444;
  background-color: transparent;
}
.navbar-inverse .navbar-toggle {
  border-color: #333;
}
.navbar-inverse .navbar-toggle:hover,
.navbar-inverse .navbar-toggle:focus {
  background-color: #333;
}
.navbar-inverse .navbar-toggle .icon-bar {
  background-color: #fff;
}
.navbar-inverse .navbar-collapse,
.navbar-inverse .navbar-form {
  border-color: #101010;
}
.navbar-inverse .navbar-nav > .open > a,
.navbar-inverse .navbar-nav > .open > a:hover,
.navbar-inverse .navbar-nav > .open > a:focus {
  background-color: #080808;
  color: #fff;
}
@media (max-width: 540px) {
  .navbar-inverse .navbar-nav .open .dropdown-menu > .dropdown-header {
    border-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu .divider {
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a {
    color: #9d9d9d;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > li > a:focus {
    color: #fff;
    background-color: transparent;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .active > a:focus {
    color: #fff;
    background-color: #080808;
  }
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:hover,
  .navbar-inverse .navbar-nav .open .dropdown-menu > .disabled > a:focus {
    color: #444;
    background-color: transparent;
  }
}
.navbar-inverse .navbar-link {
  color: #9d9d9d;
}
.navbar-inverse .navbar-link:hover {
  color: #fff;
}
.navbar-inverse .btn-link {
  color: #9d9d9d;
}
.navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link:focus {
  color: #fff;
}
.navbar-inverse .btn-link[disabled]:hover,
fieldset[disabled] .navbar-inverse .btn-link:hover,
.navbar-inverse .btn-link[disabled]:focus,
fieldset[disabled] .navbar-inverse .btn-link:focus {
  color: #444;
}
.breadcrumb {
  padding: 8px 15px;
  margin-bottom: 18px;
  list-style: none;
  background-color: #f5f5f5;
  border-radius: 2px;
}
.breadcrumb > li {
  display: inline-block;
}
.breadcrumb > li + li:before {
  content: "/\00a0";
  padding: 0 5px;
  color: #5e5e5e;
}
.breadcrumb > .active {
  color: #777777;
}
.pagination {
  display: inline-block;
  padding-left: 0;
  margin: 18px 0;
  border-radius: 2px;
}
.pagination > li {
  display: inline;
}
.pagination > li > a,
.pagination > li > span {
  position: relative;
  float: left;
  padding: 6px 12px;
  line-height: 1.42857143;
  text-decoration: none;
  color: #337ab7;
  background-color: #fff;
  border: 1px solid #ddd;
  margin-left: -1px;
}
.pagination > li:first-child > a,
.pagination > li:first-child > span {
  margin-left: 0;
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.pagination > li:last-child > a,
.pagination > li:last-child > span {
  border-bottom-right-radius: 2px;
  border-top-right-radius: 2px;
}
.pagination > li > a:hover,
.pagination > li > span:hover,
.pagination > li > a:focus,
.pagination > li > span:focus {
  z-index: 2;
  color: #23527c;
  background-color: #eeeeee;
  border-color: #ddd;
}
.pagination > .active > a,
.pagination > .active > span,
.pagination > .active > a:hover,
.pagination > .active > span:hover,
.pagination > .active > a:focus,
.pagination > .active > span:focus {
  z-index: 3;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
  cursor: default;
}
.pagination > .disabled > span,
.pagination > .disabled > span:hover,
.pagination > .disabled > span:focus,
.pagination > .disabled > a,
.pagination > .disabled > a:hover,
.pagination > .disabled > a:focus {
  color: #777777;
  background-color: #fff;
  border-color: #ddd;
  cursor: not-allowed;
}
.pagination-lg > li > a,
.pagination-lg > li > span {
  padding: 10px 16px;
  font-size: 17px;
  line-height: 1.3333333;
}
.pagination-lg > li:first-child > a,
.pagination-lg > li:first-child > span {
  border-bottom-left-radius: 3px;
  border-top-left-radius: 3px;
}
.pagination-lg > li:last-child > a,
.pagination-lg > li:last-child > span {
  border-bottom-right-radius: 3px;
  border-top-right-radius: 3px;
}
.pagination-sm > li > a,
.pagination-sm > li > span {
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
}
.pagination-sm > li:first-child > a,
.pagination-sm > li:first-child > span {
  border-bottom-left-radius: 1px;
  border-top-left-radius: 1px;
}
.pagination-sm > li:last-child > a,
.pagination-sm > li:last-child > span {
  border-bottom-right-radius: 1px;
  border-top-right-radius: 1px;
}
.pager {
  padding-left: 0;
  margin: 18px 0;
  list-style: none;
  text-align: center;
}
.pager li {
  display: inline;
}
.pager li > a,
.pager li > span {
  display: inline-block;
  padding: 5px 14px;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 15px;
}
.pager li > a:hover,
.pager li > a:focus {
  text-decoration: none;
  background-color: #eeeeee;
}
.pager .next > a,
.pager .next > span {
  float: right;
}
.pager .previous > a,
.pager .previous > span {
  float: left;
}
.pager .disabled > a,
.pager .disabled > a:hover,
.pager .disabled > a:focus,
.pager .disabled > span {
  color: #777777;
  background-color: #fff;
  cursor: not-allowed;
}
.label {
  display: inline;
  padding: .2em .6em .3em;
  font-size: 75%;
  font-weight: bold;
  line-height: 1;
  color: #fff;
  text-align: center;
  white-space: nowrap;
  vertical-align: baseline;
  border-radius: .25em;
}
a.label:hover,
a.label:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.label:empty {
  display: none;
}
.btn .label {
  position: relative;
  top: -1px;
}
.label-default {
  background-color: #777777;
}
.label-default[href]:hover,
.label-default[href]:focus {
  background-color: #5e5e5e;
}
.label-primary {
  background-color: #337ab7;
}
.label-primary[href]:hover,
.label-primary[href]:focus {
  background-color: #286090;
}
.label-success {
  background-color: #5cb85c;
}
.label-success[href]:hover,
.label-success[href]:focus {
  background-color: #449d44;
}
.label-info {
  background-color: #5bc0de;
}
.label-info[href]:hover,
.label-info[href]:focus {
  background-color: #31b0d5;
}
.label-warning {
  background-color: #f0ad4e;
}
.label-warning[href]:hover,
.label-warning[href]:focus {
  background-color: #ec971f;
}
.label-danger {
  background-color: #d9534f;
}
.label-danger[href]:hover,
.label-danger[href]:focus {
  background-color: #c9302c;
}
.badge {
  display: inline-block;
  min-width: 10px;
  padding: 3px 7px;
  font-size: 12px;
  font-weight: bold;
  color: #fff;
  line-height: 1;
  vertical-align: middle;
  white-space: nowrap;
  text-align: center;
  background-color: #777777;
  border-radius: 10px;
}
.badge:empty {
  display: none;
}
.btn .badge {
  position: relative;
  top: -1px;
}
.btn-xs .badge,
.btn-group-xs > .btn .badge {
  top: 0;
  padding: 1px 5px;
}
a.badge:hover,
a.badge:focus {
  color: #fff;
  text-decoration: none;
  cursor: pointer;
}
.list-group-item.active > .badge,
.nav-pills > .active > a > .badge {
  color: #337ab7;
  background-color: #fff;
}
.list-group-item > .badge {
  float: right;
}
.list-group-item > .badge + .badge {
  margin-right: 5px;
}
.nav-pills > li > a > .badge {
  margin-left: 3px;
}
.jumbotron {
  padding-top: 30px;
  padding-bottom: 30px;
  margin-bottom: 30px;
  color: inherit;
  background-color: #eeeeee;
}
.jumbotron h1,
.jumbotron .h1 {
  color: inherit;
}
.jumbotron p {
  margin-bottom: 15px;
  font-size: 20px;
  font-weight: 200;
}
.jumbotron > hr {
  border-top-color: #d5d5d5;
}
.container .jumbotron,
.container-fluid .jumbotron {
  border-radius: 3px;
  padding-left: 0px;
  padding-right: 0px;
}
.jumbotron .container {
  max-width: 100%;
}
@media screen and (min-width: 768px) {
  .jumbotron {
    padding-top: 48px;
    padding-bottom: 48px;
  }
  .container .jumbotron,
  .container-fluid .jumbotron {
    padding-left: 60px;
    padding-right: 60px;
  }
  .jumbotron h1,
  .jumbotron .h1 {
    font-size: 59px;
  }
}
.thumbnail {
  display: block;
  padding: 4px;
  margin-bottom: 18px;
  line-height: 1.42857143;
  background-color: #fff;
  border: 1px solid #ddd;
  border-radius: 2px;
  -webkit-transition: border 0.2s ease-in-out;
  -o-transition: border 0.2s ease-in-out;
  transition: border 0.2s ease-in-out;
}
.thumbnail > img,
.thumbnail a > img {
  margin-left: auto;
  margin-right: auto;
}
a.thumbnail:hover,
a.thumbnail:focus,
a.thumbnail.active {
  border-color: #337ab7;
}
.thumbnail .caption {
  padding: 9px;
  color: #000;
}
.alert {
  padding: 15px;
  margin-bottom: 18px;
  border: 1px solid transparent;
  border-radius: 2px;
}
.alert h4 {
  margin-top: 0;
  color: inherit;
}
.alert .alert-link {
  font-weight: bold;
}
.alert > p,
.alert > ul {
  margin-bottom: 0;
}
.alert > p + p {
  margin-top: 5px;
}
.alert-dismissable,
.alert-dismissible {
  padding-right: 35px;
}
.alert-dismissable .close,
.alert-dismissible .close {
  position: relative;
  top: -2px;
  right: -21px;
  color: inherit;
}
.alert-success {
  background-color: #dff0d8;
  border-color: #d6e9c6;
  color: #3c763d;
}
.alert-success hr {
  border-top-color: #c9e2b3;
}
.alert-success .alert-link {
  color: #2b542c;
}
.alert-info {
  background-color: #d9edf7;
  border-color: #bce8f1;
  color: #31708f;
}
.alert-info hr {
  border-top-color: #a6e1ec;
}
.alert-info .alert-link {
  color: #245269;
}
.alert-warning {
  background-color: #fcf8e3;
  border-color: #faebcc;
  color: #8a6d3b;
}
.alert-warning hr {
  border-top-color: #f7e1b5;
}
.alert-warning .alert-link {
  color: #66512c;
}
.alert-danger {
  background-color: #f2dede;
  border-color: #ebccd1;
  color: #a94442;
}
.alert-danger hr {
  border-top-color: #e4b9c0;
}
.alert-danger .alert-link {
  color: #843534;
}
@-webkit-keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
@keyframes progress-bar-stripes {
  from {
    background-position: 40px 0;
  }
  to {
    background-position: 0 0;
  }
}
.progress {
  overflow: hidden;
  height: 18px;
  margin-bottom: 18px;
  background-color: #f5f5f5;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
  box-shadow: inset 0 1px 2px rgba(0, 0, 0, 0.1);
}
.progress-bar {
  float: left;
  width: 0%;
  height: 100%;
  font-size: 12px;
  line-height: 18px;
  color: #fff;
  text-align: center;
  background-color: #337ab7;
  -webkit-box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  box-shadow: inset 0 -1px 0 rgba(0, 0, 0, 0.15);
  -webkit-transition: width 0.6s ease;
  -o-transition: width 0.6s ease;
  transition: width 0.6s ease;
}
.progress-striped .progress-bar,
.progress-bar-striped {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-size: 40px 40px;
}
.progress.active .progress-bar,
.progress-bar.active {
  -webkit-animation: progress-bar-stripes 2s linear infinite;
  -o-animation: progress-bar-stripes 2s linear infinite;
  animation: progress-bar-stripes 2s linear infinite;
}
.progress-bar-success {
  background-color: #5cb85c;
}
.progress-striped .progress-bar-success {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-info {
  background-color: #5bc0de;
}
.progress-striped .progress-bar-info {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-warning {
  background-color: #f0ad4e;
}
.progress-striped .progress-bar-warning {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.progress-bar-danger {
  background-color: #d9534f;
}
.progress-striped .progress-bar-danger {
  background-image: -webkit-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: -o-linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
  background-image: linear-gradient(45deg, rgba(255, 255, 255, 0.15) 25%, transparent 25%, transparent 50%, rgba(255, 255, 255, 0.15) 50%, rgba(255, 255, 255, 0.15) 75%, transparent 75%, transparent);
}
.media {
  margin-top: 15px;
}
.media:first-child {
  margin-top: 0;
}
.media,
.media-body {
  zoom: 1;
  overflow: hidden;
}
.media-body {
  width: 10000px;
}
.media-object {
  display: block;
}
.media-object.img-thumbnail {
  max-width: none;
}
.media-right,
.media > .pull-right {
  padding-left: 10px;
}
.media-left,
.media > .pull-left {
  padding-right: 10px;
}
.media-left,
.media-right,
.media-body {
  display: table-cell;
  vertical-align: top;
}
.media-middle {
  vertical-align: middle;
}
.media-bottom {
  vertical-align: bottom;
}
.media-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.media-list {
  padding-left: 0;
  list-style: none;
}
.list-group {
  margin-bottom: 20px;
  padding-left: 0;
}
.list-group-item {
  position: relative;
  display: block;
  padding: 10px 15px;
  margin-bottom: -1px;
  background-color: #fff;
  border: 1px solid #ddd;
}
.list-group-item:first-child {
  border-top-right-radius: 2px;
  border-top-left-radius: 2px;
}
.list-group-item:last-child {
  margin-bottom: 0;
  border-bottom-right-radius: 2px;
  border-bottom-left-radius: 2px;
}
a.list-group-item,
button.list-group-item {
  color: #555;
}
a.list-group-item .list-group-item-heading,
button.list-group-item .list-group-item-heading {
  color: #333;
}
a.list-group-item:hover,
button.list-group-item:hover,
a.list-group-item:focus,
button.list-group-item:focus {
  text-decoration: none;
  color: #555;
  background-color: #f5f5f5;
}
button.list-group-item {
  width: 100%;
  text-align: left;
}
.list-group-item.disabled,
.list-group-item.disabled:hover,
.list-group-item.disabled:focus {
  background-color: #eeeeee;
  color: #777777;
  cursor: not-allowed;
}
.list-group-item.disabled .list-group-item-heading,
.list-group-item.disabled:hover .list-group-item-heading,
.list-group-item.disabled:focus .list-group-item-heading {
  color: inherit;
}
.list-group-item.disabled .list-group-item-text,
.list-group-item.disabled:hover .list-group-item-text,
.list-group-item.disabled:focus .list-group-item-text {
  color: #777777;
}
.list-group-item.active,
.list-group-item.active:hover,
.list-group-item.active:focus {
  z-index: 2;
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.list-group-item.active .list-group-item-heading,
.list-group-item.active:hover .list-group-item-heading,
.list-group-item.active:focus .list-group-item-heading,
.list-group-item.active .list-group-item-heading > small,
.list-group-item.active:hover .list-group-item-heading > small,
.list-group-item.active:focus .list-group-item-heading > small,
.list-group-item.active .list-group-item-heading > .small,
.list-group-item.active:hover .list-group-item-heading > .small,
.list-group-item.active:focus .list-group-item-heading > .small {
  color: inherit;
}
.list-group-item.active .list-group-item-text,
.list-group-item.active:hover .list-group-item-text,
.list-group-item.active:focus .list-group-item-text {
  color: #c7ddef;
}
.list-group-item-success {
  color: #3c763d;
  background-color: #dff0d8;
}
a.list-group-item-success,
button.list-group-item-success {
  color: #3c763d;
}
a.list-group-item-success .list-group-item-heading,
button.list-group-item-success .list-group-item-heading {
  color: inherit;
}
a.list-group-item-success:hover,
button.list-group-item-success:hover,
a.list-group-item-success:focus,
button.list-group-item-success:focus {
  color: #3c763d;
  background-color: #d0e9c6;
}
a.list-group-item-success.active,
button.list-group-item-success.active,
a.list-group-item-success.active:hover,
button.list-group-item-success.active:hover,
a.list-group-item-success.active:focus,
button.list-group-item-success.active:focus {
  color: #fff;
  background-color: #3c763d;
  border-color: #3c763d;
}
.list-group-item-info {
  color: #31708f;
  background-color: #d9edf7;
}
a.list-group-item-info,
button.list-group-item-info {
  color: #31708f;
}
a.list-group-item-info .list-group-item-heading,
button.list-group-item-info .list-group-item-heading {
  color: inherit;
}
a.list-group-item-info:hover,
button.list-group-item-info:hover,
a.list-group-item-info:focus,
button.list-group-item-info:focus {
  color: #31708f;
  background-color: #c4e3f3;
}
a.list-group-item-info.active,
button.list-group-item-info.active,
a.list-group-item-info.active:hover,
button.list-group-item-info.active:hover,
a.list-group-item-info.active:focus,
button.list-group-item-info.active:focus {
  color: #fff;
  background-color: #31708f;
  border-color: #31708f;
}
.list-group-item-warning {
  color: #8a6d3b;
  background-color: #fcf8e3;
}
a.list-group-item-warning,
button.list-group-item-warning {
  color: #8a6d3b;
}
a.list-group-item-warning .list-group-item-heading,
button.list-group-item-warning .list-group-item-heading {
  color: inherit;
}
a.list-group-item-warning:hover,
button.list-group-item-warning:hover,
a.list-group-item-warning:focus,
button.list-group-item-warning:focus {
  color: #8a6d3b;
  background-color: #faf2cc;
}
a.list-group-item-warning.active,
button.list-group-item-warning.active,
a.list-group-item-warning.active:hover,
button.list-group-item-warning.active:hover,
a.list-group-item-warning.active:focus,
button.list-group-item-warning.active:focus {
  color: #fff;
  background-color: #8a6d3b;
  border-color: #8a6d3b;
}
.list-group-item-danger {
  color: #a94442;
  background-color: #f2dede;
}
a.list-group-item-danger,
button.list-group-item-danger {
  color: #a94442;
}
a.list-group-item-danger .list-group-item-heading,
button.list-group-item-danger .list-group-item-heading {
  color: inherit;
}
a.list-group-item-danger:hover,
button.list-group-item-danger:hover,
a.list-group-item-danger:focus,
button.list-group-item-danger:focus {
  color: #a94442;
  background-color: #ebcccc;
}
a.list-group-item-danger.active,
button.list-group-item-danger.active,
a.list-group-item-danger.active:hover,
button.list-group-item-danger.active:hover,
a.list-group-item-danger.active:focus,
button.list-group-item-danger.active:focus {
  color: #fff;
  background-color: #a94442;
  border-color: #a94442;
}
.list-group-item-heading {
  margin-top: 0;
  margin-bottom: 5px;
}
.list-group-item-text {
  margin-bottom: 0;
  line-height: 1.3;
}
.panel {
  margin-bottom: 18px;
  background-color: #fff;
  border: 1px solid transparent;
  border-radius: 2px;
  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.05);
}
.panel-body {
  padding: 15px;
}
.panel-heading {
  padding: 10px 15px;
  border-bottom: 1px solid transparent;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel-heading > .dropdown .dropdown-toggle {
  color: inherit;
}
.panel-title {
  margin-top: 0;
  margin-bottom: 0;
  font-size: 15px;
  color: inherit;
}
.panel-title > a,
.panel-title > small,
.panel-title > .small,
.panel-title > small > a,
.panel-title > .small > a {
  color: inherit;
}
.panel-footer {
  padding: 10px 15px;
  background-color: #f5f5f5;
  border-top: 1px solid #ddd;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .list-group,
.panel > .panel-collapse > .list-group {
  margin-bottom: 0;
}
.panel > .list-group .list-group-item,
.panel > .panel-collapse > .list-group .list-group-item {
  border-width: 1px 0;
  border-radius: 0;
}
.panel > .list-group:first-child .list-group-item:first-child,
.panel > .panel-collapse > .list-group:first-child .list-group-item:first-child {
  border-top: 0;
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .list-group:last-child .list-group-item:last-child,
.panel > .panel-collapse > .list-group:last-child .list-group-item:last-child {
  border-bottom: 0;
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .panel-heading + .panel-collapse > .list-group .list-group-item:first-child {
  border-top-right-radius: 0;
  border-top-left-radius: 0;
}
.panel-heading + .list-group .list-group-item:first-child {
  border-top-width: 0;
}
.list-group + .panel-footer {
  border-top-width: 0;
}
.panel > .table,
.panel > .table-responsive > .table,
.panel > .panel-collapse > .table {
  margin-bottom: 0;
}
.panel > .table caption,
.panel > .table-responsive > .table caption,
.panel > .panel-collapse > .table caption {
  padding-left: 15px;
  padding-right: 15px;
}
.panel > .table:first-child,
.panel > .table-responsive:first-child > .table:first-child {
  border-top-right-radius: 1px;
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child {
  border-top-left-radius: 1px;
  border-top-right-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:first-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:first-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:first-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:first-child {
  border-top-left-radius: 1px;
}
.panel > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child td:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child td:last-child,
.panel > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > thead:first-child > tr:first-child th:last-child,
.panel > .table:first-child > tbody:first-child > tr:first-child th:last-child,
.panel > .table-responsive:first-child > .table:first-child > tbody:first-child > tr:first-child th:last-child {
  border-top-right-radius: 1px;
}
.panel > .table:last-child,
.panel > .table-responsive:last-child > .table:last-child {
  border-bottom-right-radius: 1px;
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child {
  border-bottom-left-radius: 1px;
  border-bottom-right-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:first-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:first-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:first-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:first-child {
  border-bottom-left-radius: 1px;
}
.panel > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child td:last-child,
.panel > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tbody:last-child > tr:last-child th:last-child,
.panel > .table:last-child > tfoot:last-child > tr:last-child th:last-child,
.panel > .table-responsive:last-child > .table:last-child > tfoot:last-child > tr:last-child th:last-child {
  border-bottom-right-radius: 1px;
}
.panel > .panel-body + .table,
.panel > .panel-body + .table-responsive,
.panel > .table + .panel-body,
.panel > .table-responsive + .panel-body {
  border-top: 1px solid #ddd;
}
.panel > .table > tbody:first-child > tr:first-child th,
.panel > .table > tbody:first-child > tr:first-child td {
  border-top: 0;
}
.panel > .table-bordered,
.panel > .table-responsive > .table-bordered {
  border: 0;
}
.panel > .table-bordered > thead > tr > th:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:first-child,
.panel > .table-bordered > tbody > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:first-child,
.panel > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:first-child,
.panel > .table-bordered > thead > tr > td:first-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:first-child,
.panel > .table-bordered > tbody > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:first-child,
.panel > .table-bordered > tfoot > tr > td:first-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:first-child {
  border-left: 0;
}
.panel > .table-bordered > thead > tr > th:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > th:last-child,
.panel > .table-bordered > tbody > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > th:last-child,
.panel > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > th:last-child,
.panel > .table-bordered > thead > tr > td:last-child,
.panel > .table-responsive > .table-bordered > thead > tr > td:last-child,
.panel > .table-bordered > tbody > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tbody > tr > td:last-child,
.panel > .table-bordered > tfoot > tr > td:last-child,
.panel > .table-responsive > .table-bordered > tfoot > tr > td:last-child {
  border-right: 0;
}
.panel > .table-bordered > thead > tr:first-child > td,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > td,
.panel > .table-bordered > tbody > tr:first-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > td,
.panel > .table-bordered > thead > tr:first-child > th,
.panel > .table-responsive > .table-bordered > thead > tr:first-child > th,
.panel > .table-bordered > tbody > tr:first-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:first-child > th {
  border-bottom: 0;
}
.panel > .table-bordered > tbody > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > td,
.panel > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > td,
.panel > .table-bordered > tbody > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tbody > tr:last-child > th,
.panel > .table-bordered > tfoot > tr:last-child > th,
.panel > .table-responsive > .table-bordered > tfoot > tr:last-child > th {
  border-bottom: 0;
}
.panel > .table-responsive {
  border: 0;
  margin-bottom: 0;
}
.panel-group {
  margin-bottom: 18px;
}
.panel-group .panel {
  margin-bottom: 0;
  border-radius: 2px;
}
.panel-group .panel + .panel {
  margin-top: 5px;
}
.panel-group .panel-heading {
  border-bottom: 0;
}
.panel-group .panel-heading + .panel-collapse > .panel-body,
.panel-group .panel-heading + .panel-collapse > .list-group {
  border-top: 1px solid #ddd;
}
.panel-group .panel-footer {
  border-top: 0;
}
.panel-group .panel-footer + .panel-collapse .panel-body {
  border-bottom: 1px solid #ddd;
}
.panel-default {
  border-color: #ddd;
}
.panel-default > .panel-heading {
  color: #333333;
  background-color: #f5f5f5;
  border-color: #ddd;
}
.panel-default > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ddd;
}
.panel-default > .panel-heading .badge {
  color: #f5f5f5;
  background-color: #333333;
}
.panel-default > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ddd;
}
.panel-primary {
  border-color: #337ab7;
}
.panel-primary > .panel-heading {
  color: #fff;
  background-color: #337ab7;
  border-color: #337ab7;
}
.panel-primary > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #337ab7;
}
.panel-primary > .panel-heading .badge {
  color: #337ab7;
  background-color: #fff;
}
.panel-primary > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #337ab7;
}
.panel-success {
  border-color: #d6e9c6;
}
.panel-success > .panel-heading {
  color: #3c763d;
  background-color: #dff0d8;
  border-color: #d6e9c6;
}
.panel-success > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #d6e9c6;
}
.panel-success > .panel-heading .badge {
  color: #dff0d8;
  background-color: #3c763d;
}
.panel-success > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #d6e9c6;
}
.panel-info {
  border-color: #bce8f1;
}
.panel-info > .panel-heading {
  color: #31708f;
  background-color: #d9edf7;
  border-color: #bce8f1;
}
.panel-info > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #bce8f1;
}
.panel-info > .panel-heading .badge {
  color: #d9edf7;
  background-color: #31708f;
}
.panel-info > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #bce8f1;
}
.panel-warning {
  border-color: #faebcc;
}
.panel-warning > .panel-heading {
  color: #8a6d3b;
  background-color: #fcf8e3;
  border-color: #faebcc;
}
.panel-warning > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #faebcc;
}
.panel-warning > .panel-heading .badge {
  color: #fcf8e3;
  background-color: #8a6d3b;
}
.panel-warning > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #faebcc;
}
.panel-danger {
  border-color: #ebccd1;
}
.panel-danger > .panel-heading {
  color: #a94442;
  background-color: #f2dede;
  border-color: #ebccd1;
}
.panel-danger > .panel-heading + .panel-collapse > .panel-body {
  border-top-color: #ebccd1;
}
.panel-danger > .panel-heading .badge {
  color: #f2dede;
  background-color: #a94442;
}
.panel-danger > .panel-footer + .panel-collapse > .panel-body {
  border-bottom-color: #ebccd1;
}
.embed-responsive {
  position: relative;
  display: block;
  height: 0;
  padding: 0;
  overflow: hidden;
}
.embed-responsive .embed-responsive-item,
.embed-responsive iframe,
.embed-responsive embed,
.embed-responsive object,
.embed-responsive video {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  height: 100%;
  width: 100%;
  border: 0;
}
.embed-responsive-16by9 {
  padding-bottom: 56.25%;
}
.embed-responsive-4by3 {
  padding-bottom: 75%;
}
.well {
  min-height: 20px;
  padding: 19px;
  margin-bottom: 20px;
  background-color: #f5f5f5;
  border: 1px solid #e3e3e3;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.05);
}
.well blockquote {
  border-color: #ddd;
  border-color: rgba(0, 0, 0, 0.15);
}
.well-lg {
  padding: 24px;
  border-radius: 3px;
}
.well-sm {
  padding: 9px;
  border-radius: 1px;
}
.close {
  float: right;
  font-size: 19.5px;
  font-weight: bold;
  line-height: 1;
  color: #000;
  text-shadow: 0 1px 0 #fff;
  opacity: 0.2;
  filter: alpha(opacity=20);
}
.close:hover,
.close:focus {
  color: #000;
  text-decoration: none;
  cursor: pointer;
  opacity: 0.5;
  filter: alpha(opacity=50);
}
button.close {
  padding: 0;
  cursor: pointer;
  background: transparent;
  border: 0;
  -webkit-appearance: none;
}
.modal-open {
  overflow: hidden;
}
.modal {
  display: none;
  overflow: hidden;
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1050;
  -webkit-overflow-scrolling: touch;
  outline: 0;
}
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, -25%);
  -ms-transform: translate(0, -25%);
  -o-transform: translate(0, -25%);
  transform: translate(0, -25%);
  -webkit-transition: -webkit-transform 0.3s ease-out;
  -moz-transition: -moz-transform 0.3s ease-out;
  -o-transition: -o-transform 0.3s ease-out;
  transition: transform 0.3s ease-out;
}
.modal.in .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
.modal-open .modal {
  overflow-x: hidden;
  overflow-y: auto;
}
.modal-dialog {
  position: relative;
  width: auto;
  margin: 10px;
}
.modal-content {
  position: relative;
  background-color: #fff;
  border: 1px solid #999;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  box-shadow: 0 3px 9px rgba(0, 0, 0, 0.5);
  background-clip: padding-box;
  outline: 0;
}
.modal-backdrop {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 1040;
  background-color: #000;
}
.modal-backdrop.fade {
  opacity: 0;
  filter: alpha(opacity=0);
}
.modal-backdrop.in {
  opacity: 0.5;
  filter: alpha(opacity=50);
}
.modal-header {
  padding: 15px;
  border-bottom: 1px solid #e5e5e5;
}
.modal-header .close {
  margin-top: -2px;
}
.modal-title {
  margin: 0;
  line-height: 1.42857143;
}
.modal-body {
  position: relative;
  padding: 15px;
}
.modal-footer {
  padding: 15px;
  text-align: right;
  border-top: 1px solid #e5e5e5;
}
.modal-footer .btn + .btn {
  margin-left: 5px;
  margin-bottom: 0;
}
.modal-footer .btn-group .btn + .btn {
  margin-left: -1px;
}
.modal-footer .btn-block + .btn-block {
  margin-left: 0;
}
.modal-scrollbar-measure {
  position: absolute;
  top: -9999px;
  width: 50px;
  height: 50px;
  overflow: scroll;
}
@media (min-width: 768px) {
  .modal-dialog {
    width: 600px;
    margin: 30px auto;
  }
  .modal-content {
    -webkit-box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
  }
  .modal-sm {
    width: 300px;
  }
}
@media (min-width: 992px) {
  .modal-lg {
    width: 900px;
  }
}
.tooltip {
  position: absolute;
  z-index: 1070;
  display: block;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 12px;
  opacity: 0;
  filter: alpha(opacity=0);
}
.tooltip.in {
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.tooltip.top {
  margin-top: -3px;
  padding: 5px 0;
}
.tooltip.right {
  margin-left: 3px;
  padding: 0 5px;
}
.tooltip.bottom {
  margin-top: 3px;
  padding: 5px 0;
}
.tooltip.left {
  margin-left: -3px;
  padding: 0 5px;
}
.tooltip-inner {
  max-width: 200px;
  padding: 3px 8px;
  color: #fff;
  text-align: center;
  background-color: #000;
  border-radius: 2px;
}
.tooltip-arrow {
  position: absolute;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.tooltip.top .tooltip-arrow {
  bottom: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-left .tooltip-arrow {
  bottom: 0;
  right: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.top-right .tooltip-arrow {
  bottom: 0;
  left: 5px;
  margin-bottom: -5px;
  border-width: 5px 5px 0;
  border-top-color: #000;
}
.tooltip.right .tooltip-arrow {
  top: 50%;
  left: 0;
  margin-top: -5px;
  border-width: 5px 5px 5px 0;
  border-right-color: #000;
}
.tooltip.left .tooltip-arrow {
  top: 50%;
  right: 0;
  margin-top: -5px;
  border-width: 5px 0 5px 5px;
  border-left-color: #000;
}
.tooltip.bottom .tooltip-arrow {
  top: 0;
  left: 50%;
  margin-left: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-left .tooltip-arrow {
  top: 0;
  right: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.tooltip.bottom-right .tooltip-arrow {
  top: 0;
  left: 5px;
  margin-top: -5px;
  border-width: 0 5px 5px;
  border-bottom-color: #000;
}
.popover {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1060;
  display: none;
  max-width: 276px;
  padding: 1px;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-style: normal;
  font-weight: normal;
  letter-spacing: normal;
  line-break: auto;
  line-height: 1.42857143;
  text-align: left;
  text-align: start;
  text-decoration: none;
  text-shadow: none;
  text-transform: none;
  white-space: normal;
  word-break: normal;
  word-spacing: normal;
  word-wrap: normal;
  font-size: 13px;
  background-color: #fff;
  background-clip: padding-box;
  border: 1px solid #ccc;
  border: 1px solid rgba(0, 0, 0, 0.2);
  border-radius: 3px;
  -webkit-box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
  box-shadow: 0 5px 10px rgba(0, 0, 0, 0.2);
}
.popover.top {
  margin-top: -10px;
}
.popover.right {
  margin-left: 10px;
}
.popover.bottom {
  margin-top: 10px;
}
.popover.left {
  margin-left: -10px;
}
.popover-title {
  margin: 0;
  padding: 8px 14px;
  font-size: 13px;
  background-color: #f7f7f7;
  border-bottom: 1px solid #ebebeb;
  border-radius: 2px 2px 0 0;
}
.popover-content {
  padding: 9px 14px;
}
.popover > .arrow,
.popover > .arrow:after {
  position: absolute;
  display: block;
  width: 0;
  height: 0;
  border-color: transparent;
  border-style: solid;
}
.popover > .arrow {
  border-width: 11px;
}
.popover > .arrow:after {
  border-width: 10px;
  content: "";
}
.popover.top > .arrow {
  left: 50%;
  margin-left: -11px;
  border-bottom-width: 0;
  border-top-color: #999999;
  border-top-color: rgba(0, 0, 0, 0.25);
  bottom: -11px;
}
.popover.top > .arrow:after {
  content: " ";
  bottom: 1px;
  margin-left: -10px;
  border-bottom-width: 0;
  border-top-color: #fff;
}
.popover.right > .arrow {
  top: 50%;
  left: -11px;
  margin-top: -11px;
  border-left-width: 0;
  border-right-color: #999999;
  border-right-color: rgba(0, 0, 0, 0.25);
}
.popover.right > .arrow:after {
  content: " ";
  left: 1px;
  bottom: -10px;
  border-left-width: 0;
  border-right-color: #fff;
}
.popover.bottom > .arrow {
  left: 50%;
  margin-left: -11px;
  border-top-width: 0;
  border-bottom-color: #999999;
  border-bottom-color: rgba(0, 0, 0, 0.25);
  top: -11px;
}
.popover.bottom > .arrow:after {
  content: " ";
  top: 1px;
  margin-left: -10px;
  border-top-width: 0;
  border-bottom-color: #fff;
}
.popover.left > .arrow {
  top: 50%;
  right: -11px;
  margin-top: -11px;
  border-right-width: 0;
  border-left-color: #999999;
  border-left-color: rgba(0, 0, 0, 0.25);
}
.popover.left > .arrow:after {
  content: " ";
  right: 1px;
  border-right-width: 0;
  border-left-color: #fff;
  bottom: -10px;
}
.carousel {
  position: relative;
}
.carousel-inner {
  position: relative;
  overflow: hidden;
  width: 100%;
}
.carousel-inner > .item {
  display: none;
  position: relative;
  -webkit-transition: 0.6s ease-in-out left;
  -o-transition: 0.6s ease-in-out left;
  transition: 0.6s ease-in-out left;
}
.carousel-inner > .item > img,
.carousel-inner > .item > a > img {
  line-height: 1;
}
@media all and (transform-3d), (-webkit-transform-3d) {
  .carousel-inner > .item {
    -webkit-transition: -webkit-transform 0.6s ease-in-out;
    -moz-transition: -moz-transform 0.6s ease-in-out;
    -o-transition: -o-transform 0.6s ease-in-out;
    transition: transform 0.6s ease-in-out;
    -webkit-backface-visibility: hidden;
    -moz-backface-visibility: hidden;
    backface-visibility: hidden;
    -webkit-perspective: 1000px;
    -moz-perspective: 1000px;
    perspective: 1000px;
  }
  .carousel-inner > .item.next,
  .carousel-inner > .item.active.right {
    -webkit-transform: translate3d(100%, 0, 0);
    transform: translate3d(100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.prev,
  .carousel-inner > .item.active.left {
    -webkit-transform: translate3d(-100%, 0, 0);
    transform: translate3d(-100%, 0, 0);
    left: 0;
  }
  .carousel-inner > .item.next.left,
  .carousel-inner > .item.prev.right,
  .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
.carousel-inner > .active,
.carousel-inner > .next,
.carousel-inner > .prev {
  display: block;
}
.carousel-inner > .active {
  left: 0;
}
.carousel-inner > .next,
.carousel-inner > .prev {
  position: absolute;
  top: 0;
  width: 100%;
}
.carousel-inner > .next {
  left: 100%;
}
.carousel-inner > .prev {
  left: -100%;
}
.carousel-inner > .next.left,
.carousel-inner > .prev.right {
  left: 0;
}
.carousel-inner > .active.left {
  left: -100%;
}
.carousel-inner > .active.right {
  left: 100%;
}
.carousel-control {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  width: 15%;
  opacity: 0.5;
  filter: alpha(opacity=50);
  font-size: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
  background-color: rgba(0, 0, 0, 0);
}
.carousel-control.left {
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.5) 0%, rgba(0, 0, 0, 0.0001) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#80000000', endColorstr='#00000000', GradientType=1);
}
.carousel-control.right {
  left: auto;
  right: 0;
  background-image: -webkit-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: -o-linear-gradient(left, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-image: linear-gradient(to right, rgba(0, 0, 0, 0.0001) 0%, rgba(0, 0, 0, 0.5) 100%);
  background-repeat: repeat-x;
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#00000000', endColorstr='#80000000', GradientType=1);
}
.carousel-control:hover,
.carousel-control:focus {
  outline: 0;
  color: #fff;
  text-decoration: none;
  opacity: 0.9;
  filter: alpha(opacity=90);
}
.carousel-control .icon-prev,
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-left,
.carousel-control .glyphicon-chevron-right {
  position: absolute;
  top: 50%;
  margin-top: -10px;
  z-index: 5;
  display: inline-block;
}
.carousel-control .icon-prev,
.carousel-control .glyphicon-chevron-left {
  left: 50%;
  margin-left: -10px;
}
.carousel-control .icon-next,
.carousel-control .glyphicon-chevron-right {
  right: 50%;
  margin-right: -10px;
}
.carousel-control .icon-prev,
.carousel-control .icon-next {
  width: 20px;
  height: 20px;
  line-height: 1;
  font-family: serif;
}
.carousel-control .icon-prev:before {
  content: '\2039';
}
.carousel-control .icon-next:before {
  content: '\203a';
}
.carousel-indicators {
  position: absolute;
  bottom: 10px;
  left: 50%;
  z-index: 15;
  width: 60%;
  margin-left: -30%;
  padding-left: 0;
  list-style: none;
  text-align: center;
}
.carousel-indicators li {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 1px;
  text-indent: -999px;
  border: 1px solid #fff;
  border-radius: 10px;
  cursor: pointer;
  background-color: #000 \9;
  background-color: rgba(0, 0, 0, 0);
}
.carousel-indicators .active {
  margin: 0;
  width: 12px;
  height: 12px;
  background-color: #fff;
}
.carousel-caption {
  position: absolute;
  left: 15%;
  right: 15%;
  bottom: 20px;
  z-index: 10;
  padding-top: 20px;
  padding-bottom: 20px;
  color: #fff;
  text-align: center;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.6);
}
.carousel-caption .btn {
  text-shadow: none;
}
@media screen and (min-width: 768px) {
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-prev,
  .carousel-control .icon-next {
    width: 30px;
    height: 30px;
    margin-top: -10px;
    font-size: 30px;
  }
  .carousel-control .glyphicon-chevron-left,
  .carousel-control .icon-prev {
    margin-left: -10px;
  }
  .carousel-control .glyphicon-chevron-right,
  .carousel-control .icon-next {
    margin-right: -10px;
  }
  .carousel-caption {
    left: 20%;
    right: 20%;
    padding-bottom: 30px;
  }
  .carousel-indicators {
    bottom: 20px;
  }
}
.clearfix:before,
.clearfix:after,
.dl-horizontal dd:before,
.dl-horizontal dd:after,
.container:before,
.container:after,
.container-fluid:before,
.container-fluid:after,
.row:before,
.row:after,
.form-horizontal .form-group:before,
.form-horizontal .form-group:after,
.btn-toolbar:before,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:before,
.btn-group-vertical > .btn-group:after,
.nav:before,
.nav:after,
.navbar:before,
.navbar:after,
.navbar-header:before,
.navbar-header:after,
.navbar-collapse:before,
.navbar-collapse:after,
.pager:before,
.pager:after,
.panel-body:before,
.panel-body:after,
.modal-header:before,
.modal-header:after,
.modal-footer:before,
.modal-footer:after,
.item_buttons:before,
.item_buttons:after {
  content: " ";
  display: table;
}
.clearfix:after,
.dl-horizontal dd:after,
.container:after,
.container-fluid:after,
.row:after,
.form-horizontal .form-group:after,
.btn-toolbar:after,
.btn-group-vertical > .btn-group:after,
.nav:after,
.navbar:after,
.navbar-header:after,
.navbar-collapse:after,
.pager:after,
.panel-body:after,
.modal-header:after,
.modal-footer:after,
.item_buttons:after {
  clear: both;
}
.center-block {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.pull-right {
  float: right !important;
}
.pull-left {
  float: left !important;
}
.hide {
  display: none !important;
}
.show {
  display: block !important;
}
.invisible {
  visibility: hidden;
}
.text-hide {
  font: 0/0 a;
  color: transparent;
  text-shadow: none;
  background-color: transparent;
  border: 0;
}
.hidden {
  display: none !important;
}
.affix {
  position: fixed;
}
@-ms-viewport {
  width: device-width;
}
.visible-xs,
.visible-sm,
.visible-md,
.visible-lg {
  display: none !important;
}
.visible-xs-block,
.visible-xs-inline,
.visible-xs-inline-block,
.visible-sm-block,
.visible-sm-inline,
.visible-sm-inline-block,
.visible-md-block,
.visible-md-inline,
.visible-md-inline-block,
.visible-lg-block,
.visible-lg-inline,
.visible-lg-inline-block {
  display: none !important;
}
@media (max-width: 767px) {
  .visible-xs {
    display: block !important;
  }
  table.visible-xs {
    display: table !important;
  }
  tr.visible-xs {
    display: table-row !important;
  }
  th.visible-xs,
  td.visible-xs {
    display: table-cell !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-block {
    display: block !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline {
    display: inline !important;
  }
}
@media (max-width: 767px) {
  .visible-xs-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm {
    display: block !important;
  }
  table.visible-sm {
    display: table !important;
  }
  tr.visible-sm {
    display: table-row !important;
  }
  th.visible-sm,
  td.visible-sm {
    display: table-cell !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-block {
    display: block !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline {
    display: inline !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .visible-sm-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md {
    display: block !important;
  }
  table.visible-md {
    display: table !important;
  }
  tr.visible-md {
    display: table-row !important;
  }
  th.visible-md,
  td.visible-md {
    display: table-cell !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-block {
    display: block !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline {
    display: inline !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .visible-md-inline-block {
    display: inline-block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg {
    display: block !important;
  }
  table.visible-lg {
    display: table !important;
  }
  tr.visible-lg {
    display: table-row !important;
  }
  th.visible-lg,
  td.visible-lg {
    display: table-cell !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-block {
    display: block !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline {
    display: inline !important;
  }
}
@media (min-width: 1200px) {
  .visible-lg-inline-block {
    display: inline-block !important;
  }
}
@media (max-width: 767px) {
  .hidden-xs {
    display: none !important;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  .hidden-sm {
    display: none !important;
  }
}
@media (min-width: 992px) and (max-width: 1199px) {
  .hidden-md {
    display: none !important;
  }
}
@media (min-width: 1200px) {
  .hidden-lg {
    display: none !important;
  }
}
.visible-print {
  display: none !important;
}
@media print {
  .visible-print {
    display: block !important;
  }
  table.visible-print {
    display: table !important;
  }
  tr.visible-print {
    display: table-row !important;
  }
  th.visible-print,
  td.visible-print {
    display: table-cell !important;
  }
}
.visible-print-block {
  display: none !important;
}
@media print {
  .visible-print-block {
    display: block !important;
  }
}
.visible-print-inline {
  display: none !important;
}
@media print {
  .visible-print-inline {
    display: inline !important;
  }
}
.visible-print-inline-block {
  display: none !important;
}
@media print {
  .visible-print-inline-block {
    display: inline-block !important;
  }
}
@media print {
  .hidden-print {
    display: none !important;
  }
}
/*!
*
* Font Awesome
*
*/
/*!
 *  Font Awesome 4.7.0 by @davegandy - http://fontawesome.io - @fontawesome
 *  License - http://fontawesome.io/license (Font: SIL OFL 1.1, CSS: MIT License)
 */
/* FONT PATH
 * -------------------------- */
@font-face {
  font-family: 'FontAwesome';
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?v=4.7.0');
  src: url('../components/font-awesome/fonts/fontawesome-webfont.eot?#iefix&v=4.7.0') format('embedded-opentype'), url('../components/font-awesome/fonts/fontawesome-webfont.woff2?v=4.7.0') format('woff2'), url('../components/font-awesome/fonts/fontawesome-webfont.woff?v=4.7.0') format('woff'), url('../components/font-awesome/fonts/fontawesome-webfont.ttf?v=4.7.0') format('truetype'), url('../components/font-awesome/fonts/fontawesome-webfont.svg?v=4.7.0#fontawesomeregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
.fa {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
/* makes the font 33% larger relative to the icon container */
.fa-lg {
  font-size: 1.33333333em;
  line-height: 0.75em;
  vertical-align: -15%;
}
.fa-2x {
  font-size: 2em;
}
.fa-3x {
  font-size: 3em;
}
.fa-4x {
  font-size: 4em;
}
.fa-5x {
  font-size: 5em;
}
.fa-fw {
  width: 1.28571429em;
  text-align: center;
}
.fa-ul {
  padding-left: 0;
  margin-left: 2.14285714em;
  list-style-type: none;
}
.fa-ul > li {
  position: relative;
}
.fa-li {
  position: absolute;
  left: -2.14285714em;
  width: 2.14285714em;
  top: 0.14285714em;
  text-align: center;
}
.fa-li.fa-lg {
  left: -1.85714286em;
}
.fa-border {
  padding: .2em .25em .15em;
  border: solid 0.08em #eee;
  border-radius: .1em;
}
.fa-pull-left {
  float: left;
}
.fa-pull-right {
  float: right;
}
.fa.fa-pull-left {
  margin-right: .3em;
}
.fa.fa-pull-right {
  margin-left: .3em;
}
/* Deprecated as of 4.4.0 */
.pull-right {
  float: right;
}
.pull-left {
  float: left;
}
.fa.pull-left {
  margin-right: .3em;
}
.fa.pull-right {
  margin-left: .3em;
}
.fa-spin {
  -webkit-animation: fa-spin 2s infinite linear;
  animation: fa-spin 2s infinite linear;
}
.fa-pulse {
  -webkit-animation: fa-spin 1s infinite steps(8);
  animation: fa-spin 1s infinite steps(8);
}
@-webkit-keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
@keyframes fa-spin {
  0% {
    -webkit-transform: rotate(0deg);
    transform: rotate(0deg);
  }
  100% {
    -webkit-transform: rotate(359deg);
    transform: rotate(359deg);
  }
}
.fa-rotate-90 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=1)";
  -webkit-transform: rotate(90deg);
  -ms-transform: rotate(90deg);
  transform: rotate(90deg);
}
.fa-rotate-180 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2)";
  -webkit-transform: rotate(180deg);
  -ms-transform: rotate(180deg);
  transform: rotate(180deg);
}
.fa-rotate-270 {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=3)";
  -webkit-transform: rotate(270deg);
  -ms-transform: rotate(270deg);
  transform: rotate(270deg);
}
.fa-flip-horizontal {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=0, mirror=1)";
  -webkit-transform: scale(-1, 1);
  -ms-transform: scale(-1, 1);
  transform: scale(-1, 1);
}
.fa-flip-vertical {
  -ms-filter: "progid:DXImageTransform.Microsoft.BasicImage(rotation=2, mirror=1)";
  -webkit-transform: scale(1, -1);
  -ms-transform: scale(1, -1);
  transform: scale(1, -1);
}
:root .fa-rotate-90,
:root .fa-rotate-180,
:root .fa-rotate-270,
:root .fa-flip-horizontal,
:root .fa-flip-vertical {
  filter: none;
}
.fa-stack {
  position: relative;
  display: inline-block;
  width: 2em;
  height: 2em;
  line-height: 2em;
  vertical-align: middle;
}
.fa-stack-1x,
.fa-stack-2x {
  position: absolute;
  left: 0;
  width: 100%;
  text-align: center;
}
.fa-stack-1x {
  line-height: inherit;
}
.fa-stack-2x {
  font-size: 2em;
}
.fa-inverse {
  color: #fff;
}
/* Font Awesome uses the Unicode Private Use Area (PUA) to ensure screen
   readers do not read off random characters that represent icons */
.fa-glass:before {
  content: "\f000";
}
.fa-music:before {
  content: "\f001";
}
.fa-search:before {
  content: "\f002";
}
.fa-envelope-o:before {
  content: "\f003";
}
.fa-heart:before {
  content: "\f004";
}
.fa-star:before {
  content: "\f005";
}
.fa-star-o:before {
  content: "\f006";
}
.fa-user:before {
  content: "\f007";
}
.fa-film:before {
  content: "\f008";
}
.fa-th-large:before {
  content: "\f009";
}
.fa-th:before {
  content: "\f00a";
}
.fa-th-list:before {
  content: "\f00b";
}
.fa-check:before {
  content: "\f00c";
}
.fa-remove:before,
.fa-close:before,
.fa-times:before {
  content: "\f00d";
}
.fa-search-plus:before {
  content: "\f00e";
}
.fa-search-minus:before {
  content: "\f010";
}
.fa-power-off:before {
  content: "\f011";
}
.fa-signal:before {
  content: "\f012";
}
.fa-gear:before,
.fa-cog:before {
  content: "\f013";
}
.fa-trash-o:before {
  content: "\f014";
}
.fa-home:before {
  content: "\f015";
}
.fa-file-o:before {
  content: "\f016";
}
.fa-clock-o:before {
  content: "\f017";
}
.fa-road:before {
  content: "\f018";
}
.fa-download:before {
  content: "\f019";
}
.fa-arrow-circle-o-down:before {
  content: "\f01a";
}
.fa-arrow-circle-o-up:before {
  content: "\f01b";
}
.fa-inbox:before {
  content: "\f01c";
}
.fa-play-circle-o:before {
  content: "\f01d";
}
.fa-rotate-right:before,
.fa-repeat:before {
  content: "\f01e";
}
.fa-refresh:before {
  content: "\f021";
}
.fa-list-alt:before {
  content: "\f022";
}
.fa-lock:before {
  content: "\f023";
}
.fa-flag:before {
  content: "\f024";
}
.fa-headphones:before {
  content: "\f025";
}
.fa-volume-off:before {
  content: "\f026";
}
.fa-volume-down:before {
  content: "\f027";
}
.fa-volume-up:before {
  content: "\f028";
}
.fa-qrcode:before {
  content: "\f029";
}
.fa-barcode:before {
  content: "\f02a";
}
.fa-tag:before {
  content: "\f02b";
}
.fa-tags:before {
  content: "\f02c";
}
.fa-book:before {
  content: "\f02d";
}
.fa-bookmark:before {
  content: "\f02e";
}
.fa-print:before {
  content: "\f02f";
}
.fa-camera:before {
  content: "\f030";
}
.fa-font:before {
  content: "\f031";
}
.fa-bold:before {
  content: "\f032";
}
.fa-italic:before {
  content: "\f033";
}
.fa-text-height:before {
  content: "\f034";
}
.fa-text-width:before {
  content: "\f035";
}
.fa-align-left:before {
  content: "\f036";
}
.fa-align-center:before {
  content: "\f037";
}
.fa-align-right:before {
  content: "\f038";
}
.fa-align-justify:before {
  content: "\f039";
}
.fa-list:before {
  content: "\f03a";
}
.fa-dedent:before,
.fa-outdent:before {
  content: "\f03b";
}
.fa-indent:before {
  content: "\f03c";
}
.fa-video-camera:before {
  content: "\f03d";
}
.fa-photo:before,
.fa-image:before,
.fa-picture-o:before {
  content: "\f03e";
}
.fa-pencil:before {
  content: "\f040";
}
.fa-map-marker:before {
  content: "\f041";
}
.fa-adjust:before {
  content: "\f042";
}
.fa-tint:before {
  content: "\f043";
}
.fa-edit:before,
.fa-pencil-square-o:before {
  content: "\f044";
}
.fa-share-square-o:before {
  content: "\f045";
}
.fa-check-square-o:before {
  content: "\f046";
}
.fa-arrows:before {
  content: "\f047";
}
.fa-step-backward:before {
  content: "\f048";
}
.fa-fast-backward:before {
  content: "\f049";
}
.fa-backward:before {
  content: "\f04a";
}
.fa-play:before {
  content: "\f04b";
}
.fa-pause:before {
  content: "\f04c";
}
.fa-stop:before {
  content: "\f04d";
}
.fa-forward:before {
  content: "\f04e";
}
.fa-fast-forward:before {
  content: "\f050";
}
.fa-step-forward:before {
  content: "\f051";
}
.fa-eject:before {
  content: "\f052";
}
.fa-chevron-left:before {
  content: "\f053";
}
.fa-chevron-right:before {
  content: "\f054";
}
.fa-plus-circle:before {
  content: "\f055";
}
.fa-minus-circle:before {
  content: "\f056";
}
.fa-times-circle:before {
  content: "\f057";
}
.fa-check-circle:before {
  content: "\f058";
}
.fa-question-circle:before {
  content: "\f059";
}
.fa-info-circle:before {
  content: "\f05a";
}
.fa-crosshairs:before {
  content: "\f05b";
}
.fa-times-circle-o:before {
  content: "\f05c";
}
.fa-check-circle-o:before {
  content: "\f05d";
}
.fa-ban:before {
  content: "\f05e";
}
.fa-arrow-left:before {
  content: "\f060";
}
.fa-arrow-right:before {
  content: "\f061";
}
.fa-arrow-up:before {
  content: "\f062";
}
.fa-arrow-down:before {
  content: "\f063";
}
.fa-mail-forward:before,
.fa-share:before {
  content: "\f064";
}
.fa-expand:before {
  content: "\f065";
}
.fa-compress:before {
  content: "\f066";
}
.fa-plus:before {
  content: "\f067";
}
.fa-minus:before {
  content: "\f068";
}
.fa-asterisk:before {
  content: "\f069";
}
.fa-exclamation-circle:before {
  content: "\f06a";
}
.fa-gift:before {
  content: "\f06b";
}
.fa-leaf:before {
  content: "\f06c";
}
.fa-fire:before {
  content: "\f06d";
}
.fa-eye:before {
  content: "\f06e";
}
.fa-eye-slash:before {
  content: "\f070";
}
.fa-warning:before,
.fa-exclamation-triangle:before {
  content: "\f071";
}
.fa-plane:before {
  content: "\f072";
}
.fa-calendar:before {
  content: "\f073";
}
.fa-random:before {
  content: "\f074";
}
.fa-comment:before {
  content: "\f075";
}
.fa-magnet:before {
  content: "\f076";
}
.fa-chevron-up:before {
  content: "\f077";
}
.fa-chevron-down:before {
  content: "\f078";
}
.fa-retweet:before {
  content: "\f079";
}
.fa-shopping-cart:before {
  content: "\f07a";
}
.fa-folder:before {
  content: "\f07b";
}
.fa-folder-open:before {
  content: "\f07c";
}
.fa-arrows-v:before {
  content: "\f07d";
}
.fa-arrows-h:before {
  content: "\f07e";
}
.fa-bar-chart-o:before,
.fa-bar-chart:before {
  content: "\f080";
}
.fa-twitter-square:before {
  content: "\f081";
}
.fa-facebook-square:before {
  content: "\f082";
}
.fa-camera-retro:before {
  content: "\f083";
}
.fa-key:before {
  content: "\f084";
}
.fa-gears:before,
.fa-cogs:before {
  content: "\f085";
}
.fa-comments:before {
  content: "\f086";
}
.fa-thumbs-o-up:before {
  content: "\f087";
}
.fa-thumbs-o-down:before {
  content: "\f088";
}
.fa-star-half:before {
  content: "\f089";
}
.fa-heart-o:before {
  content: "\f08a";
}
.fa-sign-out:before {
  content: "\f08b";
}
.fa-linkedin-square:before {
  content: "\f08c";
}
.fa-thumb-tack:before {
  content: "\f08d";
}
.fa-external-link:before {
  content: "\f08e";
}
.fa-sign-in:before {
  content: "\f090";
}
.fa-trophy:before {
  content: "\f091";
}
.fa-github-square:before {
  content: "\f092";
}
.fa-upload:before {
  content: "\f093";
}
.fa-lemon-o:before {
  content: "\f094";
}
.fa-phone:before {
  content: "\f095";
}
.fa-square-o:before {
  content: "\f096";
}
.fa-bookmark-o:before {
  content: "\f097";
}
.fa-phone-square:before {
  content: "\f098";
}
.fa-twitter:before {
  content: "\f099";
}
.fa-facebook-f:before,
.fa-facebook:before {
  content: "\f09a";
}
.fa-github:before {
  content: "\f09b";
}
.fa-unlock:before {
  content: "\f09c";
}
.fa-credit-card:before {
  content: "\f09d";
}
.fa-feed:before,
.fa-rss:before {
  content: "\f09e";
}
.fa-hdd-o:before {
  content: "\f0a0";
}
.fa-bullhorn:before {
  content: "\f0a1";
}
.fa-bell:before {
  content: "\f0f3";
}
.fa-certificate:before {
  content: "\f0a3";
}
.fa-hand-o-right:before {
  content: "\f0a4";
}
.fa-hand-o-left:before {
  content: "\f0a5";
}
.fa-hand-o-up:before {
  content: "\f0a6";
}
.fa-hand-o-down:before {
  content: "\f0a7";
}
.fa-arrow-circle-left:before {
  content: "\f0a8";
}
.fa-arrow-circle-right:before {
  content: "\f0a9";
}
.fa-arrow-circle-up:before {
  content: "\f0aa";
}
.fa-arrow-circle-down:before {
  content: "\f0ab";
}
.fa-globe:before {
  content: "\f0ac";
}
.fa-wrench:before {
  content: "\f0ad";
}
.fa-tasks:before {
  content: "\f0ae";
}
.fa-filter:before {
  content: "\f0b0";
}
.fa-briefcase:before {
  content: "\f0b1";
}
.fa-arrows-alt:before {
  content: "\f0b2";
}
.fa-group:before,
.fa-users:before {
  content: "\f0c0";
}
.fa-chain:before,
.fa-link:before {
  content: "\f0c1";
}
.fa-cloud:before {
  content: "\f0c2";
}
.fa-flask:before {
  content: "\f0c3";
}
.fa-cut:before,
.fa-scissors:before {
  content: "\f0c4";
}
.fa-copy:before,
.fa-files-o:before {
  content: "\f0c5";
}
.fa-paperclip:before {
  content: "\f0c6";
}
.fa-save:before,
.fa-floppy-o:before {
  content: "\f0c7";
}
.fa-square:before {
  content: "\f0c8";
}
.fa-navicon:before,
.fa-reorder:before,
.fa-bars:before {
  content: "\f0c9";
}
.fa-list-ul:before {
  content: "\f0ca";
}
.fa-list-ol:before {
  content: "\f0cb";
}
.fa-strikethrough:before {
  content: "\f0cc";
}
.fa-underline:before {
  content: "\f0cd";
}
.fa-table:before {
  content: "\f0ce";
}
.fa-magic:before {
  content: "\f0d0";
}
.fa-truck:before {
  content: "\f0d1";
}
.fa-pinterest:before {
  content: "\f0d2";
}
.fa-pinterest-square:before {
  content: "\f0d3";
}
.fa-google-plus-square:before {
  content: "\f0d4";
}
.fa-google-plus:before {
  content: "\f0d5";
}
.fa-money:before {
  content: "\f0d6";
}
.fa-caret-down:before {
  content: "\f0d7";
}
.fa-caret-up:before {
  content: "\f0d8";
}
.fa-caret-left:before {
  content: "\f0d9";
}
.fa-caret-right:before {
  content: "\f0da";
}
.fa-columns:before {
  content: "\f0db";
}
.fa-unsorted:before,
.fa-sort:before {
  content: "\f0dc";
}
.fa-sort-down:before,
.fa-sort-desc:before {
  content: "\f0dd";
}
.fa-sort-up:before,
.fa-sort-asc:before {
  content: "\f0de";
}
.fa-envelope:before {
  content: "\f0e0";
}
.fa-linkedin:before {
  content: "\f0e1";
}
.fa-rotate-left:before,
.fa-undo:before {
  content: "\f0e2";
}
.fa-legal:before,
.fa-gavel:before {
  content: "\f0e3";
}
.fa-dashboard:before,
.fa-tachometer:before {
  content: "\f0e4";
}
.fa-comment-o:before {
  content: "\f0e5";
}
.fa-comments-o:before {
  content: "\f0e6";
}
.fa-flash:before,
.fa-bolt:before {
  content: "\f0e7";
}
.fa-sitemap:before {
  content: "\f0e8";
}
.fa-umbrella:before {
  content: "\f0e9";
}
.fa-paste:before,
.fa-clipboard:before {
  content: "\f0ea";
}
.fa-lightbulb-o:before {
  content: "\f0eb";
}
.fa-exchange:before {
  content: "\f0ec";
}
.fa-cloud-download:before {
  content: "\f0ed";
}
.fa-cloud-upload:before {
  content: "\f0ee";
}
.fa-user-md:before {
  content: "\f0f0";
}
.fa-stethoscope:before {
  content: "\f0f1";
}
.fa-suitcase:before {
  content: "\f0f2";
}
.fa-bell-o:before {
  content: "\f0a2";
}
.fa-coffee:before {
  content: "\f0f4";
}
.fa-cutlery:before {
  content: "\f0f5";
}
.fa-file-text-o:before {
  content: "\f0f6";
}
.fa-building-o:before {
  content: "\f0f7";
}
.fa-hospital-o:before {
  content: "\f0f8";
}
.fa-ambulance:before {
  content: "\f0f9";
}
.fa-medkit:before {
  content: "\f0fa";
}
.fa-fighter-jet:before {
  content: "\f0fb";
}
.fa-beer:before {
  content: "\f0fc";
}
.fa-h-square:before {
  content: "\f0fd";
}
.fa-plus-square:before {
  content: "\f0fe";
}
.fa-angle-double-left:before {
  content: "\f100";
}
.fa-angle-double-right:before {
  content: "\f101";
}
.fa-angle-double-up:before {
  content: "\f102";
}
.fa-angle-double-down:before {
  content: "\f103";
}
.fa-angle-left:before {
  content: "\f104";
}
.fa-angle-right:before {
  content: "\f105";
}
.fa-angle-up:before {
  content: "\f106";
}
.fa-angle-down:before {
  content: "\f107";
}
.fa-desktop:before {
  content: "\f108";
}
.fa-laptop:before {
  content: "\f109";
}
.fa-tablet:before {
  content: "\f10a";
}
.fa-mobile-phone:before,
.fa-mobile:before {
  content: "\f10b";
}
.fa-circle-o:before {
  content: "\f10c";
}
.fa-quote-left:before {
  content: "\f10d";
}
.fa-quote-right:before {
  content: "\f10e";
}
.fa-spinner:before {
  content: "\f110";
}
.fa-circle:before {
  content: "\f111";
}
.fa-mail-reply:before,
.fa-reply:before {
  content: "\f112";
}
.fa-github-alt:before {
  content: "\f113";
}
.fa-folder-o:before {
  content: "\f114";
}
.fa-folder-open-o:before {
  content: "\f115";
}
.fa-smile-o:before {
  content: "\f118";
}
.fa-frown-o:before {
  content: "\f119";
}
.fa-meh-o:before {
  content: "\f11a";
}
.fa-gamepad:before {
  content: "\f11b";
}
.fa-keyboard-o:before {
  content: "\f11c";
}
.fa-flag-o:before {
  content: "\f11d";
}
.fa-flag-checkered:before {
  content: "\f11e";
}
.fa-terminal:before {
  content: "\f120";
}
.fa-code:before {
  content: "\f121";
}
.fa-mail-reply-all:before,
.fa-reply-all:before {
  content: "\f122";
}
.fa-star-half-empty:before,
.fa-star-half-full:before,
.fa-star-half-o:before {
  content: "\f123";
}
.fa-location-arrow:before {
  content: "\f124";
}
.fa-crop:before {
  content: "\f125";
}
.fa-code-fork:before {
  content: "\f126";
}
.fa-unlink:before,
.fa-chain-broken:before {
  content: "\f127";
}
.fa-question:before {
  content: "\f128";
}
.fa-info:before {
  content: "\f129";
}
.fa-exclamation:before {
  content: "\f12a";
}
.fa-superscript:before {
  content: "\f12b";
}
.fa-subscript:before {
  content: "\f12c";
}
.fa-eraser:before {
  content: "\f12d";
}
.fa-puzzle-piece:before {
  content: "\f12e";
}
.fa-microphone:before {
  content: "\f130";
}
.fa-microphone-slash:before {
  content: "\f131";
}
.fa-shield:before {
  content: "\f132";
}
.fa-calendar-o:before {
  content: "\f133";
}
.fa-fire-extinguisher:before {
  content: "\f134";
}
.fa-rocket:before {
  content: "\f135";
}
.fa-maxcdn:before {
  content: "\f136";
}
.fa-chevron-circle-left:before {
  content: "\f137";
}
.fa-chevron-circle-right:before {
  content: "\f138";
}
.fa-chevron-circle-up:before {
  content: "\f139";
}
.fa-chevron-circle-down:before {
  content: "\f13a";
}
.fa-html5:before {
  content: "\f13b";
}
.fa-css3:before {
  content: "\f13c";
}
.fa-anchor:before {
  content: "\f13d";
}
.fa-unlock-alt:before {
  content: "\f13e";
}
.fa-bullseye:before {
  content: "\f140";
}
.fa-ellipsis-h:before {
  content: "\f141";
}
.fa-ellipsis-v:before {
  content: "\f142";
}
.fa-rss-square:before {
  content: "\f143";
}
.fa-play-circle:before {
  content: "\f144";
}
.fa-ticket:before {
  content: "\f145";
}
.fa-minus-square:before {
  content: "\f146";
}
.fa-minus-square-o:before {
  content: "\f147";
}
.fa-level-up:before {
  content: "\f148";
}
.fa-level-down:before {
  content: "\f149";
}
.fa-check-square:before {
  content: "\f14a";
}
.fa-pencil-square:before {
  content: "\f14b";
}
.fa-external-link-square:before {
  content: "\f14c";
}
.fa-share-square:before {
  content: "\f14d";
}
.fa-compass:before {
  content: "\f14e";
}
.fa-toggle-down:before,
.fa-caret-square-o-down:before {
  content: "\f150";
}
.fa-toggle-up:before,
.fa-caret-square-o-up:before {
  content: "\f151";
}
.fa-toggle-right:before,
.fa-caret-square-o-right:before {
  content: "\f152";
}
.fa-euro:before,
.fa-eur:before {
  content: "\f153";
}
.fa-gbp:before {
  content: "\f154";
}
.fa-dollar:before,
.fa-usd:before {
  content: "\f155";
}
.fa-rupee:before,
.fa-inr:before {
  content: "\f156";
}
.fa-cny:before,
.fa-rmb:before,
.fa-yen:before,
.fa-jpy:before {
  content: "\f157";
}
.fa-ruble:before,
.fa-rouble:before,
.fa-rub:before {
  content: "\f158";
}
.fa-won:before,
.fa-krw:before {
  content: "\f159";
}
.fa-bitcoin:before,
.fa-btc:before {
  content: "\f15a";
}
.fa-file:before {
  content: "\f15b";
}
.fa-file-text:before {
  content: "\f15c";
}
.fa-sort-alpha-asc:before {
  content: "\f15d";
}
.fa-sort-alpha-desc:before {
  content: "\f15e";
}
.fa-sort-amount-asc:before {
  content: "\f160";
}
.fa-sort-amount-desc:before {
  content: "\f161";
}
.fa-sort-numeric-asc:before {
  content: "\f162";
}
.fa-sort-numeric-desc:before {
  content: "\f163";
}
.fa-thumbs-up:before {
  content: "\f164";
}
.fa-thumbs-down:before {
  content: "\f165";
}
.fa-youtube-square:before {
  content: "\f166";
}
.fa-youtube:before {
  content: "\f167";
}
.fa-xing:before {
  content: "\f168";
}
.fa-xing-square:before {
  content: "\f169";
}
.fa-youtube-play:before {
  content: "\f16a";
}
.fa-dropbox:before {
  content: "\f16b";
}
.fa-stack-overflow:before {
  content: "\f16c";
}
.fa-instagram:before {
  content: "\f16d";
}
.fa-flickr:before {
  content: "\f16e";
}
.fa-adn:before {
  content: "\f170";
}
.fa-bitbucket:before {
  content: "\f171";
}
.fa-bitbucket-square:before {
  content: "\f172";
}
.fa-tumblr:before {
  content: "\f173";
}
.fa-tumblr-square:before {
  content: "\f174";
}
.fa-long-arrow-down:before {
  content: "\f175";
}
.fa-long-arrow-up:before {
  content: "\f176";
}
.fa-long-arrow-left:before {
  content: "\f177";
}
.fa-long-arrow-right:before {
  content: "\f178";
}
.fa-apple:before {
  content: "\f179";
}
.fa-windows:before {
  content: "\f17a";
}
.fa-android:before {
  content: "\f17b";
}
.fa-linux:before {
  content: "\f17c";
}
.fa-dribbble:before {
  content: "\f17d";
}
.fa-skype:before {
  content: "\f17e";
}
.fa-foursquare:before {
  content: "\f180";
}
.fa-trello:before {
  content: "\f181";
}
.fa-female:before {
  content: "\f182";
}
.fa-male:before {
  content: "\f183";
}
.fa-gittip:before,
.fa-gratipay:before {
  content: "\f184";
}
.fa-sun-o:before {
  content: "\f185";
}
.fa-moon-o:before {
  content: "\f186";
}
.fa-archive:before {
  content: "\f187";
}
.fa-bug:before {
  content: "\f188";
}
.fa-vk:before {
  content: "\f189";
}
.fa-weibo:before {
  content: "\f18a";
}
.fa-renren:before {
  content: "\f18b";
}
.fa-pagelines:before {
  content: "\f18c";
}
.fa-stack-exchange:before {
  content: "\f18d";
}
.fa-arrow-circle-o-right:before {
  content: "\f18e";
}
.fa-arrow-circle-o-left:before {
  content: "\f190";
}
.fa-toggle-left:before,
.fa-caret-square-o-left:before {
  content: "\f191";
}
.fa-dot-circle-o:before {
  content: "\f192";
}
.fa-wheelchair:before {
  content: "\f193";
}
.fa-vimeo-square:before {
  content: "\f194";
}
.fa-turkish-lira:before,
.fa-try:before {
  content: "\f195";
}
.fa-plus-square-o:before {
  content: "\f196";
}
.fa-space-shuttle:before {
  content: "\f197";
}
.fa-slack:before {
  content: "\f198";
}
.fa-envelope-square:before {
  content: "\f199";
}
.fa-wordpress:before {
  content: "\f19a";
}
.fa-openid:before {
  content: "\f19b";
}
.fa-institution:before,
.fa-bank:before,
.fa-university:before {
  content: "\f19c";
}
.fa-mortar-board:before,
.fa-graduation-cap:before {
  content: "\f19d";
}
.fa-yahoo:before {
  content: "\f19e";
}
.fa-google:before {
  content: "\f1a0";
}
.fa-reddit:before {
  content: "\f1a1";
}
.fa-reddit-square:before {
  content: "\f1a2";
}
.fa-stumbleupon-circle:before {
  content: "\f1a3";
}
.fa-stumbleupon:before {
  content: "\f1a4";
}
.fa-delicious:before {
  content: "\f1a5";
}
.fa-digg:before {
  content: "\f1a6";
}
.fa-pied-piper-pp:before {
  content: "\f1a7";
}
.fa-pied-piper-alt:before {
  content: "\f1a8";
}
.fa-drupal:before {
  content: "\f1a9";
}
.fa-joomla:before {
  content: "\f1aa";
}
.fa-language:before {
  content: "\f1ab";
}
.fa-fax:before {
  content: "\f1ac";
}
.fa-building:before {
  content: "\f1ad";
}
.fa-child:before {
  content: "\f1ae";
}
.fa-paw:before {
  content: "\f1b0";
}
.fa-spoon:before {
  content: "\f1b1";
}
.fa-cube:before {
  content: "\f1b2";
}
.fa-cubes:before {
  content: "\f1b3";
}
.fa-behance:before {
  content: "\f1b4";
}
.fa-behance-square:before {
  content: "\f1b5";
}
.fa-steam:before {
  content: "\f1b6";
}
.fa-steam-square:before {
  content: "\f1b7";
}
.fa-recycle:before {
  content: "\f1b8";
}
.fa-automobile:before,
.fa-car:before {
  content: "\f1b9";
}
.fa-cab:before,
.fa-taxi:before {
  content: "\f1ba";
}
.fa-tree:before {
  content: "\f1bb";
}
.fa-spotify:before {
  content: "\f1bc";
}
.fa-deviantart:before {
  content: "\f1bd";
}
.fa-soundcloud:before {
  content: "\f1be";
}
.fa-database:before {
  content: "\f1c0";
}
.fa-file-pdf-o:before {
  content: "\f1c1";
}
.fa-file-word-o:before {
  content: "\f1c2";
}
.fa-file-excel-o:before {
  content: "\f1c3";
}
.fa-file-powerpoint-o:before {
  content: "\f1c4";
}
.fa-file-photo-o:before,
.fa-file-picture-o:before,
.fa-file-image-o:before {
  content: "\f1c5";
}
.fa-file-zip-o:before,
.fa-file-archive-o:before {
  content: "\f1c6";
}
.fa-file-sound-o:before,
.fa-file-audio-o:before {
  content: "\f1c7";
}
.fa-file-movie-o:before,
.fa-file-video-o:before {
  content: "\f1c8";
}
.fa-file-code-o:before {
  content: "\f1c9";
}
.fa-vine:before {
  content: "\f1ca";
}
.fa-codepen:before {
  content: "\f1cb";
}
.fa-jsfiddle:before {
  content: "\f1cc";
}
.fa-life-bouy:before,
.fa-life-buoy:before,
.fa-life-saver:before,
.fa-support:before,
.fa-life-ring:before {
  content: "\f1cd";
}
.fa-circle-o-notch:before {
  content: "\f1ce";
}
.fa-ra:before,
.fa-resistance:before,
.fa-rebel:before {
  content: "\f1d0";
}
.fa-ge:before,
.fa-empire:before {
  content: "\f1d1";
}
.fa-git-square:before {
  content: "\f1d2";
}
.fa-git:before {
  content: "\f1d3";
}
.fa-y-combinator-square:before,
.fa-yc-square:before,
.fa-hacker-news:before {
  content: "\f1d4";
}
.fa-tencent-weibo:before {
  content: "\f1d5";
}
.fa-qq:before {
  content: "\f1d6";
}
.fa-wechat:before,
.fa-weixin:before {
  content: "\f1d7";
}
.fa-send:before,
.fa-paper-plane:before {
  content: "\f1d8";
}
.fa-send-o:before,
.fa-paper-plane-o:before {
  content: "\f1d9";
}
.fa-history:before {
  content: "\f1da";
}
.fa-circle-thin:before {
  content: "\f1db";
}
.fa-header:before {
  content: "\f1dc";
}
.fa-paragraph:before {
  content: "\f1dd";
}
.fa-sliders:before {
  content: "\f1de";
}
.fa-share-alt:before {
  content: "\f1e0";
}
.fa-share-alt-square:before {
  content: "\f1e1";
}
.fa-bomb:before {
  content: "\f1e2";
}
.fa-soccer-ball-o:before,
.fa-futbol-o:before {
  content: "\f1e3";
}
.fa-tty:before {
  content: "\f1e4";
}
.fa-binoculars:before {
  content: "\f1e5";
}
.fa-plug:before {
  content: "\f1e6";
}
.fa-slideshare:before {
  content: "\f1e7";
}
.fa-twitch:before {
  content: "\f1e8";
}
.fa-yelp:before {
  content: "\f1e9";
}
.fa-newspaper-o:before {
  content: "\f1ea";
}
.fa-wifi:before {
  content: "\f1eb";
}
.fa-calculator:before {
  content: "\f1ec";
}
.fa-paypal:before {
  content: "\f1ed";
}
.fa-google-wallet:before {
  content: "\f1ee";
}
.fa-cc-visa:before {
  content: "\f1f0";
}
.fa-cc-mastercard:before {
  content: "\f1f1";
}
.fa-cc-discover:before {
  content: "\f1f2";
}
.fa-cc-amex:before {
  content: "\f1f3";
}
.fa-cc-paypal:before {
  content: "\f1f4";
}
.fa-cc-stripe:before {
  content: "\f1f5";
}
.fa-bell-slash:before {
  content: "\f1f6";
}
.fa-bell-slash-o:before {
  content: "\f1f7";
}
.fa-trash:before {
  content: "\f1f8";
}
.fa-copyright:before {
  content: "\f1f9";
}
.fa-at:before {
  content: "\f1fa";
}
.fa-eyedropper:before {
  content: "\f1fb";
}
.fa-paint-brush:before {
  content: "\f1fc";
}
.fa-birthday-cake:before {
  content: "\f1fd";
}
.fa-area-chart:before {
  content: "\f1fe";
}
.fa-pie-chart:before {
  content: "\f200";
}
.fa-line-chart:before {
  content: "\f201";
}
.fa-lastfm:before {
  content: "\f202";
}
.fa-lastfm-square:before {
  content: "\f203";
}
.fa-toggle-off:before {
  content: "\f204";
}
.fa-toggle-on:before {
  content: "\f205";
}
.fa-bicycle:before {
  content: "\f206";
}
.fa-bus:before {
  content: "\f207";
}
.fa-ioxhost:before {
  content: "\f208";
}
.fa-angellist:before {
  content: "\f209";
}
.fa-cc:before {
  content: "\f20a";
}
.fa-shekel:before,
.fa-sheqel:before,
.fa-ils:before {
  content: "\f20b";
}
.fa-meanpath:before {
  content: "\f20c";
}
.fa-buysellads:before {
  content: "\f20d";
}
.fa-connectdevelop:before {
  content: "\f20e";
}
.fa-dashcube:before {
  content: "\f210";
}
.fa-forumbee:before {
  content: "\f211";
}
.fa-leanpub:before {
  content: "\f212";
}
.fa-sellsy:before {
  content: "\f213";
}
.fa-shirtsinbulk:before {
  content: "\f214";
}
.fa-simplybuilt:before {
  content: "\f215";
}
.fa-skyatlas:before {
  content: "\f216";
}
.fa-cart-plus:before {
  content: "\f217";
}
.fa-cart-arrow-down:before {
  content: "\f218";
}
.fa-diamond:before {
  content: "\f219";
}
.fa-ship:before {
  content: "\f21a";
}
.fa-user-secret:before {
  content: "\f21b";
}
.fa-motorcycle:before {
  content: "\f21c";
}
.fa-street-view:before {
  content: "\f21d";
}
.fa-heartbeat:before {
  content: "\f21e";
}
.fa-venus:before {
  content: "\f221";
}
.fa-mars:before {
  content: "\f222";
}
.fa-mercury:before {
  content: "\f223";
}
.fa-intersex:before,
.fa-transgender:before {
  content: "\f224";
}
.fa-transgender-alt:before {
  content: "\f225";
}
.fa-venus-double:before {
  content: "\f226";
}
.fa-mars-double:before {
  content: "\f227";
}
.fa-venus-mars:before {
  content: "\f228";
}
.fa-mars-stroke:before {
  content: "\f229";
}
.fa-mars-stroke-v:before {
  content: "\f22a";
}
.fa-mars-stroke-h:before {
  content: "\f22b";
}
.fa-neuter:before {
  content: "\f22c";
}
.fa-genderless:before {
  content: "\f22d";
}
.fa-facebook-official:before {
  content: "\f230";
}
.fa-pinterest-p:before {
  content: "\f231";
}
.fa-whatsapp:before {
  content: "\f232";
}
.fa-server:before {
  content: "\f233";
}
.fa-user-plus:before {
  content: "\f234";
}
.fa-user-times:before {
  content: "\f235";
}
.fa-hotel:before,
.fa-bed:before {
  content: "\f236";
}
.fa-viacoin:before {
  content: "\f237";
}
.fa-train:before {
  content: "\f238";
}
.fa-subway:before {
  content: "\f239";
}
.fa-medium:before {
  content: "\f23a";
}
.fa-yc:before,
.fa-y-combinator:before {
  content: "\f23b";
}
.fa-optin-monster:before {
  content: "\f23c";
}
.fa-opencart:before {
  content: "\f23d";
}
.fa-expeditedssl:before {
  content: "\f23e";
}
.fa-battery-4:before,
.fa-battery:before,
.fa-battery-full:before {
  content: "\f240";
}
.fa-battery-3:before,
.fa-battery-three-quarters:before {
  content: "\f241";
}
.fa-battery-2:before,
.fa-battery-half:before {
  content: "\f242";
}
.fa-battery-1:before,
.fa-battery-quarter:before {
  content: "\f243";
}
.fa-battery-0:before,
.fa-battery-empty:before {
  content: "\f244";
}
.fa-mouse-pointer:before {
  content: "\f245";
}
.fa-i-cursor:before {
  content: "\f246";
}
.fa-object-group:before {
  content: "\f247";
}
.fa-object-ungroup:before {
  content: "\f248";
}
.fa-sticky-note:before {
  content: "\f249";
}
.fa-sticky-note-o:before {
  content: "\f24a";
}
.fa-cc-jcb:before {
  content: "\f24b";
}
.fa-cc-diners-club:before {
  content: "\f24c";
}
.fa-clone:before {
  content: "\f24d";
}
.fa-balance-scale:before {
  content: "\f24e";
}
.fa-hourglass-o:before {
  content: "\f250";
}
.fa-hourglass-1:before,
.fa-hourglass-start:before {
  content: "\f251";
}
.fa-hourglass-2:before,
.fa-hourglass-half:before {
  content: "\f252";
}
.fa-hourglass-3:before,
.fa-hourglass-end:before {
  content: "\f253";
}
.fa-hourglass:before {
  content: "\f254";
}
.fa-hand-grab-o:before,
.fa-hand-rock-o:before {
  content: "\f255";
}
.fa-hand-stop-o:before,
.fa-hand-paper-o:before {
  content: "\f256";
}
.fa-hand-scissors-o:before {
  content: "\f257";
}
.fa-hand-lizard-o:before {
  content: "\f258";
}
.fa-hand-spock-o:before {
  content: "\f259";
}
.fa-hand-pointer-o:before {
  content: "\f25a";
}
.fa-hand-peace-o:before {
  content: "\f25b";
}
.fa-trademark:before {
  content: "\f25c";
}
.fa-registered:before {
  content: "\f25d";
}
.fa-creative-commons:before {
  content: "\f25e";
}
.fa-gg:before {
  content: "\f260";
}
.fa-gg-circle:before {
  content: "\f261";
}
.fa-tripadvisor:before {
  content: "\f262";
}
.fa-odnoklassniki:before {
  content: "\f263";
}
.fa-odnoklassniki-square:before {
  content: "\f264";
}
.fa-get-pocket:before {
  content: "\f265";
}
.fa-wikipedia-w:before {
  content: "\f266";
}
.fa-safari:before {
  content: "\f267";
}
.fa-chrome:before {
  content: "\f268";
}
.fa-firefox:before {
  content: "\f269";
}
.fa-opera:before {
  content: "\f26a";
}
.fa-internet-explorer:before {
  content: "\f26b";
}
.fa-tv:before,
.fa-television:before {
  content: "\f26c";
}
.fa-contao:before {
  content: "\f26d";
}
.fa-500px:before {
  content: "\f26e";
}
.fa-amazon:before {
  content: "\f270";
}
.fa-calendar-plus-o:before {
  content: "\f271";
}
.fa-calendar-minus-o:before {
  content: "\f272";
}
.fa-calendar-times-o:before {
  content: "\f273";
}
.fa-calendar-check-o:before {
  content: "\f274";
}
.fa-industry:before {
  content: "\f275";
}
.fa-map-pin:before {
  content: "\f276";
}
.fa-map-signs:before {
  content: "\f277";
}
.fa-map-o:before {
  content: "\f278";
}
.fa-map:before {
  content: "\f279";
}
.fa-commenting:before {
  content: "\f27a";
}
.fa-commenting-o:before {
  content: "\f27b";
}
.fa-houzz:before {
  content: "\f27c";
}
.fa-vimeo:before {
  content: "\f27d";
}
.fa-black-tie:before {
  content: "\f27e";
}
.fa-fonticons:before {
  content: "\f280";
}
.fa-reddit-alien:before {
  content: "\f281";
}
.fa-edge:before {
  content: "\f282";
}
.fa-credit-card-alt:before {
  content: "\f283";
}
.fa-codiepie:before {
  content: "\f284";
}
.fa-modx:before {
  content: "\f285";
}
.fa-fort-awesome:before {
  content: "\f286";
}
.fa-usb:before {
  content: "\f287";
}
.fa-product-hunt:before {
  content: "\f288";
}
.fa-mixcloud:before {
  content: "\f289";
}
.fa-scribd:before {
  content: "\f28a";
}
.fa-pause-circle:before {
  content: "\f28b";
}
.fa-pause-circle-o:before {
  content: "\f28c";
}
.fa-stop-circle:before {
  content: "\f28d";
}
.fa-stop-circle-o:before {
  content: "\f28e";
}
.fa-shopping-bag:before {
  content: "\f290";
}
.fa-shopping-basket:before {
  content: "\f291";
}
.fa-hashtag:before {
  content: "\f292";
}
.fa-bluetooth:before {
  content: "\f293";
}
.fa-bluetooth-b:before {
  content: "\f294";
}
.fa-percent:before {
  content: "\f295";
}
.fa-gitlab:before {
  content: "\f296";
}
.fa-wpbeginner:before {
  content: "\f297";
}
.fa-wpforms:before {
  content: "\f298";
}
.fa-envira:before {
  content: "\f299";
}
.fa-universal-access:before {
  content: "\f29a";
}
.fa-wheelchair-alt:before {
  content: "\f29b";
}
.fa-question-circle-o:before {
  content: "\f29c";
}
.fa-blind:before {
  content: "\f29d";
}
.fa-audio-description:before {
  content: "\f29e";
}
.fa-volume-control-phone:before {
  content: "\f2a0";
}
.fa-braille:before {
  content: "\f2a1";
}
.fa-assistive-listening-systems:before {
  content: "\f2a2";
}
.fa-asl-interpreting:before,
.fa-american-sign-language-interpreting:before {
  content: "\f2a3";
}
.fa-deafness:before,
.fa-hard-of-hearing:before,
.fa-deaf:before {
  content: "\f2a4";
}
.fa-glide:before {
  content: "\f2a5";
}
.fa-glide-g:before {
  content: "\f2a6";
}
.fa-signing:before,
.fa-sign-language:before {
  content: "\f2a7";
}
.fa-low-vision:before {
  content: "\f2a8";
}
.fa-viadeo:before {
  content: "\f2a9";
}
.fa-viadeo-square:before {
  content: "\f2aa";
}
.fa-snapchat:before {
  content: "\f2ab";
}
.fa-snapchat-ghost:before {
  content: "\f2ac";
}
.fa-snapchat-square:before {
  content: "\f2ad";
}
.fa-pied-piper:before {
  content: "\f2ae";
}
.fa-first-order:before {
  content: "\f2b0";
}
.fa-yoast:before {
  content: "\f2b1";
}
.fa-themeisle:before {
  content: "\f2b2";
}
.fa-google-plus-circle:before,
.fa-google-plus-official:before {
  content: "\f2b3";
}
.fa-fa:before,
.fa-font-awesome:before {
  content: "\f2b4";
}
.fa-handshake-o:before {
  content: "\f2b5";
}
.fa-envelope-open:before {
  content: "\f2b6";
}
.fa-envelope-open-o:before {
  content: "\f2b7";
}
.fa-linode:before {
  content: "\f2b8";
}
.fa-address-book:before {
  content: "\f2b9";
}
.fa-address-book-o:before {
  content: "\f2ba";
}
.fa-vcard:before,
.fa-address-card:before {
  content: "\f2bb";
}
.fa-vcard-o:before,
.fa-address-card-o:before {
  content: "\f2bc";
}
.fa-user-circle:before {
  content: "\f2bd";
}
.fa-user-circle-o:before {
  content: "\f2be";
}
.fa-user-o:before {
  content: "\f2c0";
}
.fa-id-badge:before {
  content: "\f2c1";
}
.fa-drivers-license:before,
.fa-id-card:before {
  content: "\f2c2";
}
.fa-drivers-license-o:before,
.fa-id-card-o:before {
  content: "\f2c3";
}
.fa-quora:before {
  content: "\f2c4";
}
.fa-free-code-camp:before {
  content: "\f2c5";
}
.fa-telegram:before {
  content: "\f2c6";
}
.fa-thermometer-4:before,
.fa-thermometer:before,
.fa-thermometer-full:before {
  content: "\f2c7";
}
.fa-thermometer-3:before,
.fa-thermometer-three-quarters:before {
  content: "\f2c8";
}
.fa-thermometer-2:before,
.fa-thermometer-half:before {
  content: "\f2c9";
}
.fa-thermometer-1:before,
.fa-thermometer-quarter:before {
  content: "\f2ca";
}
.fa-thermometer-0:before,
.fa-thermometer-empty:before {
  content: "\f2cb";
}
.fa-shower:before {
  content: "\f2cc";
}
.fa-bathtub:before,
.fa-s15:before,
.fa-bath:before {
  content: "\f2cd";
}
.fa-podcast:before {
  content: "\f2ce";
}
.fa-window-maximize:before {
  content: "\f2d0";
}
.fa-window-minimize:before {
  content: "\f2d1";
}
.fa-window-restore:before {
  content: "\f2d2";
}
.fa-times-rectangle:before,
.fa-window-close:before {
  content: "\f2d3";
}
.fa-times-rectangle-o:before,
.fa-window-close-o:before {
  content: "\f2d4";
}
.fa-bandcamp:before {
  content: "\f2d5";
}
.fa-grav:before {
  content: "\f2d6";
}
.fa-etsy:before {
  content: "\f2d7";
}
.fa-imdb:before {
  content: "\f2d8";
}
.fa-ravelry:before {
  content: "\f2d9";
}
.fa-eercast:before {
  content: "\f2da";
}
.fa-microchip:before {
  content: "\f2db";
}
.fa-snowflake-o:before {
  content: "\f2dc";
}
.fa-superpowers:before {
  content: "\f2dd";
}
.fa-wpexplorer:before {
  content: "\f2de";
}
.fa-meetup:before {
  content: "\f2e0";
}
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  border: 0;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
.sr-only-focusable:active,
.sr-only-focusable:focus {
  position: static;
  width: auto;
  height: auto;
  margin: 0;
  overflow: visible;
  clip: auto;
}
/*!
*
* IPython base
*
*/
.modal.fade .modal-dialog {
  -webkit-transform: translate(0, 0);
  -ms-transform: translate(0, 0);
  -o-transform: translate(0, 0);
  transform: translate(0, 0);
}
code {
  color: #000;
}
pre {
  font-size: inherit;
  line-height: inherit;
}
label {
  font-weight: normal;
}
/* Make the page background atleast 100% the height of the view port */
/* Make the page itself atleast 70% the height of the view port */
.border-box-sizing {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.corner-all {
  border-radius: 2px;
}
.no-padding {
  padding: 0px;
}
/* Flexible box model classes */
/* Taken from Alex Russell http://infrequently.org/2009/08/css-3-progress/ */
/* This file is a compatability layer.  It allows the usage of flexible box 
model layouts accross multiple browsers, including older browsers.  The newest,
universal implementation of the flexible box model is used when available (see
`Modern browsers` comments below).  Browsers that are known to implement this 
new spec completely include:

    Firefox 28.0+
    Chrome 29.0+
    Internet Explorer 11+ 
    Opera 17.0+

Browsers not listed, including Safari, are supported via the styling under the
`Old browsers` comments below.
*/
.hbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
.hbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.vbox {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
.vbox > * {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
}
.hbox.reverse,
.vbox.reverse,
.reverse {
  /* Old browsers */
  -webkit-box-direction: reverse;
  -moz-box-direction: reverse;
  box-direction: reverse;
  /* Modern browsers */
  flex-direction: row-reverse;
}
.hbox.box-flex0,
.vbox.box-flex0,
.box-flex0 {
  /* Old browsers */
  -webkit-box-flex: 0;
  -moz-box-flex: 0;
  box-flex: 0;
  /* Modern browsers */
  flex: none;
  width: auto;
}
.hbox.box-flex1,
.vbox.box-flex1,
.box-flex1 {
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex,
.vbox.box-flex,
.box-flex {
  /* Old browsers */
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
.hbox.box-flex2,
.vbox.box-flex2,
.box-flex2 {
  /* Old browsers */
  -webkit-box-flex: 2;
  -moz-box-flex: 2;
  box-flex: 2;
  /* Modern browsers */
  flex: 2;
}
.box-group1 {
  /*  Deprecated */
  -webkit-box-flex-group: 1;
  -moz-box-flex-group: 1;
  box-flex-group: 1;
}
.box-group2 {
  /* Deprecated */
  -webkit-box-flex-group: 2;
  -moz-box-flex-group: 2;
  box-flex-group: 2;
}
.hbox.start,
.vbox.start,
.start {
  /* Old browsers */
  -webkit-box-pack: start;
  -moz-box-pack: start;
  box-pack: start;
  /* Modern browsers */
  justify-content: flex-start;
}
.hbox.end,
.vbox.end,
.end {
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
}
.hbox.center,
.vbox.center,
.center {
  /* Old browsers */
  -webkit-box-pack: center;
  -moz-box-pack: center;
  box-pack: center;
  /* Modern browsers */
  justify-content: center;
}
.hbox.baseline,
.vbox.baseline,
.baseline {
  /* Old browsers */
  -webkit-box-pack: baseline;
  -moz-box-pack: baseline;
  box-pack: baseline;
  /* Modern browsers */
  justify-content: baseline;
}
.hbox.stretch,
.vbox.stretch,
.stretch {
  /* Old browsers */
  -webkit-box-pack: stretch;
  -moz-box-pack: stretch;
  box-pack: stretch;
  /* Modern browsers */
  justify-content: stretch;
}
.hbox.align-start,
.vbox.align-start,
.align-start {
  /* Old browsers */
  -webkit-box-align: start;
  -moz-box-align: start;
  box-align: start;
  /* Modern browsers */
  align-items: flex-start;
}
.hbox.align-end,
.vbox.align-end,
.align-end {
  /* Old browsers */
  -webkit-box-align: end;
  -moz-box-align: end;
  box-align: end;
  /* Modern browsers */
  align-items: flex-end;
}
.hbox.align-center,
.vbox.align-center,
.align-center {
  /* Old browsers */
  -webkit-box-align: center;
  -moz-box-align: center;
  box-align: center;
  /* Modern browsers */
  align-items: center;
}
.hbox.align-baseline,
.vbox.align-baseline,
.align-baseline {
  /* Old browsers */
  -webkit-box-align: baseline;
  -moz-box-align: baseline;
  box-align: baseline;
  /* Modern browsers */
  align-items: baseline;
}
.hbox.align-stretch,
.vbox.align-stretch,
.align-stretch {
  /* Old browsers */
  -webkit-box-align: stretch;
  -moz-box-align: stretch;
  box-align: stretch;
  /* Modern browsers */
  align-items: stretch;
}
div.error {
  margin: 2em;
  text-align: center;
}
div.error > h1 {
  font-size: 500%;
  line-height: normal;
}
div.error > p {
  font-size: 200%;
  line-height: normal;
}
div.traceback-wrapper {
  text-align: left;
  max-width: 800px;
  margin: auto;
}
div.traceback-wrapper pre.traceback {
  max-height: 600px;
  overflow: auto;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
body {
  background-color: #fff;
  /* This makes sure that the body covers the entire window and needs to
       be in a different element than the display: box in wrapper below */
  position: absolute;
  left: 0px;
  right: 0px;
  top: 0px;
  bottom: 0px;
  overflow: visible;
}
body > #header {
  /* Initially hidden to prevent FLOUC */
  display: none;
  background-color: #fff;
  /* Display over codemirror */
  position: relative;
  z-index: 100;
}
body > #header #header-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding: 5px;
  padding-bottom: 5px;
  padding-top: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
body > #header .header-bar {
  width: 100%;
  height: 1px;
  background: #e7e7e7;
  margin-bottom: -1px;
}
@media print {
  body > #header {
    display: none !important;
  }
}
#header-spacer {
  width: 100%;
  visibility: hidden;
}
@media print {
  #header-spacer {
    display: none;
  }
}
#ipython_notebook {
  padding-left: 0px;
  padding-top: 1px;
  padding-bottom: 1px;
}
[dir="rtl"] #ipython_notebook {
  margin-right: 10px;
  margin-left: 0;
}
[dir="rtl"] #ipython_notebook.pull-left {
  float: right !important;
  float: right;
}
.flex-spacer {
  flex: 1;
}
#noscript {
  width: auto;
  padding-top: 16px;
  padding-bottom: 16px;
  text-align: center;
  font-size: 22px;
  color: red;
  font-weight: bold;
}
#ipython_notebook img {
  height: 28px;
}
#site {
  width: 100%;
  display: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  overflow: auto;
}
@media print {
  #site {
    height: auto !important;
  }
}
/* Smaller buttons */
.ui-button .ui-button-text {
  padding: 0.2em 0.8em;
  font-size: 77%;
}
input.ui-button {
  padding: 0.3em 0.9em;
}
span#kernel_logo_widget {
  margin: 0 10px;
}
span#login_widget {
  float: right;
}
[dir="rtl"] span#login_widget {
  float: left;
}
span#login_widget > .button,
#logout {
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button:focus,
#logout:focus,
span#login_widget > .button.focus,
#logout.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
span#login_widget > .button:hover,
#logout:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
span#login_widget > .button:active:hover,
#logout:active:hover,
span#login_widget > .button.active:hover,
#logout.active:hover,
.open > .dropdown-togglespan#login_widget > .button:hover,
.open > .dropdown-toggle#logout:hover,
span#login_widget > .button:active:focus,
#logout:active:focus,
span#login_widget > .button.active:focus,
#logout.active:focus,
.open > .dropdown-togglespan#login_widget > .button:focus,
.open > .dropdown-toggle#logout:focus,
span#login_widget > .button:active.focus,
#logout:active.focus,
span#login_widget > .button.active.focus,
#logout.active.focus,
.open > .dropdown-togglespan#login_widget > .button.focus,
.open > .dropdown-toggle#logout.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
span#login_widget > .button:active,
#logout:active,
span#login_widget > .button.active,
#logout.active,
.open > .dropdown-togglespan#login_widget > .button,
.open > .dropdown-toggle#logout {
  background-image: none;
}
span#login_widget > .button.disabled:hover,
#logout.disabled:hover,
span#login_widget > .button[disabled]:hover,
#logout[disabled]:hover,
fieldset[disabled] span#login_widget > .button:hover,
fieldset[disabled] #logout:hover,
span#login_widget > .button.disabled:focus,
#logout.disabled:focus,
span#login_widget > .button[disabled]:focus,
#logout[disabled]:focus,
fieldset[disabled] span#login_widget > .button:focus,
fieldset[disabled] #logout:focus,
span#login_widget > .button.disabled.focus,
#logout.disabled.focus,
span#login_widget > .button[disabled].focus,
#logout[disabled].focus,
fieldset[disabled] span#login_widget > .button.focus,
fieldset[disabled] #logout.focus {
  background-color: #fff;
  border-color: #ccc;
}
span#login_widget > .button .badge,
#logout .badge {
  color: #fff;
  background-color: #333;
}
.nav-header {
  text-transform: none;
}
#header > span {
  margin-top: 10px;
}
.modal_stretch .modal-dialog {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  min-height: 80vh;
}
.modal_stretch .modal-dialog .modal-body {
  max-height: calc(100vh - 200px);
  overflow: auto;
  flex: 1;
}
.modal-header {
  cursor: move;
}
@media (min-width: 768px) {
  .modal .modal-dialog {
    width: 700px;
  }
}
@media (min-width: 768px) {
  select.form-control {
    margin-left: 12px;
    margin-right: 12px;
  }
}
/*!
*
* IPython auth
*
*/
.center-nav {
  display: inline-block;
  margin-bottom: -4px;
}
[dir="rtl"] .center-nav form.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] .center-nav .navbar-text {
  float: right;
}
[dir="rtl"] .navbar-inner {
  text-align: right;
}
[dir="rtl"] div.text-left {
  text-align: right;
}
/*!
*
* IPython tree view
*
*/
/* We need an invisible input field on top of the sentense*/
/* "Drag file onto the list ..." */
.alternate_upload {
  background-color: none;
  display: inline;
}
.alternate_upload.form {
  padding: 0;
  margin: 0;
}
.alternate_upload input.fileinput {
  position: absolute;
  display: block;
  width: 100%;
  height: 100%;
  overflow: hidden;
  cursor: pointer;
  opacity: 0;
  z-index: 2;
}
.alternate_upload .btn-xs > input.fileinput {
  margin: -1px -5px;
}
.alternate_upload .btn-upload {
  position: relative;
  height: 22px;
}
::-webkit-file-upload-button {
  cursor: pointer;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
ul#tabs {
  margin-bottom: 4px;
}
ul#tabs a {
  padding-top: 6px;
  padding-bottom: 4px;
}
[dir="rtl"] ul#tabs.nav-tabs > li {
  float: right;
}
[dir="rtl"] ul#tabs.nav.nav-tabs {
  padding-right: 0;
}
ul.breadcrumb a:focus,
ul.breadcrumb a:hover {
  text-decoration: none;
}
ul.breadcrumb i.icon-home {
  font-size: 16px;
  margin-right: 4px;
}
ul.breadcrumb span {
  color: #5e5e5e;
}
.list_toolbar {
  padding: 4px 0 4px 0;
  vertical-align: middle;
}
.list_toolbar .tree-buttons {
  padding-top: 1px;
}
[dir="rtl"] .list_toolbar .tree-buttons .pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .list_toolbar .col-sm-4,
[dir="rtl"] .list_toolbar .col-sm-8 {
  float: right;
}
.dynamic-buttons {
  padding-top: 3px;
  display: inline-block;
}
.list_toolbar [class*="span"] {
  min-height: 24px;
}
.list_header {
  font-weight: bold;
  background-color: #EEE;
}
.list_placeholder {
  font-weight: bold;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
}
.list_container {
  margin-top: 4px;
  margin-bottom: 20px;
  border: 1px solid #ddd;
  border-radius: 2px;
}
.list_container > div {
  border-bottom: 1px solid #ddd;
}
.list_container > div:hover .list-item {
  background-color: red;
}
.list_container > div:last-child {
  border: none;
}
.list_item:hover .list_item {
  background-color: #ddd;
}
.list_item a {
  text-decoration: none;
}
.list_item:hover {
  background-color: #fafafa;
}
.list_header > div,
.list_item > div {
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
.list_header > div input,
.list_item > div input {
  margin-right: 7px;
  margin-left: 14px;
  vertical-align: text-bottom;
  line-height: 22px;
  position: relative;
  top: -1px;
}
.list_header > div .item_link,
.list_item > div .item_link {
  margin-left: -1px;
  vertical-align: baseline;
  line-height: 22px;
}
[dir="rtl"] .list_item > div input {
  margin-right: 0;
}
.new-file input[type=checkbox] {
  visibility: hidden;
}
.item_name {
  line-height: 22px;
  height: 24px;
}
.item_icon {
  font-size: 14px;
  color: #5e5e5e;
  margin-right: 7px;
  margin-left: 7px;
  line-height: 22px;
  vertical-align: baseline;
}
.item_modified {
  margin-right: 7px;
  margin-left: 7px;
}
[dir="rtl"] .item_modified.pull-right {
  float: left !important;
  float: left;
}
.item_buttons {
  line-height: 1em;
  margin-left: -5px;
}
.item_buttons .btn,
.item_buttons .btn-group,
.item_buttons .input-group {
  float: left;
}
.item_buttons > .btn,
.item_buttons > .btn-group,
.item_buttons > .input-group {
  margin-left: 5px;
}
.item_buttons .btn {
  min-width: 13ex;
}
.item_buttons .running-indicator {
  padding-top: 4px;
  color: #5cb85c;
}
.item_buttons .kernel-name {
  padding-top: 4px;
  color: #5bc0de;
  margin-right: 7px;
  float: left;
}
[dir="rtl"] .item_buttons.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .item_buttons .kernel-name {
  margin-left: 7px;
  float: right;
}
.toolbar_info {
  height: 24px;
  line-height: 24px;
}
.list_item input:not([type=checkbox]) {
  padding-top: 3px;
  padding-bottom: 3px;
  height: 22px;
  line-height: 14px;
  margin: 0px;
}
.highlight_text {
  color: blue;
}
#project_name {
  display: inline-block;
  padding-left: 7px;
  margin-left: -2px;
}
#project_name > .breadcrumb {
  padding: 0px;
  margin-bottom: 0px;
  background-color: transparent;
  font-weight: bold;
}
.sort_button {
  display: inline-block;
  padding-left: 7px;
}
[dir="rtl"] .sort_button.pull-right {
  float: left !important;
  float: left;
}
#tree-selector {
  padding-right: 0px;
}
#button-select-all {
  min-width: 50px;
}
[dir="rtl"] #button-select-all.btn {
  float: right ;
}
#select-all {
  margin-left: 7px;
  margin-right: 2px;
  margin-top: 2px;
  height: 16px;
}
[dir="rtl"] #select-all.pull-left {
  float: right !important;
  float: right;
}
.menu_icon {
  margin-right: 2px;
}
.tab-content .row {
  margin-left: 0px;
  margin-right: 0px;
}
.folder_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f114";
}
.folder_icon:before.fa-pull-left {
  margin-right: .3em;
}
.folder_icon:before.fa-pull-right {
  margin-left: .3em;
}
.folder_icon:before.pull-left {
  margin-right: .3em;
}
.folder_icon:before.pull-right {
  margin-left: .3em;
}
.notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
}
.notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.notebook_icon:before.pull-left {
  margin-right: .3em;
}
.notebook_icon:before.pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f02d";
  position: relative;
  top: -1px;
  color: #5cb85c;
}
.running_notebook_icon:before.fa-pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.fa-pull-right {
  margin-left: .3em;
}
.running_notebook_icon:before.pull-left {
  margin-right: .3em;
}
.running_notebook_icon:before.pull-right {
  margin-left: .3em;
}
.file_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f016";
  position: relative;
  top: -2px;
}
.file_icon:before.fa-pull-left {
  margin-right: .3em;
}
.file_icon:before.fa-pull-right {
  margin-left: .3em;
}
.file_icon:before.pull-left {
  margin-right: .3em;
}
.file_icon:before.pull-right {
  margin-left: .3em;
}
#notebook_toolbar .pull-right {
  padding-top: 0px;
  margin-right: -1px;
}
ul#new-menu {
  left: auto;
  right: 0;
}
#new-menu .dropdown-header {
  font-size: 10px;
  border-bottom: 1px solid #e5e5e5;
  padding: 0 0 3px;
  margin: -3px 20px 0;
}
.kernel-menu-icon {
  padding-right: 12px;
  width: 24px;
  content: "\f096";
}
.kernel-menu-icon:before {
  content: "\f096";
}
.kernel-menu-icon-current:before {
  content: "\f00c";
}
#tab_content {
  padding-top: 20px;
}
#running .panel-group .panel {
  margin-top: 3px;
  margin-bottom: 1em;
}
#running .panel-group .panel .panel-heading {
  background-color: #EEE;
  padding-top: 4px;
  padding-bottom: 4px;
  padding-left: 7px;
  padding-right: 7px;
  line-height: 22px;
}
#running .panel-group .panel .panel-heading a:focus,
#running .panel-group .panel .panel-heading a:hover {
  text-decoration: none;
}
#running .panel-group .panel .panel-body {
  padding: 0px;
}
#running .panel-group .panel .panel-body .list_container {
  margin-top: 0px;
  margin-bottom: 0px;
  border: 0px;
  border-radius: 0px;
}
#running .panel-group .panel .panel-body .list_container .list_item {
  border-bottom: 1px solid #ddd;
}
#running .panel-group .panel .panel-body .list_container .list_item:last-child {
  border-bottom: 0px;
}
.delete-button {
  display: none;
}
.duplicate-button {
  display: none;
}
.rename-button {
  display: none;
}
.move-button {
  display: none;
}
.download-button {
  display: none;
}
.shutdown-button {
  display: none;
}
.dynamic-instructions {
  display: inline-block;
  padding-top: 4px;
}
/*!
*
* IPython text editor webapp
*
*/
.selected-keymap i.fa {
  padding: 0px 5px;
}
.selected-keymap i.fa:before {
  content: "\f00c";
}
#mode-menu {
  overflow: auto;
  max-height: 20em;
}
.edit_app #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.edit_app #menubar .navbar {
  /* Use a negative 1 bottom margin, so the border overlaps the border of the
    header */
  margin-bottom: -1px;
}
.dirty-indicator {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator.pull-left {
  margin-right: .3em;
}
.dirty-indicator.pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-dirty.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-dirty.pull-left {
  margin-right: .3em;
}
.dirty-indicator-dirty.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  width: 20px;
}
.dirty-indicator-clean.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean.pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f00c";
}
.dirty-indicator-clean:before.fa-pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.fa-pull-right {
  margin-left: .3em;
}
.dirty-indicator-clean:before.pull-left {
  margin-right: .3em;
}
.dirty-indicator-clean:before.pull-right {
  margin-left: .3em;
}
#filename {
  font-size: 16pt;
  display: table;
  padding: 0px 5px;
}
#current-mode {
  padding-left: 5px;
  padding-right: 5px;
}
#texteditor-backdrop {
  padding-top: 20px;
  padding-bottom: 20px;
}
@media not print {
  #texteditor-backdrop {
    background-color: #EEE;
  }
}
@media print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container .CodeMirror-gutter,
  #texteditor-backdrop #texteditor-container .CodeMirror-gutters {
    background-color: #fff;
  }
}
@media not print {
  #texteditor-backdrop #texteditor-container {
    padding: 0px;
    background-color: #fff;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
.CodeMirror-dialog {
  background-color: #fff;
}
/*!
*
* IPython notebook
*
*/
/* CSS font colors for translated ANSI escape sequences */
/* The color values are a mix of
   http://www.xcolors.net/dl/baskerville-ivorylight and
   http://www.xcolors.net/dl/euphrasia */
.ansi-black-fg {
  color: #3E424D;
}
.ansi-black-bg {
  background-color: #3E424D;
}
.ansi-black-intense-fg {
  color: #282C36;
}
.ansi-black-intense-bg {
  background-color: #282C36;
}
.ansi-red-fg {
  color: #E75C58;
}
.ansi-red-bg {
  background-color: #E75C58;
}
.ansi-red-intense-fg {
  color: #B22B31;
}
.ansi-red-intense-bg {
  background-color: #B22B31;
}
.ansi-green-fg {
  color: #00A250;
}
.ansi-green-bg {
  background-color: #00A250;
}
.ansi-green-intense-fg {
  color: #007427;
}
.ansi-green-intense-bg {
  background-color: #007427;
}
.ansi-yellow-fg {
  color: #DDB62B;
}
.ansi-yellow-bg {
  background-color: #DDB62B;
}
.ansi-yellow-intense-fg {
  color: #B27D12;
}
.ansi-yellow-intense-bg {
  background-color: #B27D12;
}
.ansi-blue-fg {
  color: #208FFB;
}
.ansi-blue-bg {
  background-color: #208FFB;
}
.ansi-blue-intense-fg {
  color: #0065CA;
}
.ansi-blue-intense-bg {
  background-color: #0065CA;
}
.ansi-magenta-fg {
  color: #D160C4;
}
.ansi-magenta-bg {
  background-color: #D160C4;
}
.ansi-magenta-intense-fg {
  color: #A03196;
}
.ansi-magenta-intense-bg {
  background-color: #A03196;
}
.ansi-cyan-fg {
  color: #60C6C8;
}
.ansi-cyan-bg {
  background-color: #60C6C8;
}
.ansi-cyan-intense-fg {
  color: #258F8F;
}
.ansi-cyan-intense-bg {
  background-color: #258F8F;
}
.ansi-white-fg {
  color: #C5C1B4;
}
.ansi-white-bg {
  background-color: #C5C1B4;
}
.ansi-white-intense-fg {
  color: #A1A6B2;
}
.ansi-white-intense-bg {
  background-color: #A1A6B2;
}
.ansi-default-inverse-fg {
  color: #FFFFFF;
}
.ansi-default-inverse-bg {
  background-color: #000000;
}
.ansi-bold {
  font-weight: bold;
}
.ansi-underline {
  text-decoration: underline;
}
/* The following styles are deprecated an will be removed in a future version */
.ansibold {
  font-weight: bold;
}
.ansi-inverse {
  outline: 0.5px dotted;
}
/* use dark versions for foreground, to improve visibility */
.ansiblack {
  color: black;
}
.ansired {
  color: darkred;
}
.ansigreen {
  color: darkgreen;
}
.ansiyellow {
  color: #c4a000;
}
.ansiblue {
  color: darkblue;
}
.ansipurple {
  color: darkviolet;
}
.ansicyan {
  color: steelblue;
}
.ansigray {
  color: gray;
}
/* and light for background, for the same reason */
.ansibgblack {
  background-color: black;
}
.ansibgred {
  background-color: red;
}
.ansibggreen {
  background-color: green;
}
.ansibgyellow {
  background-color: yellow;
}
.ansibgblue {
  background-color: blue;
}
.ansibgpurple {
  background-color: magenta;
}
.ansibgcyan {
  background-color: cyan;
}
.ansibggray {
  background-color: gray;
}
div.cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  border-radius: 2px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  border-width: 1px;
  border-style: solid;
  border-color: transparent;
  width: 100%;
  padding: 5px;
  /* This acts as a spacer between cells, that is outside the border */
  margin: 0px;
  outline: none;
  position: relative;
  overflow: visible;
}
div.cell:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: transparent;
}
div.cell.jupyter-soft-selected {
  border-left-color: #E3F2FD;
  border-left-width: 1px;
  padding-left: 5px;
  border-right-color: #E3F2FD;
  border-right-width: 1px;
  background: #E3F2FD;
}
@media print {
  div.cell.jupyter-soft-selected {
    border-color: transparent;
  }
}
div.cell.selected,
div.cell.selected.jupyter-soft-selected {
  border-color: #ababab;
}
div.cell.selected:before,
div.cell.selected.jupyter-soft-selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #42A5F5;
}
@media print {
  div.cell.selected,
  div.cell.selected.jupyter-soft-selected {
    border-color: transparent;
  }
}
.edit_mode div.cell.selected {
  border-color: #66BB6A;
}
.edit_mode div.cell.selected:before {
  position: absolute;
  display: block;
  top: -1px;
  left: -1px;
  width: 5px;
  height: calc(100% +  2px);
  content: '';
  background: #66BB6A;
}
@media print {
  .edit_mode div.cell.selected {
    border-color: transparent;
  }
}
.prompt {
  /* This needs to be wide enough for 3 digit prompt numbers: In[100]: */
  min-width: 14ex;
  /* This padding is tuned to match the padding on the CodeMirror editor. */
  padding: 0.4em;
  margin: 0px;
  font-family: monospace;
  text-align: right;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
  /* Don't highlight prompt number selection */
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  /* Use default cursor */
  cursor: default;
}
@media (max-width: 540px) {
  .prompt {
    text-align: left;
  }
}
div.inner_cell {
  min-width: 0;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_area {
  border: 1px solid #cfcfcf;
  border-radius: 2px;
  background: #f7f7f7;
  line-height: 1.21429em;
}
/* This is needed so that empty prompt areas can collapse to zero height when there
   is no content in the output_subarea and the prompt. The main purpose of this is
   to make sure that empty JavaScript output_subareas have no height. */
div.prompt:empty {
  padding-top: 0;
  padding-bottom: 0;
}
div.unrecognized_cell {
  padding: 5px 5px 5px 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.unrecognized_cell .inner_cell {
  border-radius: 2px;
  padding: 5px;
  font-weight: bold;
  color: red;
  border: 1px solid #cfcfcf;
  background: #eaeaea;
}
div.unrecognized_cell .inner_cell a {
  color: inherit;
  text-decoration: none;
}
div.unrecognized_cell .inner_cell a:hover {
  color: inherit;
  text-decoration: none;
}
@media (max-width: 540px) {
  div.unrecognized_cell > div.prompt {
    display: none;
  }
}
div.code_cell {
  /* avoid page breaking on code cells when printing */
}
@media print {
  div.code_cell {
    page-break-inside: avoid;
  }
}
/* any special styling for code cells that are currently running goes here */
div.input {
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.input {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
/* input_area and input_prompt must match in top border and margin for alignment */
div.input_prompt {
  color: #303F9F;
  border-top: 1px solid transparent;
}
div.input_area > div.highlight {
  margin: 0.4em;
  border: none;
  padding: 0px;
  background-color: transparent;
}
div.input_area > div.highlight > pre {
  margin: 0px;
  border: none;
  padding: 0px;
  background-color: transparent;
}
/* The following gets added to the <head> if it is detected that the user has a
 * monospace font with inconsistent normal/bold/italic height.  See
 * notebookmain.js.  Such fonts will have keywords vertically offset with
 * respect to the rest of the text.  The user should select a better font.
 * See: https://github.com/ipython/ipython/issues/1503
 *
 * .CodeMirror span {
 *      vertical-align: bottom;
 * }
 */
.CodeMirror {
  line-height: 1.21429em;
  /* Changed from 1em to our global default */
  font-size: 14px;
  height: auto;
  /* Changed to auto to autogrow */
  background: none;
  /* Changed from white to allow our bg to show through */
}
.CodeMirror-scroll {
  /*  The CodeMirror docs are a bit fuzzy on if overflow-y should be hidden or visible.*/
  /*  We have found that if it is visible, vertical scrollbars appear with font size changes.*/
  overflow-y: hidden;
  overflow-x: auto;
}
.CodeMirror-lines {
  /* In CM2, this used to be 0.4em, but in CM3 it went to 4px. We need the em value because */
  /* we have set a different line-height and want this to scale with that. */
  /* Note that this should set vertical padding only, since CodeMirror assumes
       that horizontal padding will be set on CodeMirror pre */
  padding: 0.4em 0;
}
.CodeMirror-linenumber {
  padding: 0 8px 0 4px;
}
.CodeMirror-gutters {
  border-bottom-left-radius: 2px;
  border-top-left-radius: 2px;
}
.CodeMirror pre {
  /* In CM3 this went to 4px from 0 in CM2. This sets horizontal padding only,
    use .CodeMirror-lines for vertical */
  padding: 0 0.4em;
  border: 0;
  border-radius: 0;
}
.CodeMirror-cursor {
  border-left: 1.4px solid black;
}
@media screen and (min-width: 2138px) and (max-width: 4319px) {
  .CodeMirror-cursor {
    border-left: 2px solid black;
  }
}
@media screen and (min-width: 4320px) {
  .CodeMirror-cursor {
    border-left: 4px solid black;
  }
}
/*

Original style from softwaremaniacs.org (c) Ivan Sagalaev <Maniac@SoftwareManiacs.Org>
Adapted from GitHub theme

*/
.highlight-base {
  color: #000;
}
.highlight-variable {
  color: #000;
}
.highlight-variable-2 {
  color: #1a1a1a;
}
.highlight-variable-3 {
  color: #333333;
}
.highlight-string {
  color: #BA2121;
}
.highlight-comment {
  color: #408080;
  font-style: italic;
}
.highlight-number {
  color: #080;
}
.highlight-atom {
  color: #88F;
}
.highlight-keyword {
  color: #008000;
  font-weight: bold;
}
.highlight-builtin {
  color: #008000;
}
.highlight-error {
  color: #f00;
}
.highlight-operator {
  color: #AA22FF;
  font-weight: bold;
}
.highlight-meta {
  color: #AA22FF;
}
/* previously not defined, copying from default codemirror */
.highlight-def {
  color: #00f;
}
.highlight-string-2 {
  color: #f50;
}
.highlight-qualifier {
  color: #555;
}
.highlight-bracket {
  color: #997;
}
.highlight-tag {
  color: #170;
}
.highlight-attribute {
  color: #00c;
}
.highlight-header {
  color: blue;
}
.highlight-quote {
  color: #090;
}
.highlight-link {
  color: #00c;
}
/* apply the same style to codemirror */
.cm-s-ipython span.cm-keyword {
  color: #008000;
  font-weight: bold;
}
.cm-s-ipython span.cm-atom {
  color: #88F;
}
.cm-s-ipython span.cm-number {
  color: #080;
}
.cm-s-ipython span.cm-def {
  color: #00f;
}
.cm-s-ipython span.cm-variable {
  color: #000;
}
.cm-s-ipython span.cm-operator {
  color: #AA22FF;
  font-weight: bold;
}
.cm-s-ipython span.cm-variable-2 {
  color: #1a1a1a;
}
.cm-s-ipython span.cm-variable-3 {
  color: #333333;
}
.cm-s-ipython span.cm-comment {
  color: #408080;
  font-style: italic;
}
.cm-s-ipython span.cm-string {
  color: #BA2121;
}
.cm-s-ipython span.cm-string-2 {
  color: #f50;
}
.cm-s-ipython span.cm-meta {
  color: #AA22FF;
}
.cm-s-ipython span.cm-qualifier {
  color: #555;
}
.cm-s-ipython span.cm-builtin {
  color: #008000;
}
.cm-s-ipython span.cm-bracket {
  color: #997;
}
.cm-s-ipython span.cm-tag {
  color: #170;
}
.cm-s-ipython span.cm-attribute {
  color: #00c;
}
.cm-s-ipython span.cm-header {
  color: blue;
}
.cm-s-ipython span.cm-quote {
  color: #090;
}
.cm-s-ipython span.cm-link {
  color: #00c;
}
.cm-s-ipython span.cm-error {
  color: #f00;
}
.cm-s-ipython span.cm-tab {
  background: url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAMCAYAAAAkuj5RAAAAAXNSR0IArs4c6QAAAGFJREFUSMft1LsRQFAQheHPowAKoACx3IgEKtaEHujDjORSgWTH/ZOdnZOcM/sgk/kFFWY0qV8foQwS4MKBCS3qR6ixBJvElOobYAtivseIE120FaowJPN75GMu8j/LfMwNjh4HUpwg4LUAAAAASUVORK5CYII=);
  background-position: right;
  background-repeat: no-repeat;
}
div.output_wrapper {
  /* this position must be relative to enable descendents to be absolute within it */
  position: relative;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
  z-index: 1;
}
/* class for the output area when it should be height-limited */
div.output_scroll {
  /* ideally, this would be max-height, but FF barfs all over that */
  height: 24em;
  /* FF needs this *and the wrapper* to specify full width, or it will shrinkwrap */
  width: 100%;
  overflow: auto;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  box-shadow: inset 0 2px 8px rgba(0, 0, 0, 0.8);
  display: block;
}
/* output div while it is collapsed */
div.output_collapsed {
  margin: 0px;
  padding: 0px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
div.out_prompt_overlay {
  height: 100%;
  padding: 0px 0.4em;
  position: absolute;
  border-radius: 2px;
}
div.out_prompt_overlay:hover {
  /* use inner shadow to get border that is computed the same on WebKit/FF */
  -webkit-box-shadow: inset 0 0 1px #000;
  box-shadow: inset 0 0 1px #000;
  background: rgba(240, 240, 240, 0.5);
}
div.output_prompt {
  color: #D84315;
}
/* This class is the outer container of all output sections. */
div.output_area {
  padding: 0px;
  page-break-inside: avoid;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
div.output_area .MathJax_Display {
  text-align: left !important;
}
div.output_area .rendered_html table {
  margin-left: 0;
  margin-right: 0;
}
div.output_area .rendered_html img {
  margin-left: 0;
  margin-right: 0;
}
div.output_area img,
div.output_area svg {
  max-width: 100%;
  height: auto;
}
div.output_area img.unconfined,
div.output_area svg.unconfined {
  max-width: none;
}
div.output_area .mglyph > img {
  max-width: none;
}
/* This is needed to protect the pre formating from global settings such
   as that of bootstrap */
.output {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: vertical;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: vertical;
  -moz-box-align: stretch;
  display: box;
  box-orient: vertical;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: column;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.output_area {
    /* Old browsers */
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-box-align: stretch;
    display: -moz-box;
    -moz-box-orient: vertical;
    -moz-box-align: stretch;
    display: box;
    box-orient: vertical;
    box-align: stretch;
    /* Modern browsers */
    display: flex;
    flex-direction: column;
    align-items: stretch;
  }
}
div.output_area pre {
  margin: 0;
  padding: 1px 0 1px 0;
  border: 0;
  vertical-align: baseline;
  color: black;
  background-color: transparent;
  border-radius: 0;
}
/* This class is for the output subarea inside the output_area and after
   the prompt div. */
div.output_subarea {
  overflow-x: auto;
  padding: 0.4em;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
  max-width: calc(100% - 14ex);
}
div.output_scroll div.output_subarea {
  overflow-x: visible;
}
/* The rest of the output_* classes are for special styling of the different
   output types */
/* all text output has this class: */
div.output_text {
  text-align: left;
  color: #000;
  /* This has to match that of the the CodeMirror class line-height below */
  line-height: 1.21429em;
}
/* stdout/stderr are 'text' as well as 'stream', but execute_result/error are *not* streams */
div.output_stderr {
  background: #fdd;
  /* very light red background for stderr */
}
div.output_latex {
  text-align: left;
}
/* Empty output_javascript divs should have no height */
div.output_javascript:empty {
  padding: 0;
}
.js-error {
  color: darkred;
}
/* raw_input styles */
div.raw_input_container {
  line-height: 1.21429em;
  padding-top: 5px;
}
pre.raw_input_prompt {
  /* nothing needed here. */
}
input.raw_input {
  font-family: monospace;
  font-size: inherit;
  color: inherit;
  width: auto;
  /* make sure input baseline aligns with prompt */
  vertical-align: baseline;
  /* padding + margin = 0.5em between prompt and cursor */
  padding: 0em 0.25em;
  margin: 0em 0.25em;
}
input.raw_input:focus {
  box-shadow: none;
}
p.p-space {
  margin-bottom: 10px;
}
div.output_unrecognized {
  padding: 5px;
  font-weight: bold;
  color: red;
}
div.output_unrecognized a {
  color: inherit;
  text-decoration: none;
}
div.output_unrecognized a:hover {
  color: inherit;
  text-decoration: none;
}
.rendered_html {
  color: #000;
  /* any extras will just be numbers: */
}
.rendered_html em {
  font-style: italic;
}
.rendered_html strong {
  font-weight: bold;
}
.rendered_html u {
  text-decoration: underline;
}
.rendered_html :link {
  text-decoration: underline;
}
.rendered_html :visited {
  text-decoration: underline;
}
.rendered_html h1 {
  font-size: 185.7%;
  margin: 1.08em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h2 {
  font-size: 157.1%;
  margin: 1.27em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h3 {
  font-size: 128.6%;
  margin: 1.55em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h4 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
}
.rendered_html h5 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h6 {
  font-size: 100%;
  margin: 2em 0 0 0;
  font-weight: bold;
  line-height: 1.0;
  font-style: italic;
}
.rendered_html h1:first-child {
  margin-top: 0.538em;
}
.rendered_html h2:first-child {
  margin-top: 0.636em;
}
.rendered_html h3:first-child {
  margin-top: 0.777em;
}
.rendered_html h4:first-child {
  margin-top: 1em;
}
.rendered_html h5:first-child {
  margin-top: 1em;
}
.rendered_html h6:first-child {
  margin-top: 1em;
}
.rendered_html ul:not(.list-inline),
.rendered_html ol:not(.list-inline) {
  padding-left: 2em;
}
.rendered_html ul {
  list-style: disc;
}
.rendered_html ul ul {
  list-style: square;
  margin-top: 0;
}
.rendered_html ul ul ul {
  list-style: circle;
}
.rendered_html ol {
  list-style: decimal;
}
.rendered_html ol ol {
  list-style: upper-alpha;
  margin-top: 0;
}
.rendered_html ol ol ol {
  list-style: lower-alpha;
}
.rendered_html ol ol ol ol {
  list-style: lower-roman;
}
.rendered_html ol ol ol ol ol {
  list-style: decimal;
}
.rendered_html * + ul {
  margin-top: 1em;
}
.rendered_html * + ol {
  margin-top: 1em;
}
.rendered_html hr {
  color: black;
  background-color: black;
}
.rendered_html pre {
  margin: 1em 2em;
  padding: 0px;
  background-color: #fff;
}
.rendered_html code {
  background-color: #eff0f1;
}
.rendered_html p code {
  padding: 1px 5px;
}
.rendered_html pre code {
  background-color: #fff;
}
.rendered_html pre,
.rendered_html code {
  border: 0;
  color: #000;
  font-size: 100%;
}
.rendered_html blockquote {
  margin: 1em 2em;
}
.rendered_html table {
  margin-left: auto;
  margin-right: auto;
  border: none;
  border-collapse: collapse;
  border-spacing: 0;
  color: black;
  font-size: 12px;
  table-layout: fixed;
}
.rendered_html thead {
  border-bottom: 1px solid black;
  vertical-align: bottom;
}
.rendered_html tr,
.rendered_html th,
.rendered_html td {
  text-align: right;
  vertical-align: middle;
  padding: 0.5em 0.5em;
  line-height: normal;
  white-space: normal;
  max-width: none;
  border: none;
}
.rendered_html th {
  font-weight: bold;
}
.rendered_html tbody tr:nth-child(odd) {
  background: #f5f5f5;
}
.rendered_html tbody tr:hover {
  background: rgba(66, 165, 245, 0.2);
}
.rendered_html * + table {
  margin-top: 1em;
}
.rendered_html p {
  text-align: left;
}
.rendered_html * + p {
  margin-top: 1em;
}
.rendered_html img {
  display: block;
  margin-left: auto;
  margin-right: auto;
}
.rendered_html * + img {
  margin-top: 1em;
}
.rendered_html img,
.rendered_html svg {
  max-width: 100%;
  height: auto;
}
.rendered_html img.unconfined,
.rendered_html svg.unconfined {
  max-width: none;
}
.rendered_html .alert {
  margin-bottom: initial;
}
.rendered_html * + .alert {
  margin-top: 1em;
}
[dir="rtl"] .rendered_html p {
  text-align: right;
}
div.text_cell {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
}
@media (max-width: 540px) {
  div.text_cell > div.prompt {
    display: none;
  }
}
div.text_cell_render {
  /*font-family: "Helvetica Neue", Arial, Helvetica, Geneva, sans-serif;*/
  outline: none;
  resize: none;
  width: inherit;
  border-style: none;
  padding: 0.5em 0.5em 0.5em 0.4em;
  color: #000;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
a.anchor-link:link {
  text-decoration: none;
  padding: 0px 20px;
  visibility: hidden;
}
h1:hover .anchor-link,
h2:hover .anchor-link,
h3:hover .anchor-link,
h4:hover .anchor-link,
h5:hover .anchor-link,
h6:hover .anchor-link {
  visibility: visible;
}
.text_cell.rendered .input_area {
  display: none;
}
.text_cell.rendered .rendered_html {
  overflow-x: auto;
  overflow-y: hidden;
}
.text_cell.rendered .rendered_html tr,
.text_cell.rendered .rendered_html th,
.text_cell.rendered .rendered_html td {
  max-width: none;
}
.text_cell.unrendered .text_cell_render {
  display: none;
}
.text_cell .dropzone .input_area {
  border: 2px dashed #bababa;
  margin: -1px;
}
.cm-header-1,
.cm-header-2,
.cm-header-3,
.cm-header-4,
.cm-header-5,
.cm-header-6 {
  font-weight: bold;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
.cm-header-1 {
  font-size: 185.7%;
}
.cm-header-2 {
  font-size: 157.1%;
}
.cm-header-3 {
  font-size: 128.6%;
}
.cm-header-4 {
  font-size: 110%;
}
.cm-header-5 {
  font-size: 100%;
  font-style: italic;
}
.cm-header-6 {
  font-size: 100%;
  font-style: italic;
}
/*!
*
* IPython notebook webapp
*
*/
@media (max-width: 767px) {
  .notebook_app {
    padding-left: 0px;
    padding-right: 0px;
  }
}
#ipython-main-app {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook_panel {
  margin: 0px;
  padding: 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  height: 100%;
}
div#notebook {
  font-size: 14px;
  line-height: 20px;
  overflow-y: hidden;
  overflow-x: auto;
  width: 100%;
  /* This spaces the page away from the edge of the notebook area */
  padding-top: 20px;
  margin: 0px;
  outline: none;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  min-height: 100%;
}
@media not print {
  #notebook-container {
    padding: 15px;
    background-color: #fff;
    min-height: 0;
    -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
    box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  }
}
@media print {
  #notebook-container {
    width: 100%;
  }
}
div.ui-widget-content {
  border: 1px solid #ababab;
  outline: none;
}
pre.dialog {
  background-color: #f7f7f7;
  border: 1px solid #ddd;
  border-radius: 2px;
  padding: 0.4em;
  padding-left: 2em;
}
p.dialog {
  padding: 0.2em;
}
/* Word-wrap output correctly.  This is the CSS3 spelling, though Firefox seems
   to not honor it correctly.  Webkit browsers (Chrome, rekonq, Safari) do.
 */
pre,
code,
kbd,
samp {
  white-space: pre-wrap;
}
#fonttest {
  font-family: monospace;
}
p {
  margin-bottom: 0;
}
.end_space {
  min-height: 100px;
  transition: height .2s ease;
}
.notebook_app > #header {
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
@media not print {
  .notebook_app {
    background-color: #EEE;
  }
}
kbd {
  border-style: solid;
  border-width: 1px;
  box-shadow: none;
  margin: 2px;
  padding-left: 2px;
  padding-right: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
.jupyter-keybindings {
  padding: 1px;
  line-height: 24px;
  border-bottom: 1px solid gray;
}
.jupyter-keybindings input {
  margin: 0;
  padding: 0;
  border: none;
}
.jupyter-keybindings i {
  padding: 6px;
}
.well code {
  background-color: #ffffff;
  border-color: #ababab;
  border-width: 1px;
  border-style: solid;
  padding: 2px;
  padding-top: 1px;
  padding-bottom: 1px;
}
/* CSS for the cell toolbar */
.celltoolbar {
  border: thin solid #CFCFCF;
  border-bottom: none;
  background: #EEE;
  border-radius: 2px 2px 0px 0px;
  width: 100%;
  height: 29px;
  padding-right: 4px;
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  /* Old browsers */
  -webkit-box-pack: end;
  -moz-box-pack: end;
  box-pack: end;
  /* Modern browsers */
  justify-content: flex-end;
  display: -webkit-flex;
}
@media print {
  .celltoolbar {
    display: none;
  }
}
.ctb_hideshow {
  display: none;
  vertical-align: bottom;
}
/* ctb_show is added to the ctb_hideshow div to show the cell toolbar.
   Cell toolbars are only shown when the ctb_global_show class is also set.
*/
.ctb_global_show .ctb_show.ctb_hideshow {
  display: block;
}
.ctb_global_show .ctb_show + .input_area,
.ctb_global_show .ctb_show + div.text_cell_input,
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border-top-right-radius: 0px;
  border-top-left-radius: 0px;
}
.ctb_global_show .ctb_show ~ div.text_cell_render {
  border: 1px solid #cfcfcf;
}
.celltoolbar {
  font-size: 87%;
  padding-top: 3px;
}
.celltoolbar select {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  width: inherit;
  font-size: inherit;
  height: 22px;
  padding: 0px;
  display: inline-block;
}
.celltoolbar select:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.celltoolbar select::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.celltoolbar select:-ms-input-placeholder {
  color: #999;
}
.celltoolbar select::-webkit-input-placeholder {
  color: #999;
}
.celltoolbar select::-ms-expand {
  border: 0;
  background-color: transparent;
}
.celltoolbar select[disabled],
.celltoolbar select[readonly],
fieldset[disabled] .celltoolbar select {
  background-color: #eeeeee;
  opacity: 1;
}
.celltoolbar select[disabled],
fieldset[disabled] .celltoolbar select {
  cursor: not-allowed;
}
textarea.celltoolbar select {
  height: auto;
}
select.celltoolbar select {
  height: 30px;
  line-height: 30px;
}
textarea.celltoolbar select,
select[multiple].celltoolbar select {
  height: auto;
}
.celltoolbar label {
  margin-left: 5px;
  margin-right: 5px;
}
.tags_button_container {
  width: 100%;
  display: flex;
}
.tag-container {
  display: flex;
  flex-direction: row;
  flex-grow: 1;
  overflow: hidden;
  position: relative;
}
.tag-container > * {
  margin: 0 4px;
}
.remove-tag-btn {
  margin-left: 4px;
}
.tags-input {
  display: flex;
}
.cell-tag:last-child:after {
  content: "";
  position: absolute;
  right: 0;
  width: 40px;
  height: 100%;
  /* Fade to background color of cell toolbar */
  background: linear-gradient(to right, rgba(0, 0, 0, 0), #EEE);
}
.tags-input > * {
  margin-left: 4px;
}
.cell-tag,
.tags-input input,
.tags-input button {
  display: block;
  width: 100%;
  height: 32px;
  padding: 6px 12px;
  font-size: 13px;
  line-height: 1.42857143;
  color: #555555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 2px;
  -webkit-box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  box-shadow: inset 0 1px 1px rgba(0, 0, 0, 0.075);
  -webkit-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  -o-transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  transition: border-color ease-in-out .15s, box-shadow ease-in-out .15s;
  height: 30px;
  padding: 5px 10px;
  font-size: 12px;
  line-height: 1.5;
  border-radius: 1px;
  box-shadow: none;
  width: inherit;
  font-size: inherit;
  height: 22px;
  line-height: 22px;
  padding: 0px 4px;
  display: inline-block;
}
.cell-tag:focus,
.tags-input input:focus,
.tags-input button:focus {
  border-color: #66afe9;
  outline: 0;
  -webkit-box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
  box-shadow: inset 0 1px 1px rgba(0,0,0,.075), 0 0 8px rgba(102, 175, 233, 0.6);
}
.cell-tag::-moz-placeholder,
.tags-input input::-moz-placeholder,
.tags-input button::-moz-placeholder {
  color: #999;
  opacity: 1;
}
.cell-tag:-ms-input-placeholder,
.tags-input input:-ms-input-placeholder,
.tags-input button:-ms-input-placeholder {
  color: #999;
}
.cell-tag::-webkit-input-placeholder,
.tags-input input::-webkit-input-placeholder,
.tags-input button::-webkit-input-placeholder {
  color: #999;
}
.cell-tag::-ms-expand,
.tags-input input::-ms-expand,
.tags-input button::-ms-expand {
  border: 0;
  background-color: transparent;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
.cell-tag[readonly],
.tags-input input[readonly],
.tags-input button[readonly],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  background-color: #eeeeee;
  opacity: 1;
}
.cell-tag[disabled],
.tags-input input[disabled],
.tags-input button[disabled],
fieldset[disabled] .cell-tag,
fieldset[disabled] .tags-input input,
fieldset[disabled] .tags-input button {
  cursor: not-allowed;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button {
  height: auto;
}
select.cell-tag,
select.tags-input input,
select.tags-input button {
  height: 30px;
  line-height: 30px;
}
textarea.cell-tag,
textarea.tags-input input,
textarea.tags-input button,
select[multiple].cell-tag,
select[multiple].tags-input input,
select[multiple].tags-input button {
  height: auto;
}
.cell-tag,
.tags-input button {
  padding: 0px 4px;
}
.cell-tag {
  background-color: #fff;
  white-space: nowrap;
}
.tags-input input[type=text]:focus {
  outline: none;
  box-shadow: none;
  border-color: #ccc;
}
.completions {
  position: absolute;
  z-index: 110;
  overflow: hidden;
  border: 1px solid #ababab;
  border-radius: 2px;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  line-height: 1;
}
.completions select {
  background: white;
  outline: none;
  border: none;
  padding: 0px;
  margin: 0px;
  overflow: auto;
  font-family: monospace;
  font-size: 110%;
  color: #000;
  width: auto;
}
.completions select option.context {
  color: #286090;
}
#kernel_logo_widget .current_kernel_logo {
  display: none;
  margin-top: -1px;
  margin-bottom: -1px;
  width: 32px;
  height: 32px;
}
[dir="rtl"] #kernel_logo_widget {
  float: left !important;
  float: left;
}
.modal .modal-body .move-path {
  display: flex;
  flex-direction: row;
  justify-content: space;
  align-items: center;
}
.modal .modal-body .move-path .server-root {
  padding-right: 20px;
}
.modal .modal-body .move-path .path-input {
  flex: 1;
}
#menubar {
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
  margin-top: 1px;
}
#menubar .navbar {
  border-top: 1px;
  border-radius: 0px 0px 2px 2px;
  margin-bottom: 0px;
}
#menubar .navbar-toggle {
  float: left;
  padding-top: 7px;
  padding-bottom: 7px;
  border: none;
}
#menubar .navbar-collapse {
  clear: left;
}
[dir="rtl"] #menubar .navbar-toggle {
  float: right;
}
[dir="rtl"] #menubar .navbar-collapse {
  clear: right;
}
[dir="rtl"] #menubar .navbar-nav {
  float: right;
}
[dir="rtl"] #menubar .nav {
  padding-right: 0px;
}
[dir="rtl"] #menubar .navbar-nav > li {
  float: right;
}
[dir="rtl"] #menubar .navbar-right {
  float: left !important;
}
[dir="rtl"] ul.dropdown-menu {
  text-align: right;
  left: auto;
}
[dir="rtl"] ul#new-menu.dropdown-menu {
  right: auto;
  left: 0;
}
.nav-wrapper {
  border-bottom: 1px solid #e7e7e7;
}
i.menu-icon {
  padding-top: 4px;
}
[dir="rtl"] i.menu-icon.pull-right {
  float: left !important;
  float: left;
}
ul#help_menu li a {
  overflow: hidden;
  padding-right: 2.2em;
}
ul#help_menu li a i {
  margin-right: -1.2em;
}
[dir="rtl"] ul#help_menu li a {
  padding-left: 2.2em;
}
[dir="rtl"] ul#help_menu li a i {
  margin-right: 0;
  margin-left: -1.2em;
}
[dir="rtl"] ul#help_menu li a i.pull-right {
  float: left !important;
  float: left;
}
.dropdown-submenu {
  position: relative;
}
.dropdown-submenu > .dropdown-menu {
  top: 0;
  left: 100%;
  margin-top: -6px;
  margin-left: -1px;
}
[dir="rtl"] .dropdown-submenu > .dropdown-menu {
  right: 100%;
  margin-right: -1px;
}
.dropdown-submenu:hover > .dropdown-menu {
  display: block;
}
.dropdown-submenu > a:after {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: block;
  content: "\f0da";
  float: right;
  color: #333333;
  margin-top: 2px;
  margin-right: -10px;
}
.dropdown-submenu > a:after.fa-pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.fa-pull-right {
  margin-left: .3em;
}
.dropdown-submenu > a:after.pull-left {
  margin-right: .3em;
}
.dropdown-submenu > a:after.pull-right {
  margin-left: .3em;
}
[dir="rtl"] .dropdown-submenu > a:after {
  float: left;
  content: "\f0d9";
  margin-right: 0;
  margin-left: -10px;
}
.dropdown-submenu:hover > a:after {
  color: #262626;
}
.dropdown-submenu.pull-left {
  float: none;
}
.dropdown-submenu.pull-left > .dropdown-menu {
  left: -100%;
  margin-left: 10px;
}
#notification_area {
  float: right !important;
  float: right;
  z-index: 10;
}
[dir="rtl"] #notification_area {
  float: left !important;
  float: left;
}
.indicator_area {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] .indicator_area {
  float: left !important;
  float: left;
}
#kernel_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  border-left: 1px solid;
}
#kernel_indicator .kernel_indicator_name {
  padding-left: 5px;
  padding-right: 5px;
}
[dir="rtl"] #kernel_indicator {
  float: left !important;
  float: left;
  border-left: 0;
  border-right: 1px solid;
}
#modal_indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
}
[dir="rtl"] #modal_indicator {
  float: left !important;
  float: left;
}
#readonly-indicator {
  float: right !important;
  float: right;
  color: #777;
  margin-left: 5px;
  margin-right: 5px;
  width: 11px;
  z-index: 10;
  text-align: center;
  width: auto;
  margin-top: 2px;
  margin-bottom: 0px;
  margin-left: 0px;
  margin-right: 0px;
  display: none;
}
.modal_indicator:before {
  width: 1.28571429em;
  text-align: center;
}
.edit_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f040";
}
.edit_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.edit_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.edit_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: ' ';
}
.command_mode .modal_indicator:before.fa-pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.fa-pull-right {
  margin-left: .3em;
}
.command_mode .modal_indicator:before.pull-left {
  margin-right: .3em;
}
.command_mode .modal_indicator:before.pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f10c";
}
.kernel_idle_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_idle_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_idle_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f111";
}
.kernel_busy_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_busy_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_busy_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f1e2";
}
.kernel_dead_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_dead_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_dead_icon:before.pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before {
  display: inline-block;
  font: normal normal normal 14px/1 FontAwesome;
  font-size: inherit;
  text-rendering: auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  content: "\f127";
}
.kernel_disconnected_icon:before.fa-pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.fa-pull-right {
  margin-left: .3em;
}
.kernel_disconnected_icon:before.pull-left {
  margin-right: .3em;
}
.kernel_disconnected_icon:before.pull-right {
  margin-left: .3em;
}
.notification_widget {
  color: #777;
  z-index: 10;
  background: rgba(240, 240, 240, 0.5);
  margin-right: 4px;
  color: #333;
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget:focus,
.notification_widget.focus {
  color: #333;
  background-color: #e6e6e6;
  border-color: #8c8c8c;
}
.notification_widget:hover {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  color: #333;
  background-color: #e6e6e6;
  border-color: #adadad;
}
.notification_widget:active:hover,
.notification_widget.active:hover,
.open > .dropdown-toggle.notification_widget:hover,
.notification_widget:active:focus,
.notification_widget.active:focus,
.open > .dropdown-toggle.notification_widget:focus,
.notification_widget:active.focus,
.notification_widget.active.focus,
.open > .dropdown-toggle.notification_widget.focus {
  color: #333;
  background-color: #d4d4d4;
  border-color: #8c8c8c;
}
.notification_widget:active,
.notification_widget.active,
.open > .dropdown-toggle.notification_widget {
  background-image: none;
}
.notification_widget.disabled:hover,
.notification_widget[disabled]:hover,
fieldset[disabled] .notification_widget:hover,
.notification_widget.disabled:focus,
.notification_widget[disabled]:focus,
fieldset[disabled] .notification_widget:focus,
.notification_widget.disabled.focus,
.notification_widget[disabled].focus,
fieldset[disabled] .notification_widget.focus {
  background-color: #fff;
  border-color: #ccc;
}
.notification_widget .badge {
  color: #fff;
  background-color: #333;
}
.notification_widget.warning {
  color: #fff;
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning:focus,
.notification_widget.warning.focus {
  color: #fff;
  background-color: #ec971f;
  border-color: #985f0d;
}
.notification_widget.warning:hover {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  color: #fff;
  background-color: #ec971f;
  border-color: #d58512;
}
.notification_widget.warning:active:hover,
.notification_widget.warning.active:hover,
.open > .dropdown-toggle.notification_widget.warning:hover,
.notification_widget.warning:active:focus,
.notification_widget.warning.active:focus,
.open > .dropdown-toggle.notification_widget.warning:focus,
.notification_widget.warning:active.focus,
.notification_widget.warning.active.focus,
.open > .dropdown-toggle.notification_widget.warning.focus {
  color: #fff;
  background-color: #d58512;
  border-color: #985f0d;
}
.notification_widget.warning:active,
.notification_widget.warning.active,
.open > .dropdown-toggle.notification_widget.warning {
  background-image: none;
}
.notification_widget.warning.disabled:hover,
.notification_widget.warning[disabled]:hover,
fieldset[disabled] .notification_widget.warning:hover,
.notification_widget.warning.disabled:focus,
.notification_widget.warning[disabled]:focus,
fieldset[disabled] .notification_widget.warning:focus,
.notification_widget.warning.disabled.focus,
.notification_widget.warning[disabled].focus,
fieldset[disabled] .notification_widget.warning.focus {
  background-color: #f0ad4e;
  border-color: #eea236;
}
.notification_widget.warning .badge {
  color: #f0ad4e;
  background-color: #fff;
}
.notification_widget.success {
  color: #fff;
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success:focus,
.notification_widget.success.focus {
  color: #fff;
  background-color: #449d44;
  border-color: #255625;
}
.notification_widget.success:hover {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  color: #fff;
  background-color: #449d44;
  border-color: #398439;
}
.notification_widget.success:active:hover,
.notification_widget.success.active:hover,
.open > .dropdown-toggle.notification_widget.success:hover,
.notification_widget.success:active:focus,
.notification_widget.success.active:focus,
.open > .dropdown-toggle.notification_widget.success:focus,
.notification_widget.success:active.focus,
.notification_widget.success.active.focus,
.open > .dropdown-toggle.notification_widget.success.focus {
  color: #fff;
  background-color: #398439;
  border-color: #255625;
}
.notification_widget.success:active,
.notification_widget.success.active,
.open > .dropdown-toggle.notification_widget.success {
  background-image: none;
}
.notification_widget.success.disabled:hover,
.notification_widget.success[disabled]:hover,
fieldset[disabled] .notification_widget.success:hover,
.notification_widget.success.disabled:focus,
.notification_widget.success[disabled]:focus,
fieldset[disabled] .notification_widget.success:focus,
.notification_widget.success.disabled.focus,
.notification_widget.success[disabled].focus,
fieldset[disabled] .notification_widget.success.focus {
  background-color: #5cb85c;
  border-color: #4cae4c;
}
.notification_widget.success .badge {
  color: #5cb85c;
  background-color: #fff;
}
.notification_widget.info {
  color: #fff;
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info:focus,
.notification_widget.info.focus {
  color: #fff;
  background-color: #31b0d5;
  border-color: #1b6d85;
}
.notification_widget.info:hover {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  color: #fff;
  background-color: #31b0d5;
  border-color: #269abc;
}
.notification_widget.info:active:hover,
.notification_widget.info.active:hover,
.open > .dropdown-toggle.notification_widget.info:hover,
.notification_widget.info:active:focus,
.notification_widget.info.active:focus,
.open > .dropdown-toggle.notification_widget.info:focus,
.notification_widget.info:active.focus,
.notification_widget.info.active.focus,
.open > .dropdown-toggle.notification_widget.info.focus {
  color: #fff;
  background-color: #269abc;
  border-color: #1b6d85;
}
.notification_widget.info:active,
.notification_widget.info.active,
.open > .dropdown-toggle.notification_widget.info {
  background-image: none;
}
.notification_widget.info.disabled:hover,
.notification_widget.info[disabled]:hover,
fieldset[disabled] .notification_widget.info:hover,
.notification_widget.info.disabled:focus,
.notification_widget.info[disabled]:focus,
fieldset[disabled] .notification_widget.info:focus,
.notification_widget.info.disabled.focus,
.notification_widget.info[disabled].focus,
fieldset[disabled] .notification_widget.info.focus {
  background-color: #5bc0de;
  border-color: #46b8da;
}
.notification_widget.info .badge {
  color: #5bc0de;
  background-color: #fff;
}
.notification_widget.danger {
  color: #fff;
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger:focus,
.notification_widget.danger.focus {
  color: #fff;
  background-color: #c9302c;
  border-color: #761c19;
}
.notification_widget.danger:hover {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  color: #fff;
  background-color: #c9302c;
  border-color: #ac2925;
}
.notification_widget.danger:active:hover,
.notification_widget.danger.active:hover,
.open > .dropdown-toggle.notification_widget.danger:hover,
.notification_widget.danger:active:focus,
.notification_widget.danger.active:focus,
.open > .dropdown-toggle.notification_widget.danger:focus,
.notification_widget.danger:active.focus,
.notification_widget.danger.active.focus,
.open > .dropdown-toggle.notification_widget.danger.focus {
  color: #fff;
  background-color: #ac2925;
  border-color: #761c19;
}
.notification_widget.danger:active,
.notification_widget.danger.active,
.open > .dropdown-toggle.notification_widget.danger {
  background-image: none;
}
.notification_widget.danger.disabled:hover,
.notification_widget.danger[disabled]:hover,
fieldset[disabled] .notification_widget.danger:hover,
.notification_widget.danger.disabled:focus,
.notification_widget.danger[disabled]:focus,
fieldset[disabled] .notification_widget.danger:focus,
.notification_widget.danger.disabled.focus,
.notification_widget.danger[disabled].focus,
fieldset[disabled] .notification_widget.danger.focus {
  background-color: #d9534f;
  border-color: #d43f3a;
}
.notification_widget.danger .badge {
  color: #d9534f;
  background-color: #fff;
}
div#pager {
  background-color: #fff;
  font-size: 14px;
  line-height: 20px;
  overflow: hidden;
  display: none;
  position: fixed;
  bottom: 0px;
  width: 100%;
  max-height: 50%;
  padding-top: 8px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  /* Display over codemirror */
  z-index: 100;
  /* Hack which prevents jquery ui resizable from changing top. */
  top: auto !important;
}
div#pager pre {
  line-height: 1.21429em;
  color: #000;
  background-color: #f7f7f7;
  padding: 0.4em;
}
div#pager #pager-button-area {
  position: absolute;
  top: 8px;
  right: 20px;
}
div#pager #pager-contents {
  position: relative;
  overflow: auto;
  width: 100%;
  height: 100%;
}
div#pager #pager-contents #pager-container {
  position: relative;
  padding: 15px 0px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
div#pager .ui-resizable-handle {
  top: 0px;
  height: 8px;
  background: #f7f7f7;
  border-top: 1px solid #cfcfcf;
  border-bottom: 1px solid #cfcfcf;
  /* This injects handle bars (a short, wide = symbol) for 
        the resize handle. */
}
div#pager .ui-resizable-handle::after {
  content: '';
  top: 2px;
  left: 50%;
  height: 3px;
  width: 30px;
  margin-left: -15px;
  position: absolute;
  border-top: 1px solid #cfcfcf;
}
.quickhelp {
  /* Old browsers */
  display: -webkit-box;
  -webkit-box-orient: horizontal;
  -webkit-box-align: stretch;
  display: -moz-box;
  -moz-box-orient: horizontal;
  -moz-box-align: stretch;
  display: box;
  box-orient: horizontal;
  box-align: stretch;
  /* Modern browsers */
  display: flex;
  flex-direction: row;
  align-items: stretch;
  line-height: 1.8em;
}
.shortcut_key {
  display: inline-block;
  width: 21ex;
  text-align: right;
  font-family: monospace;
}
.shortcut_descr {
  display: inline-block;
  /* Old browsers */
  -webkit-box-flex: 1;
  -moz-box-flex: 1;
  box-flex: 1;
  /* Modern browsers */
  flex: 1;
}
span.save_widget {
  height: 30px;
  margin-top: 4px;
  display: flex;
  justify-content: flex-start;
  align-items: baseline;
  width: 50%;
  flex: 1;
}
span.save_widget span.filename {
  height: 100%;
  line-height: 1em;
  margin-left: 16px;
  border: none;
  font-size: 146.5%;
  text-overflow: ellipsis;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 2px;
}
span.save_widget span.filename:hover {
  background-color: #e6e6e6;
}
[dir="rtl"] span.save_widget.pull-left {
  float: right !important;
  float: right;
}
[dir="rtl"] span.save_widget span.filename {
  margin-left: 0;
  margin-right: 16px;
}
span.checkpoint_status,
span.autosave_status {
  font-size: small;
  white-space: nowrap;
  padding: 0 5px;
}
@media (max-width: 767px) {
  span.save_widget {
    font-size: small;
    padding: 0 0 0 5px;
  }
  span.checkpoint_status,
  span.autosave_status {
    display: none;
  }
}
@media (min-width: 768px) and (max-width: 991px) {
  span.checkpoint_status {
    display: none;
  }
  span.autosave_status {
    font-size: x-small;
  }
}
.toolbar {
  padding: 0px;
  margin-left: -5px;
  margin-top: 2px;
  margin-bottom: 5px;
  box-sizing: border-box;
  -moz-box-sizing: border-box;
  -webkit-box-sizing: border-box;
}
.toolbar select,
.toolbar label {
  width: auto;
  vertical-align: middle;
  margin-right: 2px;
  margin-bottom: 0px;
  display: inline;
  font-size: 92%;
  margin-left: 0.3em;
  margin-right: 0.3em;
  padding: 0px;
  padding-top: 3px;
}
.toolbar .btn {
  padding: 2px 8px;
}
.toolbar .btn-group {
  margin-top: 0px;
  margin-left: 5px;
}
.toolbar-btn-label {
  margin-left: 6px;
}
#maintoolbar {
  margin-bottom: -3px;
  margin-top: -8px;
  border: 0px;
  min-height: 27px;
  margin-left: 0px;
  padding-top: 11px;
  padding-bottom: 3px;
}
#maintoolbar .navbar-text {
  float: none;
  vertical-align: middle;
  text-align: right;
  margin-left: 5px;
  margin-right: 0px;
  margin-top: 0px;
}
.select-xs {
  height: 24px;
}
[dir="rtl"] .btn-group > .btn,
.btn-group-vertical > .btn {
  float: right;
}
.pulse,
.dropdown-menu > li > a.pulse,
li.pulse > a.dropdown-toggle,
li.pulse.open > a.dropdown-toggle {
  background-color: #F37626;
  color: white;
}
/**
 * Primary styles
 *
 * Author: Jupyter Development Team
 */
/** WARNING IF YOU ARE EDITTING THIS FILE, if this is a .css file, It has a lot
 * of chance of beeing generated from the ../less/[samename].less file, you can
 * try to get back the less file by reverting somme commit in history
 **/
/*
 * We'll try to get something pretty, so we
 * have some strange css to have the scroll bar on
 * the left with fix button on the top right of the tooltip
 */
@-moz-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-webkit-keyframes fadeOut {
  from {
    opacity: 1;
  }
  to {
    opacity: 0;
  }
}
@-moz-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
@-webkit-keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}
/*properties of tooltip after "expand"*/
.bigtooltip {
  overflow: auto;
  height: 200px;
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
}
/*properties of tooltip before "expand"*/
.smalltooltip {
  -webkit-transition-property: height;
  -webkit-transition-duration: 500ms;
  -moz-transition-property: height;
  -moz-transition-duration: 500ms;
  transition-property: height;
  transition-duration: 500ms;
  text-overflow: ellipsis;
  overflow: hidden;
  height: 80px;
}
.tooltipbuttons {
  position: absolute;
  padding-right: 15px;
  top: 0px;
  right: 0px;
}
.tooltiptext {
  /*avoid the button to overlap on some docstring*/
  padding-right: 30px;
}
.ipython_tooltip {
  max-width: 700px;
  /*fade-in animation when inserted*/
  -webkit-animation: fadeOut 400ms;
  -moz-animation: fadeOut 400ms;
  animation: fadeOut 400ms;
  -webkit-animation: fadeIn 400ms;
  -moz-animation: fadeIn 400ms;
  animation: fadeIn 400ms;
  vertical-align: middle;
  background-color: #f7f7f7;
  overflow: visible;
  border: #ababab 1px solid;
  outline: none;
  padding: 3px;
  margin: 0px;
  padding-left: 7px;
  font-family: monospace;
  min-height: 50px;
  -moz-box-shadow: 0px 6px 10px -1px #adadad;
  -webkit-box-shadow: 0px 6px 10px -1px #adadad;
  box-shadow: 0px 6px 10px -1px #adadad;
  border-radius: 2px;
  position: absolute;
  z-index: 1000;
}
.ipython_tooltip a {
  float: right;
}
.ipython_tooltip .tooltiptext pre {
  border: 0;
  border-radius: 0;
  font-size: 100%;
  background-color: #f7f7f7;
}
.pretooltiparrow {
  left: 0px;
  margin: 0px;
  top: -16px;
  width: 40px;
  height: 16px;
  overflow: hidden;
  position: absolute;
}
.pretooltiparrow:before {
  background-color: #f7f7f7;
  border: 1px #ababab solid;
  z-index: 11;
  content: "";
  position: absolute;
  left: 15px;
  top: 10px;
  width: 25px;
  height: 25px;
  -webkit-transform: rotate(45deg);
  -moz-transform: rotate(45deg);
  -ms-transform: rotate(45deg);
  -o-transform: rotate(45deg);
}
ul.typeahead-list i {
  margin-left: -10px;
  width: 18px;
}
[dir="rtl"] ul.typeahead-list i {
  margin-left: 0;
  margin-right: -10px;
}
ul.typeahead-list {
  max-height: 80vh;
  overflow: auto;
}
ul.typeahead-list > li > a {
  /** Firefox bug **/
  /* see https://github.com/jupyter/notebook/issues/559 */
  white-space: normal;
}
ul.typeahead-list  > li > a.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .typeahead-list {
  text-align: right;
}
.cmd-palette .modal-body {
  padding: 7px;
}
.cmd-palette form {
  background: white;
}
.cmd-palette input {
  outline: none;
}
.no-shortcut {
  min-width: 20px;
  color: transparent;
}
[dir="rtl"] .no-shortcut.pull-right {
  float: left !important;
  float: left;
}
[dir="rtl"] .command-shortcut.pull-right {
  float: left !important;
  float: left;
}
.command-shortcut:before {
  content: "(command mode)";
  padding-right: 3px;
  color: #777777;
}
.edit-shortcut:before {
  content: "(edit)";
  padding-right: 3px;
  color: #777777;
}
[dir="rtl"] .edit-shortcut.pull-right {
  float: left !important;
  float: left;
}
#find-and-replace #replace-preview .match,
#find-and-replace #replace-preview .insert {
  background-color: #BBDEFB;
  border-color: #90CAF9;
  border-style: solid;
  border-width: 1px;
  border-radius: 0px;
}
[dir="ltr"] #find-and-replace .input-group-btn + .form-control {
  border-left: none;
}
[dir="rtl"] #find-and-replace .input-group-btn + .form-control {
  border-right: none;
}
#find-and-replace #replace-preview .replace .match {
  background-color: #FFCDD2;
  border-color: #EF9A9A;
  border-radius: 0px;
}
#find-and-replace #replace-preview .replace .insert {
  background-color: #C8E6C9;
  border-color: #A5D6A7;
  border-radius: 0px;
}
#find-and-replace #replace-preview {
  max-height: 60vh;
  overflow: auto;
}
#find-and-replace #replace-preview pre {
  padding: 5px 10px;
}
.terminal-app {
  background: #EEE;
}
.terminal-app #header {
  background: #fff;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.2);
}
.terminal-app .terminal {
  width: 100%;
  float: left;
  font-family: monospace;
  color: white;
  background: black;
  padding: 0.4em;
  border-radius: 2px;
  -webkit-box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
  box-shadow: 0px 0px 12px 1px rgba(87, 87, 87, 0.4);
}
.terminal-app .terminal,
.terminal-app .terminal dummy-screen {
  line-height: 1em;
  font-size: 14px;
}
.terminal-app .terminal .xterm-rows {
  padding: 10px;
}
.terminal-app .terminal-cursor {
  color: black;
  background: white;
}
.terminal-app #terminado-container {
  margin-top: 20px;
}
/*# sourceMappingURL=style.min.css.map */
    </style>
<style type="text/css">
    .highlight .hll { background-color: #ffffcc }
.highlight  { background: #f8f8f8; }
.highlight .c { color: #408080; font-style: italic } /* Comment */
.highlight .err { border: 1px solid #FF0000 } /* Error */
.highlight .k { color: #008000; font-weight: bold } /* Keyword */
.highlight .o { color: #666666 } /* Operator */
.highlight .ch { color: #408080; font-style: italic } /* Comment.Hashbang */
.highlight .cm { color: #408080; font-style: italic } /* Comment.Multiline */
.highlight .cp { color: #BC7A00 } /* Comment.Preproc */
.highlight .cpf { color: #408080; font-style: italic } /* Comment.PreprocFile */
.highlight .c1 { color: #408080; font-style: italic } /* Comment.Single */
.highlight .cs { color: #408080; font-style: italic } /* Comment.Special */
.highlight .gd { color: #A00000 } /* Generic.Deleted */
.highlight .ge { font-style: italic } /* Generic.Emph */
.highlight .gr { color: #FF0000 } /* Generic.Error */
.highlight .gh { color: #000080; font-weight: bold } /* Generic.Heading */
.highlight .gi { color: #00A000 } /* Generic.Inserted */
.highlight .go { color: #888888 } /* Generic.Output */
.highlight .gp { color: #000080; font-weight: bold } /* Generic.Prompt */
.highlight .gs { font-weight: bold } /* Generic.Strong */
.highlight .gu { color: #800080; font-weight: bold } /* Generic.Subheading */
.highlight .gt { color: #0044DD } /* Generic.Traceback */
.highlight .kc { color: #008000; font-weight: bold } /* Keyword.Constant */
.highlight .kd { color: #008000; font-weight: bold } /* Keyword.Declaration */
.highlight .kn { color: #008000; font-weight: bold } /* Keyword.Namespace */
.highlight .kp { color: #008000 } /* Keyword.Pseudo */
.highlight .kr { color: #008000; font-weight: bold } /* Keyword.Reserved */
.highlight .kt { color: #B00040 } /* Keyword.Type */
.highlight .m { color: #666666 } /* Literal.Number */
.highlight .s { color: #BA2121 } /* Literal.String */
.highlight .na { color: #7D9029 } /* Name.Attribute */
.highlight .nb { color: #008000 } /* Name.Builtin */
.highlight .nc { color: #0000FF; font-weight: bold } /* Name.Class */
.highlight .no { color: #880000 } /* Name.Constant */
.highlight .nd { color: #AA22FF } /* Name.Decorator */
.highlight .ni { color: #999999; font-weight: bold } /* Name.Entity */
.highlight .ne { color: #D2413A; font-weight: bold } /* Name.Exception */
.highlight .nf { color: #0000FF } /* Name.Function */
.highlight .nl { color: #A0A000 } /* Name.Label */
.highlight .nn { color: #0000FF; font-weight: bold } /* Name.Namespace */
.highlight .nt { color: #008000; font-weight: bold } /* Name.Tag */
.highlight .nv { color: #19177C } /* Name.Variable */
.highlight .ow { color: #AA22FF; font-weight: bold } /* Operator.Word */
.highlight .w { color: #bbbbbb } /* Text.Whitespace */
.highlight .mb { color: #666666 } /* Literal.Number.Bin */
.highlight .mf { color: #666666 } /* Literal.Number.Float */
.highlight .mh { color: #666666 } /* Literal.Number.Hex */
.highlight .mi { color: #666666 } /* Literal.Number.Integer */
.highlight .mo { color: #666666 } /* Literal.Number.Oct */
.highlight .sa { color: #BA2121 } /* Literal.String.Affix */
.highlight .sb { color: #BA2121 } /* Literal.String.Backtick */
.highlight .sc { color: #BA2121 } /* Literal.String.Char */
.highlight .dl { color: #BA2121 } /* Literal.String.Delimiter */
.highlight .sd { color: #BA2121; font-style: italic } /* Literal.String.Doc */
.highlight .s2 { color: #BA2121 } /* Literal.String.Double */
.highlight .se { color: #BB6622; font-weight: bold } /* Literal.String.Escape */
.highlight .sh { color: #BA2121 } /* Literal.String.Heredoc */
.highlight .si { color: #BB6688; font-weight: bold } /* Literal.String.Interpol */
.highlight .sx { color: #008000 } /* Literal.String.Other */
.highlight .sr { color: #BB6688 } /* Literal.String.Regex */
.highlight .s1 { color: #BA2121 } /* Literal.String.Single */
.highlight .ss { color: #19177C } /* Literal.String.Symbol */
.highlight .bp { color: #008000 } /* Name.Builtin.Pseudo */
.highlight .fm { color: #0000FF } /* Name.Function.Magic */
.highlight .vc { color: #19177C } /* Name.Variable.Class */
.highlight .vg { color: #19177C } /* Name.Variable.Global */
.highlight .vi { color: #19177C } /* Name.Variable.Instance */
.highlight .vm { color: #19177C } /* Name.Variable.Magic */
.highlight .il { color: #666666 } /* Literal.Number.Integer.Long */
    </style>


<style type="text/css">
/* Overrides of notebook CSS for static HTML export */
body {
  overflow: visible;
  padding: 8px;
}

div#notebook {
  overflow: visible;
  border-top: none;
}@media print {
  div.cell {
    display: block;
    page-break-inside: avoid;
  } 
  div.output_wrapper { 
    display: block;
    page-break-inside: avoid; 
  }
  div.output { 
    display: block;
    page-break-inside: avoid; 
  }
}
</style>

<!-- Custom stylesheet, it must be in the same directory as the html file -->
<link rel="stylesheet" href="custom.css">

<!-- Loading mathjax macro -->
<!-- Load mathjax -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/latest.js?config=TeX-AMS_HTML"></script>
    <!-- MathJax configuration -->
    <script type="text/x-mathjax-config">
    MathJax.Hub.Config({
        tex2jax: {
            inlineMath: [ ['$','$'], ["\\(","\\)"] ],
            displayMath: [ ['$$','$$'], ["\\[","\\]"] ],
            processEscapes: true,
            processEnvironments: true
        },
        // Center justify equations in code and markdown cells. Elsewhere
        // we use CSS to left justify single line equations in code cells.
        displayAlign: 'center',
        "HTML-CSS": {
            styles: {'.MathJax_Display': {"margin": 0}},
            linebreaks: { automatic: true }
        }
    });
    </script>
    <!-- End of mathjax configuration --></head>
<body>
  <div tabindex="-1" id="notebook" class="border-box-sizing">
    <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Notes-on-Latent-Variable-Models">Notes on Latent Variable Models<a class="anchor-link" href="#Notes-on-Latent-Variable-Models">&#182;</a></h2><p><strong>All the notes below are from Prof. David M. Blei's paper: Build, Compute, Critique, Repeat: Data Analysis with Latent Variable Models</strong></p>
<h3 id="1.-Box's-Loop">1. Box's Loop<a class="anchor-link" href="#1.-Box's-Loop">&#182;</a></h3><ul>
<li>Formulate a simple model based on the types of hidden structures that you believe exist in the data</li>
<li>Use an inference algorithm to approximate the posterior (e.g. MCMC, variational inference) - <strong>the condional distribution of the hidden variables given the data</strong>. </li>
<li>Use the posterior to test the model against the data, identifying the important ways that it succeeds and fails. Some techniques to assess a model's fitness in this setting: predictive sample reuse (PSR), and posterior predictive checks (PPcs).</li>
<li>If satisfied use the model to solve problem. If not, revise the model according to last step</li>
</ul>
<h3 id="2.-Latent-Variable-Modeling-Basics">2. Latent Variable Modeling Basics<a class="anchor-link" href="#2.-Latent-Variable-Modeling-Basics">&#182;</a></h3><ul>
<li>Think what types of hidden quantities might be used to describe the data we are interested in.</li>
<li>Encode that relationship in a joint probability distribution of hidden and observed random variables.</li>
<li>Given an observed data set, we uncover the particular hidden quantities that describe it through the posterior (condional distribution of the hidden variables given the observations)</li>
<li>Use the posterior to form predictive distribution, the distribution over future data that the observations and the model imply.</li>
</ul>
<h3 id="3.-Model-Variabes-Formulas">3. Model Variabes Formulas<a class="anchor-link" href="#3.-Model-Variabes-Formulas">&#182;</a></h3><p>A model consists of three types of variables:</p>
<ul>
<li>Observation: data point $x= x_{1:N}$</li>
<li>Hidden Variable: encodes hiden quantity $h=h_{1:M}$</li>
<li>Hyperparameters: fixed nonrandom quantity that we denote by $\eta$ </li>
</ul>
<p>Formally:</p>
<ul>
<li>A model is a joint distribution of x and h: $p(h, x | \eta)= p(h | \eta) p(x | h)$</li>
<li>After we observe the data, we are interested in the conditional distribution of the hidden variables $p(h | x, \eta) \propto p(h,x | \eta)$</li>
<li>The conditional distribution above leads to predictive distribution: $p(x_{\text{new}}|x)= \int p(x_{\text{new}}|h)p(h| x , \eta) dh$</li>
</ul>
<h3 id="4.--An-Example">4.  An Example<a class="anchor-link" href="#4.--An-Example">&#182;</a></h3><p>A mixture model assumes that data are clustered and each data point is drawn from a distribution associated with its assigned cluster. The hidden variables of the model are the cluster assignments and parameters to the per-cluster distributions.</p>
<p>One example is the Gaussian misture model. The variables of the model are K mixture components $\mu_{1:k}$, each of which is the mean of Gaussian distribution and a set of mixture proportions $\theta$, a nonnegative $K$ vector that sums to one. Data arise by first choosing a component assignment $z_n$ (an index from 1 to K) from the mixture proportions and then drawing the data point $x_n$ from the corresponding Gaussian $x_i | z_i \sim N (\mu_{z_i}, 1)$. The hidden variables for this model are the mixture assignments for each data point $z_{1:N}$, the set of mixture component means $\mu_{1:k}$, and the mixture proportions $\theta$. To complete the model, we place distributions (priors) on the mixture components (e.g. Gaussian) and the mixture proportions (e.gg. Dirichlet). The fixed hyperparameters $\eta$ are the parameters to these distributions.</p>
<h3 id="5.-Three-Ways-of-Specifying-a-Model">5. Three Ways of Specifying a Model<a class="anchor-link" href="#5.-Three-Ways-of-Specifying-a-Model">&#182;</a></h3><h4 id="5.1-The-Generative-Probabilistic-Process">5.1 The Generative Probabilistic Process<a class="anchor-link" href="#5.1-The-Generative-Probabilistic-Process">&#182;</a></h4><p>The Generative Process for the Gaussian Mixture Model:</p>
<ol>
<li>Draw mixture proportions $\theta \sim \text{Dirichlet($\alpha$)}$</li>
<li>For each mixture component $k$, draw $\mu_k \sim N(0, \sigma_0^2)$</li>
<li>For each data point n:<ul>
<li>Draw mixture assignment $z_n | \theta \sim  \text{Discrete}(\theta)$</li>
<li>Draw data point $x_n | z_n$ , $\mu \sim N(\mu_{z_n}, 1)$</li>
</ul>
</li>
</ol>
<p>Parameters Classifications:</p>
<ul>
<li>Hyperparameters: $\sigma_0^2$, $\alpha$</li>
<li>Global Variables: $\theta$, and the mixture components $\mu = \mu_{1:K}$</li>
<li>Local Variables: $z_i$</li>
</ul>
<h4 id="5.2-The-Joint-Distribution">5.2 The Joint Distribution<a class="anchor-link" href="#5.2-The-Joint-Distribution">&#182;</a></h4><p>The traditional way of representing a model is with the factored joint distribution of its hidden and observed variables. For the Gaussian mixture case, the joint distribution is
$$p(\theta, \mu, z, x | \sigma_0^2, \alpha)= p(\theta | \alpha) \prod_{k=1}^{K} p(\mu_k | \sigma_0^2) \prod_{i=1}^{N} (p(z_i | \theta) p(x_1 | z_i, \mu))$$</p>
<p>In particular:</p>
<ul>
<li>$p(\theta |a)$ is the Dirichlet density</li>
<li>$p(\mu_k | \sigma_0)$ is the Gaussian density</li>
<li>$p(z_i | \theta) = \theta_{z_i}$ is discrtete distribution</li>
<li>$p(x_i | z_i, \mu)$ is a Gaussian density centered at the $z_i$th mean.</li>
</ul>
<p>Observe: local variables have terms inside the product over N data points, whereas global variables have terms outside of the product.</p>
<p>We can use the joint distribution above to calculate the <strong>posterior</strong> fir the Gaussian mixture model:
$$p(\theta, \mu, z | x, \sigma_0^2, \alpha)= \frac{p(\theta, \mu, z, x | \sigma_0^2, \alpha)}{p(x | \sigma^2, \alpha)}$$</p>
<p>We call the denomitor of the equation above the marginal probablity of the data, known as <strong>evidence</strong>. For many applications, the evidence is hard to compute. Developing approximation to the posteriors is the focus of modern Bayesian statistics.</p>
<p>To make predictions, we can use the posterior (over the global variables $\theta$ and $\mu$) to posterior predictive distribution of future data:
$$p(x_{\text{new}} | x, \sigma_0^2, \alpha)= \int (\sum_{z_{\text{new}}} p(z_{\text{new}}| \theta) p(x_{\text{new}} |z_{\text{new}}, \mu, \sigma^2)) p(\theta, \mu | x, \sigma_{0}^2, \alpha) d\theta d \mu$$</p>
<p>Note the inner sum marginalizes out the local hidden variables for the new data point, conditional on the global hidden variables. The outer integral marginalizes out the global hidden variables, conditional on the data.</p>
<h3 id="5.3-Graphical-Models">5.3 Graphical Models<a class="anchor-link" href="#5.3-Graphical-Models">&#182;</a></h3><p>Formally, a graphical model represents the family of distributions that respects the independencies it implies:
<img src="data:image/png;base64,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EiABEiABEiABEiABExGgQDdRY7AoJEACJEACJEACJEACJECBzj5AAiRAAiRAAiRAAiRAAiYiQIFuosZgUUiABEiABEiABEiABEiAAp19gARIgARIgARIgARIgARMRIAC3USNwaKQAAmQAAmQAAmQAAmQAAU6+wAJkAAJkAAJkAAJkAAJmIgABbqJGoNFIQESIAESIAESIAESIAEKdPYBEiABEiABEiABEiABEjARAQp0EzUGi0ICJEACJEACJEACJEACFOjsAyRAAiRAAiRAAiRAAiRgIgIU6CZqDBaFBEiABEiABEiABEiABCjQ2QdIgARIgARIgARIgARIwEQEKNBN1BgsCgmQAAmQAAmQAAmQAAlQoLMPkAAJkAAJkAAJkAAJkICJCFCgm6gxWBQSIAESIAESIAESIAESoEBnHyABEiABEiABEiABEiABExGgQDdRY7AoJEACJEACJEACJEACJECBzj5AAiRAAiRAAiRAAiRAAiYiQIFuosZgUUiABEiABEiABEiABEiAAp19gARIgARIgARIgARIgARMRIAC3USNwaKQAAmQAAmQAAmQAAmQAAU6+wAJkAAJkAAJkAAJkAAJmIgABbqJGoNFIQESIAESIAESIAESIAEKdPYBEiABEiABEiABEiABEjARAQp0EzUGi0ICJEACJEACJEACJEACFOjsAyRAAiRAAiRAAiRAAiRgIgIU6CZqDBaFBEiABEiABEiABEiABCjQ2QdIgARIgARIgARIgARIwEQEKNBN1BgsCgmQAAmQAAmQAAmQAAlQoLMPkAAJkAAJkAAJkAAJkICJCFCgm6gxWBQSIAESIAESIAESIAESoEBnHyABEiABEiABEiABEiABExGgQDdRY7AoJEACJEACJEACJEACJECBzj5AAiRAAiRAAiRAAiRAAiYiQIFuosZgUUiABEiABEiABEiABEiAAp19gARIgARIgARIgARIgARMRIAC3USNwaKQAAmQAAmQAAmQAAmQAAU6+wAJkAAJkAAJkAAJkAAJmIgABbqJGoNFIQESIAESIAESIAESIAEKdPYBEiABEiABEiABEiABEjARAQp0EzUGi0ICJEACJEACJEACJEACFOjsAyRAAiRAAiRAAiRAAiRgIgIU6CZqDBaFBEiABEiABEiABEiABCjQ2QdIgARIgARIgARIgARIwEQEKNBN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" alt="gm_example.png"></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="6.-Example-Models">6. Example Models<a class="anchor-link" href="#6.-Example-Models">&#182;</a></h3><p><img src="data:image/png;base64,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EiABEiABEiABEiABErA5AlRkbK7ImGASIAESIAESIAESIAESIAEqMnwHSIAESIAESIAESIAESIAEbI4AFRmbKzImmARIgARIgARIgARIgARIgIoM3wESIAESIAESIAESIAESIAGbI0BFxuaKjAkmARIgARIgARIgARIgARKgIsN3gARIgARIgARIgARIgARIwOYIUJGxuSJjgkmABEiABEiABEiABEiABKjI8B0gARIgARIgARIgARIgARKwOQJUZGyuyJhgEiABEiABEiABEiABEiABKjJ8B0iABEiABEiABEiABEiABGyOABUZmysyJpgESIAESIAESIAESIAESICKDN8BEiABEiABEiABEiABEiABmyNARcbmiowJJgESIAESIAESIAESIAESoCLDd4AESIAESIAESIAESIAESMDmCFCRsbkiY4JJgARIgARIgARIgARIgASoyPAdIAESIAESIAESIAESIAESsDkCVGRsrsiYYBIgARIgARIgARIgARIgASoyfAdIgARIgARIgARIgARIgARsjgAVGZsrMiaYBEiABEiABEiABEiABEiAigzfARIgARIgARIgARIgARIgAZsjQEXG5oqMCSYBEiABEiABEiABEiABEqAiw3eABEiABEiABEiABEiABEjA5ghQkbG5ImOCSYAESIAESIAESIAESIAEqMjwHSABEkg7gchdmFjZAxXd5a8Kui/ySXtYfJIESIAESIAESIAEUkGAikwqYNErCZAACZAACZAACZAACZBA9iBARSZ7lANTQQIkQAIkQAIkQAIkQAIkkAoCVGRSAYteSYAESIAESIAESIAESIAEsgcBG1ZkfLC4axVUrDwBuyItwAzcgYmNK6NGj4XweWThflZf0m7h4Of9Ud9D1haUx5Pv7sXDdKVJQ8S1I9i88yzupSscPkwCWUzAtO6mMcZtu5kwMWF7MaV+hbhrcqxU3yN3TkB1W1oLZLDsuggXE5LMxCtB2DW+sSqj3ljsa0lAS9SPEPT722jqURu9Fp1WZ3QkEJdAdH1TbWSNcdgeosW9CQ1h+yajkb4+L6n3LN5j6rmUtZUZ8H5m93Y+w+XmA1w7sgO7TgfHQs/wOGKD5hEJCAErKzIaIgPPYteyTzBxSG90bFRVNXRKSFVujM4vvI3FO8/jXnxZldZycnRBCdeCcCnxBPJaOZfJJzkcvsvfwNA551Ft9KdY+M1ifNqnCh5L/sHEfUTuxuTWPTF69l5Y6Pol/hzvkEBGEtBC4PPLHIzr3xb1PDxRr2VPvDx5OQ4GhKc8livn4B0m3gOwa8s/CI3zpOq8/L0D225GxbmKbF3f4yaVZwaBXMhT2BWueQuhpGs+azdGRiL4m6kEwnHz6DrMGT8MfTs0VoMA0e19x95jsfzU/WRijsTV877QRUHofmzdfyue/2D8s20P4l+N5ynhaYrbyvS+nzbQzmew3Izc+R7a9xiNuX8GxHLP4DhiA+YRCUQTyG1tEA+Pfoc3Jq9CiHnEYf44u3cFZu7djC1vfYcfR9aGk/n9tBzna4AxPx/CmLQ8m+nPXMW+X/7BA+dOeHFUD7TKk+kRMgISsAKBCPh9MxI9/W/ggRHbxSPYqf527TiCz36ahS6lHY07yfw6olChPGrEfjv2h3RA+4IOMf5jOi9PuME16DYC74TqI/mPZev6nkxWc+xtB+SrOwZr/82eUjrHFktGZTziHDa9OxZvrzoVKw8kbNXe+/wdBMcnUigLchVEofy3owc1OjyNAkb6wk5i+1Z/FHN7AsH+wQgMkpm/jGxM0/t+2kA7bw25aY04jHeCvzmSgJXnKhzweL2maFmuIXqNnoyPvl6CRUvm4N0+tfC4jj8Yx2fPw8/+6TOy0oOKb1IRc159zAKse7enyaSreuu3sM7XfGToIYKOfItxz9RFJX30qDlenLEZFyNiporuHcHiVzup0WYxCZPRpXZ4bcnfCDJmkkzxfIVVY9urEajGmLgzKPbl0u+3wdRDygAsbDWGVZIwxDwuCMcWvYaOtT2jw3WvjnYjv8HRQHMW93Fx60y82DhmJkvFX6n2MKz4/Qt0r/QS1sjQ1YkP0FZPl2FyJ/lZjondGkTnR5mxVW/5Mubu9ENETKqip+8bYezChXijdfXEzfVic8EjErBAIEp1KALhXLsHRr39Bga3KQ/nGF/a9Q2Y/MnOeLMrFoJQlx4F3UEgCqNJ+8YoGH8kNuQA1v58DU88/QwaPxaJW7dDoM/NxKnvoTj5eXd4ujfAy2svK0MScWp0dNmLqOFeH4NXXNCvaYF/45vXu8TU5apoOmAmtpnLgogL2DZjIJpWLq/XyUp1+2LG1nPR8elhxv8vxpyq8kgsXjEJnWPqcqXGw7H4yGVc2DgFPetG1+9KdftjzsFbMWmTcJKWO7F1dBEmGrLJozleXnQIARc2YIpRvz0aot/nf8XKIyOJWgAOfjUcbWLykkBuKX9J8khMrsUxnRF51AMf7bttxKp+7+Lcrx/GyqzK7fHG2nPxZE/stt2mfH63Gh+/0Dx6BN/dE/W7TcEm87Ixi4GH2ZGAqoNfvIU3TEpMHhSu2RUvvzUJE98ejUH9OqBmseTGUSMRdEeZKDnWRdvWxRGqD2oYDa2G0D/WY+PNUujQqY6yZgjB7UBp0TTcO7oEozrEtN/S3rV+Dd8cialrvosSaSvN6+5baKfqSfXxu3Df3JQ0/AjmdFRtb7URWBcQ0y5rPljet466NgyrLhstqkqGrbTz92K2z9dNTyNxcVHvmP5HTP9G+hLy5zUW2+9HJcE2+tkqL61WM2hhOPl+B/05YRgZRzbHvKtKbhxdNtEkDyuq/k6boXOx64oxBGZWHmti5WbFePIjO775TJP1CVhZkVEZLPg0Zv2mZl/GDUaPDq3RslFjtBzaFy2MKZjIE9h72LwhzFgoYRs+x6e+9fDmgoWY/V4fVPJfiwnDvsYp3UBb2c56f4sRA2bhkMcIfL/vT2yY8RRufvMmXvviqOoKKffoGk7/VwLdp87BwiWf4rX6odgyYyI+j9N4Kx1lw0f43/6i6DFmFLpUzhubidy18dKS6ejlrkajHJvitYXfKGVuCOrkDseVf6+hVK9JmL1kIT4fUw9Bv87CmM/2xXT+7sNn0XB0eeVbnKvwAt6PUQInD3kWTzbpjimLRuMpGeBSNunvf2OEqSH81NcYMuA9/BrVBv+btxAL572DLgUPYe6QV/DxwcDYdCkznk0ffIoDT3TBa293gVdybYzZkzwkAYNArtpj8f3qT/D6y6PwzuIf8Fn30jG3VMfj13XYcTv5lRBRgXeUuYgD8jZuhiaO5uZlKoz927ErtCTat6qOxF/RAqjx6iQMqxCCnR/OxY47D6EF/IIPZ+2DQ/OxmN63PBwi/sWSV4bhw4Nl8crK3fjrl/fQ9OYyvDZyEU6GS2cpEAdnjcKoxSfwxLPv6HXys5cK4vefjpg64UaeE/yGbcasubfRcdoX+PKDAagevAOzBnfFc5NOoPqbSm7MHYtWTn9j3ktT8esd4ZECuaNHouroh8txp9O7+PrraehfQ+Xvg6Ho1H0GTtR4DV8s+Qzj2jjh7zlj8b9frsdN1slvMGNjPvT76GslA/6H5zxvYsv00Xj3lyvRylSyPKKDiyvXnHDnl6kYNucMKr7yiTKR/RIznm+KiqXym8V9Bmu/jzGhnTcJz5a7gg1vjsNXSZoV3cSOmR/jj2LP40MlC2e/1xOlfZZj3PPvYZvRgTSLgYfZj4AWsB3zFh+PUfqd4DHwa+zYMAfjR76MoS+r9/P9vqiSrC11BALVQAVQDI2a1YZjnEGNW9i/ZT9Cn3gKLeu6xAHw6MpZnCvdA5OlvZs7CvWCNuPD1+bhz1BVr0t1SqStjAlC1d2Zb/+JYr1ew8SuleKaezvVwSszBqH8/e2YNXMH7mgPEbDuc3x8IDea/W8Sepcxm2GyyXY+N0p2Uib+0n/Q/xbioyF11SCzI0p264h6jzsgcbaP6c8uGNNU+XZEud7T9TC+HlrbgpwOxakvR2Hg5K2IajdBl62z3+uCgn/NxssDP8dB8/UFIks/uYiGbym5qcutGymQH3FeB57kBAKa1d1D7e6FndqSaSO1Po2qaBXKucf7q6x1W+idglR5a4u6VNYqeI3XdkZY8B6xU5vgpcLuslDzldvGedVXtLX+kTEP3NC2jWmk4u+szT55X12LOa8+VtsWHBXjx1/bNKKeViHOtZhb6ifq5Gdau3IeWt3/7dH0UI14PJ7TvjhzL9ZjnKNk0i5+o45ps1t7ahVq/k/bJwHf3qCNrOqhVXr2S+1suJE2s0CNeI386mFc1FYOqKVVqPiStvK6kWcV9PUV2osV3bVKvZdql1VQEb+P16qpckg0bLNoeEgCcQgY751ejxPW3YdHZmotTHW8tTbjQEicxy2dRL+PjbQJv5/S1r5U26zuxdTPeu9q+4J/1+t3pf4rNH8JxEiH6f2P0u4eeF9r6+6ltZ22Xtv4VjOtQpWB2rILYcpzlBaydaxWu1wjbezWGzFJiNKCN47UqsRci/JbqvX1cNcqD1ihXTdVt2Dt4LS2Sl4kzGd0IIHazrdEnjTURm28qmIRF6jt+18Lda2a1mPhmZhr4dqFhb21iuUaqPhvKj/Jy51oJh5a7Vc3aLf0gKO0B3vf1RpKve22UDsfk8aoCwu1Hu7uWtUxWzVd+hhcPPpoi85L3qNdlP8abZiSJxWfma95RyXPw8Q3jlwz8ttN+8I7NuzoGIx79bVha/xi8m3E46m1++yYfi06X7E8TbLILE+akqz+a17RaijuneefignLyAl/sx8Boy7FtO3x2p+UpzfmHZI2/vpabWhF9f6P2aLpEiR4iza2eiWtoWp3Q/T2q6Y28MdLFoK+r536rLOqf820yXuDo+8bdcIkK+Sy8b6qejr/hBYeE1L891PT7mgHpj2jVXR/RpuxfZU24clKWvU+32oXTDIi5kH9xwbaeYssovMQdXu7NrGJp1axydva77dj+w+xOUzINiEv5TteHEb/I65sjdSu//iSVrlcDa3v0nOqjhvlkbT8iE0Lj3IyASvPyCjziYOzMbDTEHyw5Ff8fd2YRrSiylihLuq6GmO5heBZrYyK/Bau31DzLQ/P4s9dAXBs1gqNTDb5RVC9jgcQ+i+On0+YXgev2qjrrCH4+FlcMc+GR2O08DKbiTG/l5Jjh3Ko+WQRINgbZy6HI+TP7dh5rwAa9+kEL0djvUAyAYWq2a2DwcjTvBPauhl5BhzcmqNr80KIOrIPh/QRYQnHEe4tmsAzpWEnEzVvk4AQeKxQEWUkZrj7CL2X3IyMscC3GEoUd0eLjvWRJ/QQdv6tZg9D/sHW32+j2NPt8GTevChQMBeiQkLj2t8bUakZnXwNhmBS71K4uGQsxq4ORf2x49HHQ6Z+Q3Fi398IdXwSrRsXi3nCAQWr14IXbuPIMV/cPLQPx6IKokHHJnAzVbeCqPNUXZO5nCmqBAdlUav6EyoF4vKhVNni6rcAKlVwi7nmiNIV3NU6wBD4+t1JhdxxgnvtyiiqB+wA51JlUEKF7FipIsrEpNGhdEVUUlkMv+CHGxK94byaobme9+gLDq6N8XQjF2hn/8bRG4HJ8PCL3VEsjlwrgDptmqjyPY6vxkzC4m1nE5q0wR0N6hr5dkABzyrqSgSuXb+TxC6NTvBs+xQ8YvIENabr2rIdGuYJg/f+k3HzZeSPv9mIwEPcUevkTIZWjxVD8aKx7U/KE3oD588qs+xSbiju2gjPNHdB6M7d+PvBI9PMbIcONfB4vvyqdkUg5K6+LUC84B+HZ62qqs7exIkz/vHuWTr1QPMWFVVrmJgrjAYjx6JXyfP4dtgErLnfEGOm9jZ7VxN7LpHr2bWdV6aou2bNxJprpdFr2mi0KmKp/FLLVhioWfXDqt8RWQhNuzU3k6254da+E5rmCcWxP45DScUYlxb5YTzL35xCwNLbmXl5D/0DM0d+ieP3xXTDGR7d3saMMZ1R1+MmlnZ9FjNPWBJEmZecBCFfPosTwcrMY/No1HUfHe+2W4wNrgOu7P0RX8z/DpsOXlHWoIk4JVzzmRriRPzEuazivbIPy+Z9ge82HIJ/mGELLIrWo5iGIa++E1ucx5I6ue2Pq6o1eaxoYRSM4y8vChdVqxfUupw7IcbuT7mQL//jMR2tOJ55QgJpJhC93sV43A1lS0evhjOuJP77OPLlc0TRpq3RINfv+ONPb6V+7MZuZVbWRXVenHPfgKtb4t0NPVwHV7To2x6lVi3AlVzV0fFpz5gOij/OHFd7+0X8itdrqr94iXC+HYigIkGIRCrrW7xwUnyaIrmT4tAse8yjDD7iyKMYGRB1D6H3ryfDI2YdkoQcR649hkLtJ2HhuxEY//HPmDn8F3zdcCTmLxiJhrHaq+X0JHnVAXkcc8eVRQULo6gyRUpccU0yQN60KoHcKOJWXK9rujITcQ1X/NVC/DJpXIivv3PF8VTb2sj1+2H8deIq8PshZVbWGu3ruSD3dTe4mecv4jL2Lf0SX3yzAYdNg6XGaj1zj5aORe4k3S1yKPIU+nR1x09f+SBXjXZ42jM1A5a20M4/xI1tn2Ly6iso0Xs+3mrtGlsX08VWeBtKrjOKFo7HLaaOR968HWNOb6l8eI0EEhKw6ozMw9N/4Y9bRse5BvqM6YuGHoWRR3uAe/eM6wkTabUreQtADfLCqdsCnLjoi3Nx/vZjZuv8uLF1CvoOnIuTJftj5ro/1XqZb9ArpTIyiYxoAZsx6blhmHOiJAZ9vAZ7fI5gUW9DPOdCgSKF1H4sYUqZMt+YIIkA5VbBoiim2o5HqmMWZ5c4dXbjmgrHsTjc0jRSlky8vJ1DCYTh33XrcNDYoCLCB2u++Dl2prJ4XdQrLzMiSbmYBb6Gl+L10bZ+Ptzc9guW7zmMkCea650X4zYu+eGq+X4YphvqQLuANZ+vwdXiakQXh7Bo/m5l1y4enNVsjlKCnLrhy9MX4tVzX5z6qA1c8st2wKmsb+Zxp+Y4WblTKDWhpdDvfbX+QA3D6DIgXzI8WiW+F5RDMdQZMg87TuzGwqE1EHZwrlrXtz/xAZ4Upi6Bt5BAyPIqx9JuUPPUdNmagJp5q90AtYzeRdRfmDt1JXySnY2Nl6lHoWpXQmMGNzeKN22FJ3Ndxo7f1mPv7pvRM7POhnYeDj+/ADzUrmHbhBcw+POTKDn4I/z012mc+aZ3CmZR48WdxKl2+WfMWXYJT7ip2dxDS/HFzoDodWZJPGPcsoV2Xgv4FdPfXouAkr3w3oRWKGIgzhC2SfRl7gTgutJ8WceNt4W/KSVgiJqU+k+XPwdHR7NtlU9h3Vc/YPvvP2PxuHew+LxpIjpdcaTr4eI10LCyM8L37cZBWRiYwF3Dru+3wd+xNUa/Pxyd65aE44O7uJtuHUyNgOxcg03XXdDu9bcxtEtdlHSMwL27Rg/tMRSpUx9VcwXhj+Ub4G3soJYgffEuFKmF5nULIHLPz9jsF8tX89uNDQdDkKtOA9QuYEipeM/ylATSQCDqzNcY0KYnRo4fgxfb98A7vxnmHIXQYFQf1E96sFPFGLPA11CyHcqiVadayHV1Lb5ccdms8xKjjIRHwHJ1kIW4H+P9PQ5oNeELzOjlimurP8dXh2SDi+Ko07gCHML/wc4DljYWUZ2muvXg5RCMg2pBcYBJFITg6J9HMr6TnqzcSUNBxH/kzAEcNNsNUgtQ3+U4EBwjA9yS4RE/MAvnjmXResIodHKOwi1lZmuUugWfKbgUhrN7jsDfxF2V5e4dOBhZALXUt8dM2++mICR6yRoCDmU6YWR/Vcf06KMQ+NtkdHqqC4a+Ph4Tx7+KFzpMVrtgmQrYciKj1E5ktyJNHVuH0k+hY31nXF2+AKtulICYleljiPpAgNrYJlxt6nFjD37ccAmO7V/D9Jc7o05JZzy4dy+JnQYtR53oVe0y1k+djb1ohbe+n44eRS9izftLcMh8gXqiD9tAO69dwa/TZmFLYEU8P/P1uCZlGcJW9WUaNEVt1ZfZ99NvuGx6BSJwedtmHIpiHU/09eGNRAkk261I9Mk03HisdncMabQSUw8ou1dl2e6zeipeXS0BOcLZWelUYWnQCKKu4cSuXWJGbXIOhb3QpLrpNOUHDl7o+0YPrBz6E8YPyY1RavvPsvkeQ+QdH5zK1Qpjeih7/2JqOjTiCDZ+/yvylLuH46u/wLZYHSHlccXx+RjyFimsrOmDcGjDGmzL4457x9bisy3yqS8P3adD+V4YP3g9BiyZjZdeCsLoFxqieO67aqezR6g7vBuqOZZU2yYrs51/f8NPv1ZA/ZKV0aROefQY1xfL+i7GR8MnInzEMyiP8/j1q69wKE99vDahK0qrliax727HSSJPSCA5Ao610KFFILbvOIFtq0+Y+XaEW6dJeL9vpVgTBbO7Fg9z5UM+tUuOfBeiVLPmqIF9OB7uiRd7PBkzuloQxUvGM00wC0hGFWe8vx1htd/EG13qwLPpGLT+9S0snboMXdePRvV+I9Drx1FY8+ZIOI3ujxZlC8Ah8ibOnHRE27Hd4OnZHaO6/YRR66fjlcn3MaKVG8JP/4RZ35xTsWTAFKxZWpGs3PEy9522Y7UF6oyX30XYsNYoAz/sWDQPO+9XxuBxXZQMcIaWHA+Lsd7Hqa/+h28fNUKHqoURfvwH/B7mhAqt6qs4AF+Lz6TsYuTemRgx8R6GtC8LXN6JJR9tw4PyQ/F6T7XjXMqCoK8sJVAUT42bhlE+YzH/4A19xkILOoPdP5+JSVVtNL4Sgfaeyc3Qqq92588f/XkGhzJo2rYKcPAQwks/g+6NY2Yqi7iihGFl+nghFFU23REHN+LHrblR9u4x/PTpDjU8YjZmm9tSW5m4LInFqBSRXz7Fh7/dR623XkXnilXw1KT22PzG95ix8GmsGVvXbKA29qnYo+zezkv+PsHUX/3xeINnUS/yFHbvjEm9Q2F41XBJlm1uj4pqACgMp3esx+YKTVCycj3UfiKWgBw5lOmC1wevVH2ZTzFi3H0M71wBOL8FX8/+E7lrj8Z4vY6rbbfpSCCFBMy6/yl8Ij3eHDzVy7sCRb6Yh8XrduGkGrZzrdkK3V5+Bc9cm45uHxxWoT+K/chdSuKK2Id5L++L67Pm2/htbcW411J0pmx727yDZQuK4P0Pv8X0176PfkpV4irDq2GYWgrcboracvm6Es4fvIatDsVR76Xe6Om5CGvu3UWKBmUspkNNxbd/GwvGBGDU3FkYuVntud+gHwY/VwWfrRazO5mZKYyGExZgYcEZmPHVIryzb6G6phb8luiOmX26oJprBfSaNARbBn+Br0cewsIGU7Fr9UCUbjgeP60sgvET5mPm6PXqGRW2+tbDlO/fxIC6mWGyYjGDvJgTCJRpgVfnPYtn536Gb37/B6cuAe71GqNt9wHo37UOnsiTki5ozAJfM14O7k3Qpoozjoe0Rrua8TocYb44fyUSrUqbPSALVT+bi62BVfDy4gHRm2O4dsakCRuxf/IivLe4NVaMbIup389BkRkfY+l7Y/CD/ngeFKo6BLWGa/AsUBIdZi3GZ/knYNr3k/HqclXXynfCuI+HYeOby80iy4jD5OVO+lSnPCj90hSMvLsKs0av1Bfky4YfwxdMwZiYxSwORZLhYTEB9xAUfAV7vp6ADTKy6vAEar0wC5+MrKW2rU1PR8QJlXr3RU3vrzF21U3VCc6Hcm1G4ov/jUDD1C08zIjCYRhpJOBQuAnGfL8RLTauxMrNf+LEv6fg4x8GZ7dKqF6ttlrXkszA5ZVz8I6zCFVtSNO8OSp/cBShXdqiRrztm8POnsPVgoMxefEYXB/xBWa+shkORRpi0EtdUemTjcrC4YGuUDk4WGoruyabS+3OLnw+cwuCKgxRZpTV1fCrA1x7jMVbPx3A1HkzseSZ7/Cq+acWEoSY3dv5C9i4aJvaeF5V5kMLMFb9xbr6mLhrafJs3btj/IhtGPrlAow+tBz1pm3Eyn6xoUQfqb7M/5bhh2LvYNKcjzB2vYpPZMdz72HZpH6owzoeHxjPkyHgIFu2JeOHt0mABEiABEgg0wnIBzHrvLQRld7ZgPXDPDM9PkZAAiRAAiRg2wTM5lttOyNMPQmQAAmQAAmQAAmQAAmQQM4hQEUm55Q1c0oCJEACJEACJEACJEACdkOApmV2U5TMCAmQAAmQAAmQAAmQAAnkHAKckck5Zc2ckgAJkAAJkAAJkAAJkIDdEKAiYzdFyYyQAAmQAAmQAAmQAAmQQM4hQEUm55Q1c0oCJEACJEACJEACJEACdkOAiozdFCUzQgIkQAIkQAIkQAIkQAI5hwAVmZxT1swpCZAACZAACZAACZAACdgNASoydlOUzAgJkAAJkAAJkAAJkAAJ5BwCVGRyTlkzpyRAAiRAAiRAAiRAAiRgNwSoyNhNUTIjJEACJEACJEACJEACJJBzCFCRyTllzZySAAmQAAmQAAmQAAmQgN0QoCJjN0XJjJAACZAACZAACZAACZBAziFARSbnlDVzSgIkQAIkQAIkQAIkQAJ2Q4CKjN0UJTNCAiRAAiRAAiRAAiRAAjmHQO6ck1Xr5vRacDjWnAhIdaS9arqipItTqp/jAyRAAplL4LBfMPZfCk5VJC7OudGjZnEUcKKoTRU4eiYBGyYQGv4Q607cQHDYw1TlonE5F9Qv65KqZ+iZBHI6AQdNuZwOIaPzv/5kAHqs90lzsOu6e6J7Ddc0P88HSYAEMpbAm5t88OnR1A9MSCpKKmVm56Ca8CqeL2MTxdBIgASyHQHvG/fQ+rsTuJZKJcbIyBt1XPFJF0/jlL8kQALJEKBpWTKAUntbZmLSo8RIfPK8hENHAiSQ9QRkYCKtSoykXjo0fVadzvqMMAUkQAKZTkDqelqVGEmcyBqROXQkQAIpI0BFJmWcUuwrLeZklgLf4XPb0mVeIwESsDKBH46lv1NxPDAMYppGRwIkYL8EpI5LXU+vywiZk9408HkSsBUCVGSyaUml1rY2m2aDySIBEiABEiABEiABEiCBTCFARSZRrBoirhzF4Uv3E/XBGyRAAnZCQAvFzVvpH0m1ExrMBgmQQMRlHD7khwiSIAESyNYEqMjoxaOUFt/NeH9Ac1R390BF/a88qj23DP6PcbehbP0GM3EkkFoCEeewacZbGDekA2o+NQX7Qs5gcY+emPlPELjzSWph0j8J2AGBiAvYNmMgmlYuH9P+q36A1wAs99eQxw6yxyyQgD0TYC9dla525We8OeALaGO/wZHlDljVdxC2dFqCHwZ6wsGeS595I4GcRkC7hE1j38aOpz/DnDd8MKnhOMwZ64NbRYdjZXs31vec9j4wvySgy4SX8TFexvITi5Fn5VB02dwa61YMggc7AHw/SCDbE+CMDK7j1w9mYkf5oXinZ0U4OhRF6XIP8ff2I7iR7YuPCSQBEkg5AQ2huxZgxqHK6NOuFBweL61GX8Nx9EB+vDKlC1zZaUk5SvokAbsg8Ah3fvkE72wvh5Hv9oCHoyNcS5dA5KE/cOhG6r4BYxc4mAkSsEECVGRC/sbW38LQoGMTuOkdmXDcu0sBZoPvMpNMAskQCMTfW/citH591HCWyp4fRZ5whlO7XuhSxjGZZ3mbBEjA/gjcwl9bDiCsYTu0dBMDFQ0P7t1DlP1llDkiAbslQEXmtj+uRuRFCdeC0YUcfgHHj4fDq3ENFA9YiRe9Xsa624+gXViEnuV7Y7FvJDT/lRhUeQhW+VPhsduawYzZIYFbOH/2NnLlz4/HVYclwvtX/LQ/GOEX/Dj7aoelzSyRQPIEguF/5S4cS7qiiO45FGePeSOycj3UKX4Nq9S62WFrryn95iwWd6+P7ovUh66VKdqqF5pj0IpLXFOXPGD6IIFMJ0BFxq0CvAqGwT8gWAmlh7ixfRU2OvXChOe94FDEFSUcgnAnJBCHf/gZ3o6BCLgRDN9NG+Hd9Xl01EdwMr2MGAEJkECGEIiegQk/eQwnvTfhvRnn0XpgPTic/R3fTB6FKTtvZUgsDIQESMBWCBRDhcpF8eh6AG6rnT60gF1YvsERz0/qjUoOBVG8ZC7cuhOK8EPrsOrMPQT430Gk73as9n4KL3YuyzV1tlLMTKddE6Ai83gjDJ/cAhc+HY1RY0bgrS1lMX3Jm2haWE0zO+SGk5MyQQn9Cyt/fQLtmzsjNOQkNq1+gB59G6CAXb8azBwJ2BuBEmg3qCtKnJ2HgSP2ot60yXipc2OUjzyLf/P3w9hWxewtw8wPCZBAkgQK46kRo9H2wlyMeHUUXn7jN5R9fx7eafaEUlJywdFJ9iy7iT9WHITX008iIvQWTm3Yirs9u6NJAS6qSxItb5KAlQhw1zLkhUev2djTywLx3K4oU+4+Tn2zFIfaDcI0zMPcpV9gT/6O+L4O1RgLxHiJBLIxAQcUaDYVe3ynmqVxLLb5jjU75yEJkEDOIeAAR4/emPdnbwtZfhylyj6BuydXYvHBWnh1RhQOzP4Rn/3hhOdW1IKThSd4iQRIwPoEOCOTJHM1I+Psi1825sFLg1uiYtlCOL3PD9UHPM1tGZPkxpskQAIkQAIkYMsEHJBbWWRc3Lgbj4Y+jxYVy6HMvwdwvEZPdPGgGmPLJcu02xcBzsgkWZ5FUNq9IAqUHIQ+5fMi4mgh5CnWBv3al85021gXZxZNkkXDmyRgJQKFMqguFsygcKyUbUZDAjmcQG61FXNpOBVwxfA+as1s5GkUy1MaXs+3yPSt2jNK5uTwAmT2cwgBB025HJJXq2TzWnA4Ss05lK64SqoOz+HhdVHShaM+6QLJh0kgAwisPxmAHuvVbkXpcLUKO+PYa/XTEQIfJQESsAUCtecdxvHAsHQl9bd+VdGmUtF0hcGHSSCnEKBpWQaXtCgf67p7pjlUUWLmP1OeSkyaCfJBEshYAt1ruGJa41JpDlSUmFV9qqb5eT5IAiRgOwSkrkudT6sTWUMlJq30+FxOJMAZmUwqdZmZ2eFzG8Fhcb81E7R7uR5joZYvJIhZzMnaeRalEpOADC+QQNYT8L5xD9u8bydISFJ1ukwhJ7RVdbqAE01FE4DjBRKwUwKh4Q/xm2r/LweFJ8hhUvKig1dReBXPl+AZXiABEkicAFvXxNmk647MzLxYv2SCMKbtjr40ulnZBPd4gQRIIPsSkA6GpU4G63T2LTOmjASygoAMXMhMriVHeWGJCq+RQNoJ0LQs7ez4JAmQAAmQAAmQAAmQAAmQQBYRoCKTReAZLQmQAAmQAAmQAAmQAAmQQNoJUJFJOzs+SQIkQAIkQAIkQAIkQAIkkEUErLZGpqK7RxZlMXtFO3DIUD1B5BFbLucu+sae8MhmCPAdji4q1um4ryzrc1weOe2MciHpEs+p8oJyIen3gnfTTsBqiowkkS8yMG36+3ppkUX0S8tGL5qDrf7P95h12vzdZX02p5FzjykXEi/7nNgHoFxI/H3gnfQToGlZ+hkyBBIgARIgARIgARIgARIgASsToCJjZeCMjgRIgARIgARIgARIgARIIP0EqMiknyFDIAESIAESIAESIAESIAESsDIBKjJWBs7oSIAESIAESIAESIAESIAE0k+Aikz6GTIEEiABEiABEiABEiABEiABKxOgImNl4IyOBEiABEiABEiABEiABEgg/QSoyKSfYbIh+PldRnBwsEV/N27cgPzRkQAJ2A4BqdPh4eEWE5zUPYsP8CIJ5DQCD/diSq3ykG15PfsswxUtBoBx3XMUfgkxLto2HGn7RSZYciJDErtnyT+vkQAJJCRARSYhkwy/4uJSEHPmzseO3343hS0CTM4XfL0ITk5Opus8IAESyP4EpHMidfrw4b9NiZVry7//ARs2bGSdNlHhAQlYIODvC+8YRSXq8A7suhIZ7cm4XqYCPAo4WHjQ9i65uLjoMkFkg/mApsgOkSHm12wvd0wxCWQ9ASoyVigDEWQeHu7Yv/+AKTYRYHJepUplyH06EiAB2yFQo0Z1PbFbtm4zJVrqtK/vRTRq1NB0jQckQAIJCTy8+B/+0xzg5OwEh6jj2LzLDzL/En0dcPSqiDL2ocfomReZILJBZIThDNlhyBLjOn9JgARSR4CKTOp4pdl3o4YN4jwbFhamn9euVTPOdZ6QAAnYBoE6dWpbTGjNmjUsXudFEiABIRCJK2e8EYwCqP10c5RCKP7Zfhg38BD+Fy4gBE4oX62Cums/LjGZkJgMsZ+cMyckkPkEqMhkPmM9hkqVKqFwoUJxYpNzuU5HAiRgewQa1K+XINHSMaGpaAIsvEACZgTuwfc/WTPigortmqO6IxB1cCf+vB2KS+q6pq57ViwOO5qQ0WWCJaXFkgwxA8VDEiCBFBCgIpMCSBnlpXa8EVyaoGQUWYZDAtYnYJiMmsdcqyZnWM158JgEEhDQruHMyUDAoQwq1mqG1s3UAF/kSez72xsXvO8o7yVR0cOe5mOiCcSXDTQrT/Bm8AIJpIkAFZk0YUvbQzVj7OqNpxObbjbu85cESCB7EzA3GS1Rwg1ly5bJ3glm6kggqwk8uIxzF9SOfwXLo7xbSTRoUR25cBtH/j4I34sPACd3VCytpmnszIlsMLfKoFm5nRUws5NlBKjIWBG9jODKKIw4mqBYETyjIoFMImBuMtqoIRf5ZxJmBmtHBLQr5+Cj9BgHr0oolzsPSrVqhydzReLqwT9xKiQK8KoKz7z2ZFgWW3gtW7bQT2hWHsuERySQXgJUZNJLMJXPN2wQveg//jRzKoOhdxIggWxCQExGnZ2d4enJ9W7ZpEiYjGxLQMMD33PwVStgCnp5wE2l06H0U+hYvwC0E4dxRO2B41y5otoAwD6dyAiRFfHNzO0zt8wVCViHABUZ63A2xSLTyx4e7jRBMRHhAQnYNgExGZWZVi7yt+1yZOqtQSAMvqfPIRx51UY3pZBbonQoi1adainzMnH5UL16OeTRj+3vP5ERIivim5nbX06ZIxKwHgEqMtZjbYrphQH9Tcc8IAESsG0CYjLapXMn284EU08CViEQonYs81cxFYFX+WIxMSrzsoaN4KVbk5lft0qCrB6JyAp+O87q2BmhHRPQB0TsOH/MGgmQAAmQAAmQQLYg4IrOXx5G53hpcfAaiU2+I+Nd5SkJkAAJJE+AMzLJM6IPEiABEiABEiABEiABEiCBbEaAikw2KxAmhwRIgARIgARIgARIgARIIHkCNC1LnlGG+QgNf4izAfdM4VV2zYcCTiwCExAekICNEbgWHI6rwWqrpRhXv6yLcchfEiABEohD4LBfsOm8lIszSro4mc55QAIkkDYC7EWnjVuKnhKhtdX7No7738Va31gBFv/hnh4uqOWWH71rucKreL74t3lOAiSQTQj8/t9tbDmrPt7nfw+7rt+1mKqSzrnRuEQ+dKlcDO08i7KzYpESL5KAfROQQY4dPrex6ewt7L9+D9fCHlrMcKsS+VHXLR+eqVwUbSoVteiHF0mABBInQEUmcTZpuiOzLt8euoZvjgXgeGD0SK0IqmmNS8FFOjjlYkds918KRrASbrsuBmPy/qv6X63CzhjbqBRerF8yTfHzIRIggYwlIB2SJYeuYsHRAFNnRAYf5rQqp9fpqmpmVVyIqvv/KgXHLygMv6k6PWjLeUD9id/+tV3RvYZrxiaMoZEACWQ7AutPBuAH1f4bg5fSpverUhRlCzmjmlJYCsZYYZxW1hnS/u+5GIRPlWyRPxkEeaWOK4Y0KMUBkGxXskxQdiXgoClnjcRVdPfAuYu+1ogqy+KQ0dqB6330zo4Irykty6KtGpFNifmYKEDrTtzA5weu6gqQPP/p0+XtfoQmJ7wXWfZCZnLEOaHs5u71wyw1yCCjqaKQjFCDDCkdNRUFaM2JgDjPv9+hgl3PuuaEdyKTq5XNB59T3wHvG/fwzrbzugIjCskENXjZq6ZrihUScwXIeH50s7I2/z5IBnLqO2EXhWcDmaAikwGFJErI2I0+WHLmNgwFJj2jryLQpu720xWaN9TozJT25VOkDGVAVqweBAWc1ZFnWIT2XHbSKRmxwUc3HxMFZkKLckjr+hdjltZQiL57poLdzrja8zuRYRXHzgPKie+ADHiM2XVJn1ERBWZwg5JpbrPFJH3WH5d0hUisOb7vXTXFylB2fbVy4juRXcvCHtNF07J0lqp0Up5ddlLv8Ij52OvNy6ZZgBlJESVIZnKmbr+gTzeLPf6GgTXSHa4RPn9JgAQSJyBKTOvvTugeMkLpkBlZGVmV0dkBq0/rJmcn1bq5T7p4Jp4I3iEBErAJAm9u8tHbaRnwmNvVK91KhwyYrHmhJpYevqbLivpfH8HOQTXteibXJgqaicy2BLj9cjqKxlyJWdfdE++2y7iZE+n8SEdHwpVFxaIsSXx0JEACmUfAXImRzkNGrlWTHYp2DqsDmWUVe3jpANGRAAnYLgFDiZE6LcpHRu5CJrLn7Ct1dTgysCKyiY4ESCAhASoyCZmk6Ep8JSY9pmRJRSjhmiszSfnlPRIggbQTkDUtxkxMZo6AygCFocxM33Eh7QnmkyRAAllGwFyJyazZVdnFVGSROJFNIqPoSIAE4hKgIhOXR4rPZu/x02dKRMnILCXGSIyELyYuMjPDjo9Bhb8kkLEExOxLFvVnphJjpFg6PkPUTkayW6FsEkJHAiRgOwSkzsqsqgxIZJYSY9AwlBmRTSKj6EiABOISoCITl0eKzmQxnnRApCOS2UqMkSCZZjY6PuYf1TLu85cESCDtBGSxrgwUyICBtb7l9HlXT31zENnpkGajaS87PkkC1iQgdVXqrL6xj9qIxxpOZJIxmCmyio4ESCCWABWZWBYpPpqw7YK+O4l0RKzpJD7ZllF2NKFLP4G9e/Zi8aJFuHvX8ocN0x9D6kI49985fP7pZxj60hBI2uisQ0A6JrKjmCzWzcg1McmlXtbBLXrWU58Fkm9P0ZEACWR/AlJXZXZE6m5KPq2QUTkS2SQySmQVBz5STtVo5/39/VP+UCb6lHRIv0PaefmlSz8BKjKpZCizITJyK1ssWlOISTIlPolXPrTFWZmkC06Uk82/bk7U03M9e2LwwIGY+f4HifoRxcKawu+H779HgYIF0K59ez1tEr84ycuxo0ezjcKVKDBr3Yg4h02Th2HQiKHo3rgzJm27hvR8DMvomMgWy9Z2skMROyfWps74SCBtBMwHPdK6HXvaYo5+SmSUKFEc+IilmFQ7LwODRjt/N9TygKW0s0ZbGxtq5h39smkTrl65ihcHDcLXX30Vp59i7bRkXi6tGzIVmVTy/vrgVX1WRPaJzwpnxLvqeEBWRG8zca5csQKjR4602PkXpcDFpRC+XbYMW3fsQP78+RPkS/w83a4dDOEnyoQxW/LG2LEpFnyiCMke+qtWrkoQR/wLU6a+h6HDhqFP3z4oX6G8Snuo7kXSN/7NN7Ho64XxH8l551oAdr47Ft+5jsbCr77EZy/lw5rpy3H8UdpRGLMxWdExkVQbnRP5IC5dLIGH+97Fk6ruSP0x/irVbosXxy/ATt/7MR7v49TnXVHJoyvmnDKuxYYhR49OfY4OHpXR4fNjSPo1CcKu8Y1RsfIE7IqMG4ZxFrlzAqq7N8bEnUHGpQz+1RBx7Rj+OHoNEUmG/ADXjv6FY9ceJOmLNzOWgNRRUSSyYtBDcmI+8JGxObPN0KRdlXbekiIibe9ff/1paucrVqqYIJPip1+f3rh+/brpnjFbIu18aiwjREZJHyE5J228tPXNmjdDrdp1cO3aVdMjkg7pd1hzANUUuQ0fUJFJReHJaIx89LKfWhtj7dkYI5kSr7HjkXGNvwkJHNh/QL+45489CW5u+HkDJk6apAsSS8JNHpg/bz5eePFFGPcHq+Mff/ge1apVw8kTJ3ThlxJh85/Pf3r8Xl4pN0MUoXzh/AW4lShhSvvr497AF/Pm5XABp+HeoSX4cGd1jBpYHY7qX+kK7nC6dhbet9K2Nbks2pWOSf/aribW1j6QzonY2y89xsEJc/ZaRATCURitP92L/y5ewOm/1mL2uObAns/xcqfhWOwtiot6B5q0R+u27dGolKP546bjXKUaolPbdujUpDSs2uAFrMWwqlXRfVEqttkO/QPvP/cqfrjwCHlMObB08Biizn6Lwc/NxL7Q9MxHWgqb1xIjIHVU6mpWDXpIukRWicyiVQYQGhqiF9WmjRsTFNkfu//AYGW+JQqD0Y7H9/T1Vwt0ZUL8iBPlRaw0pJ338/PTZ3NSoswYfQGvypXjR5HouQyOHj92FF5esc9IOlq2bq1mahYk+hxvJCRgVbmeMPrMu/Lw4HQ0Nh85C/0dE+tVQPXxuxA92HZLjb41R6U2H+FoeMoagkPKrEzcM5WLZl7CUxCyET8FWdKwZFbj9992JPB06tTJRAWbeBZFYvfOneg/YID+rExdH/3nCKZOn4Gxb4zDsh9+QOCdwBQJG2/vs3oYtevU0X+T+0+E26SJEzDytdfg5uZm8t6xU0d9lmbFDz+aruW8A3/sWroJoU93ROMCDrHZj7qH0Pspq8OxD0Uf/XUxuk7LB2iz0vVUMkVMVuniE3BCkcL54aD+OZasi04D38WiFVPQ2vkg5n68BQFabhRqOApfLxqFhoUtf9/ZoXATjF40D6MbFlOhWNHdv4NbqXovw3Fh5QKsdumPN3uUSSatSoHr+zqGuWzG5yu902VaaUUi1ovq4QG83yBhex8726YhdOckNPTojI+PRM98J5c4GciUOip1NSudIav2X4qWXVmZlqyO+8zp06jzZF1s2fxrgqTs2L4dzVuogY9EnLS1y5cuRQ9lZi5O2v0N63/GxHfe1tv5b9U96UPMnTM7kRBiLxsDliVLxg4+xt61fPT66DFxlCjDl6RH0iXpo0sZAbtVZHIXd0NsN1AaiEVYdytKTdsH4I6wufMX1v4ahJp9u6K2U8qat3/9oz9I1UCNoGalM+KnILNcCoYAeKZjJ10wGefiW4RV9eo1LD8Yc/Wff/5B4SKFTcqOKENyLsqEOFEwZNTkz33JL8gXQSvC0NwZiw9lClv+pk55T59pkXTKzI+kTxSm+O6pps3w77//xr+cc85v78eGHVFo0rQKnPVcP0JIYCAe5cqHAnlTVofjwzrufxetSuTPshlWIz1N3KNlCgcnDCKJ/SqFRnU+h3Yvh/s7f8HuGw8Rx9zLdxG6u9fH0OnTMaiRFyp2XYSLkbswsbKH2SDWQwQd+RbjnqmLSjFma5Xafo5Tht1Z1Dlsnd4X9T3EpK062o1dC98Iy4qyFngAC4a2UeZmyq9HA/R8d4PuV09Tqw9wEmE4+X4HFU4KzNEencLapd6o3fdpVErydX6I4Jt3EOHgia59K+Pk0g3pMq1MjLRNX89dBK5usTN02oX1mL/mMhBxAzfuyOytP/5YsxOBtZ9FzzoFUpTVswHR7b9RV1P0UCZ4EqsMkVl7LmaWeWMmJDqTggwODkGv53rrFgzSthvOaPMtmY0bfs79F20tUVcpQuJ2796l/3bu0kX/lWelDyGDmMk5SwOWkh6jjTfaeWn7JW3S5gcHB2H23DkJgjaUr6NHjia4xwuWCditIoO8BVAwl1JcIpXQCj+OtSsvoqKXG6JCQvFAGSxcWPsjtudqi+F9vJIZ+YoFd0J1emRaOavMyoyUSPyye5lfUJhxyS5/pcLLWhVzASUZlXNjKtdSxkVANWrcCF26dtVvm5uXibBq3aaNpcdM186eOaOPlBgXRFiKLau5k6lnMf9KzokZWo2aNXVvkh/ZqWS6so+VxX4yhS0mcPUbNNCVI1FiLvr6olTpUroAlLybO7kuM0U502m4//de/BUZioOfvYTuXZ9Vf93xwsf7EFmsPDyKWh6NT47V/uv3UL6QU3LeMv1+aZdo1ex0TGcp0yO06QgKoHqD6nCK8sO5i5bWiNzC7m92IE/vafhyaifEXc2oIfzU1xgyYBYOlRqCb/edxn/HtuDLt5+Bx2MxUCJO4c9bHfHtkUP4+d0mCFo/BW8qBSOBKqNdwOoxr+Gzqy0wd98J/L2yD7B2Kt5Z+R9yt56FU7veRg2lctd4Z5tK537MbF0oSeramT3YcaU0GtUtadYm3Yfvxll44/XB6FitHabsvYYLiwbi6Q8O4q6WB6Xq1oX7lX3444wlDklGZ+c3VTtd0BFinhiJUBz7aSN8K1VC6ZjZW+3CL/h2ay50fqUbyiepNMZiMupmleIJ11TG+rLOkcisc0H283FMS+28tPHx235zunLfxaUgWrRsoV82Ny8TJUD6AEm5v//+W79tWD4Y5ujGudyUzXfExW+L9Ytm/8mzMjNkOFFUZO1NqOpvyoJ+uV+wYEHdzE3aeZlxadLkKcha3vibFYgCJYOfhnJkhMnfxAnYryJTxBUlHEPg63cDAb98i+U3GqK3+nhlLp9z8A0VxeYM3Af0RYuCKZRiimGQskutmA06PVKcjUvkw0U7V2Skwvfq3kNf/CYKgFR4EWwiIGTnj8Tcrp27UK9ePX1GRQTCurVrTV51gVM3VimR8IzRG8PT5ctq5C4ZZwi4pLxJuKLsVFF28uJksb7YxK7bsEFf7CeCb9Rro0wzPR2efhrDR4xINEjJU851Ebhy7iLCXXrio183Yv3GDepvAYZWc0KeGtVQIW16jG5rXtMt6zsmxrdrgpWMoUuOgAPy5HFUnf37CL1nTKPEfcbxmbfw6bg+aF+npFpFY+78sePLZTierzdmzX8VTUs/DodCldGudWXkM7zlaYFx0/ujeuEnUH3QcPQuHYGTfxxD/K0YHh37CV/teRw93noVrUsXUCZuAzC45WM4tHB9GmZINDy46oerjuVQoWy0UqumD3Bl47sYva0yJnz+Kd7q9ACrZ7+DGcsK462J7VBENV0OZSvC09Ef//mGGKnnr06gIIqXzIvwC34ICNiOr5bdRsu+z6Bcrss45+uvFJsNOOmhBkJaFksxL6NulnTJ+oEPkVnHA+1jIFPadqOdb9+mjb4xjrTLA/v3x1dffpFo+RxRMyVt1No3UTye7d5NX8NqeP778GG9D2CcS3iWBj/FsiIjnLTrhqWHbEAgisqKVat1y4rmLVro5muGlYW082K+llQfomw594xIVo4Jw34VGYfH1YuihtiizmLtkv1wG9AfPT3d4BgViuu/rcUa35p44fk6yHqRlGPetVRlVEZAZEr3/ZkzMfeLaGEmu5PIjh6yPiWpTr2YXxlrUnr37avPYhhCTKZzzaebJTxjijk1CZQZleScEa6kVZQaWaz/fP8Bpvhl5zTZeMBwspuJ+Z+RB+N+zv59gKuX/IFyZVHKUFpCTmDfISe06dYYWWu1nrNLJmW5VzMLa15HUzHX8qiLjiNmYdUubwRparR8Vmc8+e5epFyFizEpRDGUKG5JgjvDq44XClpK2MNzOPznTTg99RTqOCcyiPVYYRSWtkPcYwWUWalaWK/P5Edfiv4/HOf/OoAreSqjQa3CMTeKoHodDyCZzSceHZ2Flg2m49BDtUOZ9yL0q9cbHx/0R4DfVYQrM8l8j8ekK3Qv5k87hrr9WqC4QwF4VCqJyH9OQXv1DXR3jakEj+dH/lx3cdU/2DxxPMZjyFcgr+IQBp81P2C3zz3ITQAAQABJREFUWze80KuWGtx8iLvX/8Cqn67gyRd7ptisnEAzj4BYGciaUNlFVMyn35k4UW/nZRCwmxrITMyJybdhFiYKjfQLjIX5sluZefs588MPIYpPUk5mdxJz5hvvxPcjbbvELRYT4pYsWhhnoyAZyDQfTDVv4+XYMFmPHy7PU07A6BKk/Alb8anbyObG/d+XYdmlxhg/qC7yBx+Ge8T3+H6BajJ7zUS3MtH7wog9c51JPqjnHomAS1cQ2vxj/PJROyRtCGArIGwznRWVGcCa9etMwkgquygj/mp7QhEq5tO/5jkUP2XKlDFdEntXMeGSXUCe7fasPp1r3DSUG3OBJ/fkefNZGRFwsgjQ3MmGAeZTyeb3jGNj6lryYig1rVq3Mm7D79JFfXcU04VkDozwkvFmp7dzwdHJfB8ntVh3/3bsLtgBc1tGr4aTelx36jnULRyKy35RqDW8Gx7bshFHLgaiyMilWDWsqure0GUJgYcn8ONHR9FwwU6MLXQIK5auwNwRX+OdMGWwlbc+Xvu+BlLeGN3BP3tPIrJgC9SsoGYv4k+VJJVB7SHCU7i5S1LBQBko64p15DGMf7IixsfxXD+JzSceIejCedz0bI2yobvx/qur8cTkxXhTbURw6YR5IGqG5vAObA+pgmk1Zf1UFAoUKYQ8Tk3R71kPM9Mz82d4HEvAGcXd1PDG/d349rtraDmxH2rnD8V+j3CsXvYtgvEMPutePpqjrKGq8TYu1C+D+wGXcSm0FeZsno7WhSktYnlm3pG089JGygCj7Nr1xltv6u1l/vwFTOtU48cuyoOYfBv9AOkfTHm3MJZ+9x3qKIsLGSQ0d6IsyU6l8Z25qbYoHNLOS7/ACNcYsDTO4z8v50bbbgyuigImA6iGM0zWjPOU/ErfIDnTuJSEk1P82O+MjLJNLlBQw/lDZ1Fw4GB0UiNYDi5FUTSXP3x8SuD5gY0Rbf34EAFXriD8bjE888laZeLcCoEbf8PRyOz9CtwJs2xSkb1TnfLUiVCLr2CIMJFrSQkV2dXLfA2M+JVpZ5nqldmPevXrmxIhO42IMiJCUT6QaewBLyMrMlVsOBntEWd8C8aYLZIpYnEyCiTT44ZipF9U/4kQlE0CzGeAjHsShgg8c8VG0mGMKBlT4RKmcU3Cy6ipcCMdtvObFxWrVkCui+fh+0CDFrgbn3x0Cq3eHY6n9B3MInH1vC8e3CuP/t/8jAVDCmDToktoL8fDSuPYpj9xOZHMGiYjidy2ymW7/1L3Y6XRcvQEvNTUHaUb9sFbX/6MP89eUGtHfHHu9GqMqRu345E4dLVQ/8ASzN0YiPL9e6CJMXuR+ANx7+SpgDr1CiJcmZ6cSpdC44jCRdUIrmMnzD4Rkw/Ji/63GkM9zJVu8ySE4/K5qyjofh9bRk/HqR4f4+Ou5VSHWq13qeAB50eBCAwR2a7aJSUfQowZmoizWL/6MCLDr8IvwGzuKiQQtx8VgleF4uaR8FgRfTx/PuQ6dwT/FOyBEZ1Lw8EhP4oWdcAV76so3r8Pmhs7Hyrl5aLakSxfx5nY9PN7aHdnF7YfDU2UYXaoq9lBZiUKKJU3pE03byONtj+xLZMleFn3Kh+ONndili2KyacffxJHCZC2VJxbCTe9nZe2Xpyx7bHRbrdsGT3IaOwMKtd/2bRR7z+If2mzpZ03wpNr4owBRlHG4jsJQ9Jk7Iwm9yUMoy8hx7IRgPl16QdI38BIn36T/yVJwI4VmWgbWeRrhVfUbIxugKCvm3FA3jYvom81mXYWpz4sdukGivYYiGfLOOJhRCQ0DzPzlWhP+v+1lF3qWt/sMYUv20A2d09p42+WCTs8lIovtrWiiMiUsrEnvJHVEa+O1A9FmZHRGsPJYrqyZcsm2ClMBJpMFYvgEiejPaLwyJS3CJ5hQ4bo53379dPvyyiQjKDEV7Bk1sbYJECEtSg1y9X0uSgm8oFLsZM1V9ZkO0bZCEDcq68M12efRNn6WY1YiROhGl946zdyxH+54drjdYyvegAfDBuOwYO/AcZ8iQ+fNhZGqxFyv9uqczsA7dTigciIKDzxbE+01o8fwql8WVjq6vX0cIHsXJbVztgRqXE5GX23Q+dQGk8N6Ihq+WLMplKdRaXA+OzGqlkj0HPQIlyqOQzTX46R66kKqww6qpm6kteWY9zIL7HvygNoQWexY+dZ3EtVOHlRq3c/NMj9G2aOm4/t3oFqMwBJ41/40ydmvUpRN5RyjMC10+dxJ/wObgaLAhKECz7XEbLmI3wY2g+fvFrbZN6c26MivB6ex5lz8n2cXNEzMOHeOKE2DNk6eQ68W/dAXYf/8MeSd/HS5J1qCbtSd879i1MPyypzPaM9S1Um7NhzbhRxLa7WRz2BVq+q2Rh9Z9LYPsHw56ubZmcfXr2ES8WeUTvhqZmuhxGI0NxQVq2diu+quUWvojLqavz71jwXmSWyK6c5UUJkIf3szz5Fp86d4mRf2mO9jVXtvDE7Ih58fHz0xfPGjqA/xayZNfoChsmZKE7y7TgxAZd4unTsqIf/1oQJ+q8MhIpSIgqRuTN2JjWUMRls3LZ1q95/eE2Zw0uY5uZjYuEh37+RNb/GgKn0NeRY8mRsTmSkzzwuHlsmkPLZfMvPZ+OrhdDqo/0495FZEvO0wkw1CjjT7BIQCF/vcNToXkHN4USojyBdhYNXF5S20N6WLaTMGJTzvnEPxuLcOEFZ6cTYorVMNtl4wErZTjQa/+v+CFTb8IoAEjvb+E4ElCgNsoOIIWzEj0z5imCSDQHkS7uGE/8ijERwGYqG7Cn/6y+/6gJIlAkROEZYEoaEH9/JjI25QN20ebO+SYEoUB998okpbOO5xd8sUdu0euijNTIiI06UJNkQQISeKFfGDi3GMznq16kWhq7cjaEWM30LF7wfofqQUmosVm3y8V8wPJuVVOZK95QJUJBaX1AGCbsmgLuq0yvUR26z2hk7IpVyiZYxWZ2e7BC/g6Oj6uT7Y81LdbBGT1AeFCpfD82Hf6m+5t0e7o4WhHSyCXdAgWYTsHQO8OZ7czCo6SfqCQc4V3sDq1r0T/Zpcw8OHgPw5fcapr0zDyM7fBa9q5lDYVR7YzHWetZF7oLNMGTEk/hjzqtosL48Bq/6Ge/Uu47z3o+hcpc2eLRhj1KkBsEjxsTZwb0J2lSZh9W7fTCx4ZMo2v559C45HPP6v4ln31dKe7e7+OqnH7H41BNY/G1zZVFwH8d278Pt2r3Q2t3RPGk8VgTyyM5xF81RWOgTKOXz9gU181WzCyqrNVOa+gjiRQd3dC2dkKexW5nU1az8IKbkSHZblA9z5zQnu3rK2llpb43212Ag5/Ktt8OHDsVpW69du6rPcIiSYygx8oz4FyVDlCJD0ZB+gOwiKs+IE9N0Y4BSBibFf/x4xWLDsNqQZ2RLZdmNTGZq5IOcRthyT5yx+Y/EK7NI0g8Raws5lrBlPY2leKKf5v8WCWhWchXKuVspplRGE7lfm1G/rTbjQIh68Ka2bUxTrdP8f7UoC8GcDbirYeoe7btDVy3ctd6ladvP6+m4GhRmvUgzKaaMfC+uX7+eqlTWq1NHW7RwoSZpOHrkSJxn5dzS9Tie1IkaPdH9hYaGxr+VpnOJc9zrr+vpate6tfbZJ59qErZxnKZAM+mhjCy7dCcxco82uWYXbfbJ+5oWdUyb3bp9dJ2O+lf74umm2titNy1Gse6Ev16XpG5npRuy+l+t1txDWZmEDIk7W70TGZKjDA7k1lptqOcgbaW/n7ZpRDOt8/xTZm1NpOa/5hWtxpMTtZ0hllqgeGkJ+U2b8GRDbdgaP7Mw4vnJglPbegdCtIPT2mqNpu3XIhXFe1tf16o+PV/zTgS/1FGpq1npDl0K0mWWyC5bcRn5TqS2nR8y+CVTe6oGI+Mgk7CkHxD/ehxP6kT8SR7i9xPi+0vJufQ5evXooUm6JDxp2yUN0s5Lf0KOU5vHlMRrz37s2LTMot6W8OLti/AJKq1GwtV4rXYD57wBz4rF1RhdQiezMPIdmaXHAhLetOKVtWdv6x/Eyg7bQFox28lGZYycJOtReRBzNJnhkOloGf2YP29+nMdkJmbrjh36xgJxbsQ7qeRZSfcXf5QmnrdUnRqmcC6FCmHY8Jf1Z2UGxzhOVWA5xfPtq8rOvWz01rUP/HHpajGULaXq9AO13eqFYsr0JnpFXHwcDctGm2cuOhg9Ahf/vjXOrwWHY4maFcrqL4ZbI685PY5Hfv/hPxf57lFptOj1FG78uB6HTWt1lPlkl1EYXWEXPvzysPraWVIuFEe/nI3NFV/BpB5lLLZXST3NewYBsch4oNp8mb2N3uIdXhUtWmTIE23Vh2ulrkqdzSq36nh0/6OtZ86bkRHmqWnnxb+YbIllxOvj3tBnX+Sa4SQs2SbZ09PTuGTxV9p3882HLHpK4UVZ+yKzSmJpIetqxPrCmI0poTYykvSkNo8pjNp+vVlLS8tIjdxaabYUz5w9l/TREBkVyQpnjMZk9axQRuU9q94LGfGQkRFx5scZla+0hiMjMuJkpEatj0lrMFZ5LqvKLqMzJyOsJWf9pYWERWZ00CkKz5ApWT0rlKLEJuPJXt6JZLKZxtsPtVtrhmlV+6/Q9LH0B2oWsV4LbcLvlmcL0xhJlj9mz++AYZUhdTYrnMgokVVZPSuU2rxn5TthtPOSZjnO6tkOiX/lipUmhJKmjLLoMAWaww4cJL/WUNPE9l92dLF1JzuWVJ5zWP8g5ZoXalo9O72Wn9DtY8+OqY8CTra/xMle3gurvwjZIEJ7KTtZc9bguxOY06ocRjcra1WyWS1PMjqz9vJOZDSXnBSevb8DWdkGz93rhzG7LuHQoJpZvk4nNe+0vb8TqWFBvxlPgKZlqWQqysOExqX03ct+/8+6i4SXHr6mxyvx24MSk0r09E4CmUJAFu7KDkDSQZCNPKzpxm70wbWwh5jQopw1o2VcJEACaSQgdVXq7NTt0RuypDGYVD8msklklMiqrN5sINWJ5wMkkIkEqMikAe7gBiX1tTID16tOiJVsZUWIva2EWKsS+a0+apwGRHyEBGyKwNyuXijpnBsjNvjAWt+JWH8yQLe3n6YGJtgxsanXhYnNwQSkrr5RxxWfHg2AtQYzRSaJbBIZJbKKjgRIIJYAFZlYFik+ktmQVX2q6qMyA1afzvSOjyHEJIFfPZv0orQUZ4IeSYAETARk44z5z5SHfJ/JGiOtMjAxaov6IKoamHi9uXXN2UyZ5gEJkECaCExpX16vuzKYaY1ZXJFJIptERnGTnzQVGR+yYwJUZNJYuLKD2brunrpweXbZyUxTZkSJkfANIZaV369JIyo+RgI2QaB7DVfTSOubm3wyLc3S8Wmt1uSIk4EJmolmGmoGTAKZQkDqrDGoKHU5M5UZkUUy+yOzQCKj6EiABOISoCITl0eqzkSoGMpMs4VHM1yYiXCUcEWJkXgoxFJVPPRMAqkm8EkXT5MyI4t6M9rMTMzJDCVmp1qwy4GJVBcRHyCBbEFA6q7UYXFSp6VuZ6QT2SMyyFBiRDbRkQAJJCRARSYhk1RdEeXit35VcfOB2s1swRHIriIZ4SQcCU/ClfCpxGQEVYZBAskTkA6D7GC21jdY36EwI+zgpVMy9KfT6KFMUbzUt6ioxCRfDvRBAtmdgKHMSJ2Wui11PCMGP0TmyO6oIoNEFlGJye5vAtOXlQSoyGQA/TaViuLw8LqmnY9qzzusj86kVqCJfxnVkeeN3UkkXAmfjgRIwHoEZBtm2eL0icdzo+2K0/rIaFoUGtkMRB+UUJ0S+ZCeLOzfMLAGZ2KsV5SMiQQylYAoM1KnpW5LHRcFROp8WjYCEhkjszAic0T2iAyy9pbwmQqLgZNAJhDgd2QyGKooIlN3++F4YJi+w0i/KkXxlPoacFXX/BY7L2I+djrgLv68GIwV8sVgta1jLTW6M6Vl2RwxC8P95TP4BbRicDmh7GRw4dtD1zBr/1VT3exZuSiaqDpdpXh+iwtv5bs0pwPuYe/FIL1jI0UiW6bKtq32vjtZTngnrFjFbDKqnPwOSN2f9cclfSZFCm+Iav+buRdS7X8+i3VflJ0zN+7iL9X+rz1729RvkE8syO6o9rJ+Lie/EzZZiW0s0VRkMqnAZGRlxbHo7VXjRyGdGpkyNneyreIz6nq/2q45agaGAs78LbCt45xUdqLQ/OZzGz+oOh2/7kqpyeCDDF6YO7nWVik8wxqWsjiIYe7XXo5z0jthL2WW0fngOwB9veyig1dNg5PmjGWnQm8lK2TQ0txJv6C/av/beha1GwXGyB/fCYMEfzODABWZzKAaL0xjhDZYCa4Nu/bDH/nQt3FVuCjlRf4SG62JF4xdnlLA2W6x5tSyE6XmrJpx2X8pejBi1a7DCIIThreKXvhbppBTojOwtlvaKUt5Tn0nUkYnZ/jiOxC3nA2ri8tB4fqNr3edQCGEo0+r+vp543IuqKxmbOxl9iVu7qPP+E5YosJrGUUgd0YFxHASJyDmJIZJSdDu5brHd9t1TvwB3iEBEsi2BKTDYalOj27GOp1tC40JI4EsIiBraOTPcEYfYHSznsYl/pIACaSDABf7pwMeHyUBEiABEiABEiABEiABEsgaAlRksoY7YyUBEiABEiABEiABEiABEkgHASoy6YDHR0mABEiABEiABEiABEiABLKGABWZrOHOWEmABEiABEiABEiABEiABNJBgIpMOuDxURIgARIgARIgARIgARIggawhQEUma7gzVhIgARIgARIgARIgARIggXQQoCKTDnh8lARIgARIgARIgARIgARIIGsIUJHJGu6MlQRIgARIgARIgARIgARIIB0E+EHMdMDjoyRAAhlDQL78bKtu4JChetJtOQ+SgXMXfW21CJhuGyVg63UmLdjtRV6kNu+pKWvKotTSzdn+qcjk7PJn7kkg2xCw1cZr2vT3dYa2mn5JfGo6GdnmhWFC7IKALdebtBSAPciL1OZb5EtKy5myKLV06Z+mZXwHSIAESIAESIAESIAESIAEbI4AFRkrFNnJk6ew6ZdfERwcHCc2Of9pzVr8999/ca7zhARIIHsT2LvvT8hfeHh4nIT6+V3G8u9/SHA9jieekAAJ5BgC0s6LTBDZYO5EdhhyxPw6j0mABFJHgKZlqeOVJt81alTHlq3bcObMWdPzIsD27z+Ax52dUalXT9N1HpAACWR/AjVVnZ4zdz6OHT1mSqwMVhxV53Xq1IaTk5PpOg9IgARyLgEXFxcUKlQI3y1dpssGg8TChYsRGBSEMaNHGZf4SwIkkAYCnJFJA7S0PNK4cSOEhYWZHt21a7d+Xlt1euhIgARsi4B0Tjw83PWOiJFyUWLE1apZ07jEXxIgARIwyQRDRggSUWI8PNwhsoSOBEgg7QSoyKSdXaqelBFcS65B/XqWLvMaCZBANidQu1atBCksrEZey5Ytk+A6L5AACeRcAiITRDbEd5ZkSHw/PCcBEkiaABWZpPlk2F0ZdalSpXKc8GiCEgcHT0jApgiIyaizMg01d40aNTQ/5TEJkAAJ6ATiywZRbESG0JEACaSPABWZ9PFL1dO1a8U1OaEJSqrw0TMJZDsCYjJqOFFqatasYZzylwRIgARMBOLLBpqVm9DwgATSRYCKTLrwpe7hSpUqmaaXaYKSOnb0TQLZkYC5yajMuHKRf3YsJaaJBLKegMgGscIwnLnsMK7xlwRIIPUEqMiknlm6njBGYeJPM6crUD5MAiSQJQTMTUYbNqifJWlgpCRAArZBwJARMujBRf62UWZMZfYnQEXGymVkLO6PP81s5WQwOhIggQwiICajJUq4oXjx4hkUIoMhARKwRwIiI0RWxDczt8e8Mk8kYC0C/I6MtUjHxCPTy4NeHEgTFCtzZ3QkkFkExGTUySnuov/MiovhkgAJ2DaBDu3bc2dD2y5Cpj6bEeCMTBYUCLdnzQLojJIEMpEA63QmwmXQJGBHBCgr7KgwmZVsQYCKTLYoBiaCBEiABEiABEiABEiABEggNQSoyKSGFv2SAAmQAAmQAAmQAAmQAAlkCwJUZLJFMTARJEACJEACJEACJEACJEACqSHAxf6poZUGv6HhD3HILxj/+t9DcNhDHPe/awqlllt+uDjnRuNyLqjsmg8FnFgcJjg8IIFsSuBacDjO3Lir12m/oDBcVH+Ga+5eSK/TVVV9rl/WxbjMXxIggRxK4LBq/08HRLf/ey4GmSi4F3JGWfVXzS0fqhTPj5IuTqZ7PCABEkg5AfacU84qxT5FefnN5zZm/3UVe5QAM3fVXWJ3N1rrG2x+CwO9iqBb1WLoXsM1znWekAAJZC0BqdPrTtzA0mMB2HU9djCipAxElMinJ+5O2COM2XXJlFC5169KUfSp5UqlxkSFByRg/wREefnxmD9+PHMbN8IfmTJcIZ8jHs8dbQiz43IoQh5Gme41LZ4PQ590Q4+axTmoaaLCAxJIngAVmeQZpcrH3L1++OCvKwhQwquE6si0L+WCckp5KVPQGU4xAsw8wHAlyC6HhOFScBh+Ph+EZd534Lr5PGa1dseL9Uuae+UxCZCAlQmIAjN7jx8m77+qx9yqRH7MaVVOn0VNbMZFZmwO+gXhz4vBWKE6Mp8eDUCtws5Y9KwnFRorlx+jIwFrEhAF5qX13jilZICLau9rFc2Lp10eRxnVByiYiMXFFdX2X1J9gH9v3cOgLef1v2mNS+H15mWp0Fiz8BiXzRKgIpNBRed94x5eVgJMZmBk1KVDuSKopqaLk3Oi3FQsklf/a+NRBP8qk5UdfoG6MPvmiD8WdveClxqpoSMBErAugd//u42B631wTZmE9vRwwYQW5VKkiIiJiMyqyt+U9g/x7aFrmKUUoQbfncAQNUPzeVdPdlCsW5SMjQQylYAMeIze4IPvzt5GQdWmd/0/e9cBV1X5vx9c4GAoCoiAbJyouFNxa85cOXJkqZlaacO04d/K7JdlmS0rK9MsR27NpoIrZwKCIkM2CKSyHIDg/b/fczl4gXuBC/dygft9/eA9413nOee8533e72rdFN1aWqhdvCzeEQdBcuivj6MViNT4ie8/LZx8Ib7/P03wwmAP6+JFeJ8RYARUEGAiowJGRTf3Bqdggpjw0ArMZFdrdLW3qGhVEvkhAvRvUib+EAOa7/dB+GqUG6ubVRhRLsgIaI/AKwfDCyUp+6a2KxeBUdcK2b290M8JT/WwL5Ts/BZ9Hkdne/MChTrA+BgjUMMQoEXMAZuCkCy0MEgDo68gJOq0L8pzWURoZnZsKRGaXRH/Yci2KyDpzIqhruUpznkYAaNEgL2WVfK2yySGpDDPdWlVKRKj2hUiQ/PEgGZev65EkqgdTowAI6B/BGQS83IXW5x4pkuFSYxqT4nQ0GTknCAwlAYJ6QxNgDgxAoxAzUWA3mFabLybr8Dz4ntNWhUVJTGqKBChWdC5FboL1TSSzrx4IEz1NG8zAoyACgJMZFTA0HZTlcQ8KQYxTTqw2tYr528hyBHVSySJJD5MZmRk+JcR0A8CqiRm7Rjdq4CRXQ1JYygxmdHPPeRaGYGqQEAmMdkPFHhGfKeJfOgyESGa1NYWvrZN8ElgKpMZXYLLddUqBJjIVPB2klEfkQsiGUQ2dLEKo64rVK8qmeFVXHUo8TFGoPIIbD6fJKmTkSSGSIy+Etm8yWRmyo4rIP16TowAI1BzEKB3ltTJcgpIDC066iuN8mhRSGZojOLECDACRRFgIlMUj3Lt0SD2lDDsJ6M+fZIYuTNEZqa2s5Xam7jtMk98ZGD4lxHQEQK0QEAeg8grmT5JjNxdIjNbxnsiKC1brLSGy4f5lxFgBGoAAmTYTzYxs4TERJ8kRoaCyAwtmtIYxYuZMir8ywgoEWAiU4EngbwQXRbuFad4ttCbJKZ4t0htjdqjdql9TowAI6A7BN744xoo7svWye10V2kZNZE3IjLk/U64aCYJLydGgBGo/gjQu0reyciwX9fqZKVdPS1mkkOh5b9fKy0bn2MEjA4BJjJa3nKSxlDQOwpsSW6TqzJRe9Tu6lMJLJWpSuDLbCsBh16dgvFjR2NwZ094dB6AcWMfw8RXDyK1zLKcwdAI0MSEgtMuE6SiqqNrU6wIIlBrjj0MpGloPLh9RoAR0IzAu+L7T9oY5J2sKhMtZvYX5GmfiE/FCx9ViXxF2spD6sE3MFHMA8YN6AIPly4YPOYxjB/3Bg6lsCpxRRAtrQwTmdLQUXNOloYMdGqq5qz+D1G7qbn5UpRx/bfGLZQPAQeM/mAH9h7YijeHWcN02Er8cmA/dn8wBjblq4BzGRABIhFEJshFclUn8mZGBIqIFE9OiqKfd3IFujq7wF3lz6PzEDz56lc4Gn23IPNdhKwbKyYKY7E+RD5WtJ7qs6dAblIgjgUkIbewU3cRfeAdPDXzGSwY2x/Dlv2GVEXhSc0buUkI9A9EUm55Mmuuhs9ohwC9owdiMzBAEAp92cWW1iOKTUMk6sszygC9peXlc4ZEoB5sxqzGbjEP+OX/hsHUdBje3LMfe/etxmhbjnqi6zvDREZLRL8RQapIV7UqRcqqXaR2W4pJ14f/JKge5u1yI6BuMiEXvo+YjZPhPnYjYuRD+vzlyYg+0S1X3UlCVZNIxLPCwJ9IhSGSTKB2BLGLdVX8Fbm5yEFTDProBCJionDln9345CVf4Pg6PDNqPr4NI+IixuJHhmHQkGHo1Up/Bteq/QLEauvu+ejoPBnfRt8veqq0vaxjWP34QvwUlY/6Ur483DqyGk9vaoHl332NL9fPgPnOT7A5sByErH42wr5fgKmrjiGrtDb5nE4RkN9RIhSGSESeetmaS6ptNHZx0hUC95AU8A8Ck+6pqTAc347tgvEbq4stY2l9VdN9IzhkPEQm5zRW9/GC98IDuEU3NvcqfpzZHZ4j3sfZtPKJ+sjIjmxUuoqBxJCpn72l1A8eyCpwF0pMJipQh66K8GSkVCTzzq5Cb5XVeGll3mUCvgzLLrWcNif/Cr8pZZ/cyVabYjrNSwRqTltrbBO2MpyKI2CKZk2bwET8a2Dvg1GzVmDjtpUYZHYWn374G1IU9WDV8zl8vfE59GxaVURUgbu30qBuylO89w/3cxC1/SvstJyOVyY4iqsR6c5ZbFh9Fj2ffxxeDcQVOrjDwzQZIVdvPCymacvEFZPfmAFLUeeOKJ7QQgffd01Qqx7feuWGFNvFENIYuR/eImA2pbNx6fIh/q0UAgpknXgfU2f9iKi6yiWGSlWn98J18eDqJjz1+Ps4mcUSWYLbeIiMqQ+mze6C7N9/wa/xtxCy8S188G8bvPrJC+X+AJ4RImVKTjr2Fy9VqsV/cvs8kGkBmpRVzWRC2yp0mZ8nI6WiWa/nCpyOiUYkrcb7rcagZuZoM+dFPOGpu3gNJ2LSJbUy8iJmyNTP2QpJ2XngxYmy7oIgNC6jMXd8a9w9egj+qXm4f3QZOjj3xvKjNLETqlq7l2JoG1dJJc2j28v441a+VKki7QK+XzIG3VwK1NUkdbQMpRTWaxZWr5uDPi5tC1Ze85B+9is8M6CDsh6fiVh5IFKohKXD71VfDFl9XtR5Hu8P9IR7m2XwI8GM4gbObZiPwVLbnug+biUOyipw+SHYvTkMnac+Cg+JxeTj1tHt2JH1CMY8Yi31T/lfLjJvl4+om3g+isk+Ydj6SwiUV6hSjbFt6uD7XhZktJCZIjyVuVg2LCurXs+TlzRSLzslbGU46QABRRh2fHwYls8+h/E1Qu1LSKGnLsE8y8NYtz0MTGWMicjAFC5jH8eAhkHY/eFrWP5JMoZ9vAZzvMpvsB+XrvzAVIW7xdJeT7n9+HReiVPFSRGyDsOcB2PZF2sfTkB6L8EejZMJ1dLFt7NwbtXgh5MUMVxkHX0NPQsnTCJ/1hEs79YOw9acEyowFUs8GSkbN0WaP1bPWYXTHs/j41f7wkqaCJZdrjw5osQ71LulYUkM9bOdrbIPoam3y9NtI89jjg49OsD0QZwguUXlIoqon/DK0t/Q5OmfcSHgN3yx5FG4WdYFcgKx4em5+N/Zlnh6y3Fcib6Iw1+/gmEuBaQ45wR+2FkHj3/4KVaOcoQifidefPpzJPl+BP+wc9g61QR7lq/CjuiGGPjBcfz9RndxD7pjuV84Iq+uwcD6uUjY/hrmfpiEvl/443LAJkzGAbz+2k5Ei5mGIvQ4/kpwQC8fe6U0Binw33cS+X36oItZwQOdmYab+WKS2qScRN3EHj69HJDw53FcNfrZTOW/72W9VAkZyu+/rR5jxpTVB/m8k+hD6I2iz758jn9VEFAEYf3gdvB9dT2+mDtYLHiIRQyX/nh+Fy1KKFN+4H5sDWqDyWM9C95NlfLFNpVaAvKiiTgpzQHc0OFVPyiVTG9ICx0egz9AQI4eX0oTT4yd2gbBm/cjyOhXMYyKyAAmtv0xbZQVQg6cAOauwTuPyh+VYk+rht2g5NuS1zANp6v0MNnpHBeryZxkBBS4lxiHRERhz9ZwdF51GAEn1uLR+wexfMUBMW1QN5mQy6r7NYONncpKKa3afHYQN8WK7/WUTFFArKj678PhW96Y/HgnQZM1p3xBsIa7jBHGyPThUSD77BoM7zgfe26KEYgnI5qBozOKaOx99XX8fG8M1n76FDyFCo4uk9/12+hkp1TV0GW92tbVpoDIXE6+o21RI8xvgvr1G4hJx11k3Sn6Fc//LxlJD+rCrKklGjVtg2EzhsK9rnhX//wOXwVY4YkPP8DCfo5oYNIUnsN80baxrJTQHMNffxdLJg1FZ3sFgn7ejBMNx+DlpcPgYNoCPZ99Ev3zTuO7nRqkH/nB2PbFCTSctASvDHaCadNHMH9OH+Sf2YZdgXeUY1OD1nBzKiApd4Nx8mQGTM58hOnCs9F4+nviQ5y+3xyeruV1JGMGR/fWaBB/DdGsYlLp73tZL5L8bhrKPla1f/ZNTHE4nr5DnEpF4F4yYhOETckvuxHUZSV+D/4bH4zMx2+vrsZeyXvYPVz1P4kEFx/4OJStVlbPxg52hQ2ShsdG7LnxQDjxSFGaLNz6B7t/TYf31LHobKrpW0XS3vWY5iMI1gp/pY1b3gms7DwUK0+UV724Plr5+MA54SSOhTKhlUfxwltTmzcUacHwv0AOcevAtJn40Gl5sffy9MiwtexLQyFazq8+3dGy9/rILlZEI2OEZMQBY996Bwv6OcHccTAmDLLBgwsBuHK/gOioTiakbtzEyRVD4NHuCWE8rDogmKBhk8aoo8jFfVE2J+AAdl6zhacDlKofigjs+f4Y6o6djSmupdGYPFy/eAFRFp3RrQ2pJGTj2j8nEeXWDV2aiZVi8GRE89OQhZAvX8PKvy3wxAdLMUxPYn9L4TzD0MlQjgaq7rqFyteuJehLal1i0jBywRrs8AtDuiILgWtGo+uKE8KEvrwpH5lpaWIpoTla2hR99+p1mYalYrHqwurHMWLOR/hTksbeQei5INw17YI+PpYaGnFB5w7NlOcUMfjHPxb1O3WHt3nBZMTCC53b1EVScATUWbAorp3BsYSG8O7ZFuZSLSaw6NAJXiCbl+tIjUtETp3GaNxQWZ8iIRLhOQ6YuHaX8HYovBkd2INvn+mI/PpuaOte3i+TGKMaizEqNxXJN8uPngYAavzhyn7faxIAZuL7z6lsBJTvWR1Yj3sN7y/0hYO5G8ZM7AOzB1cRcJmk33eQGJuKBl7ucCzkHWQzsxK+Lp0xaeOVomqbjcxhUUcQl/vifcsR2j3bY+DuZYcHmVnCZk4Qm90/4886QzB/ipdm6U7WSXzyZSp69LNB0v7fceGemMjVs4WjUyZiEsq/kGXi5C4W9pIREc2E1njeBkUsDr35FnaajcO84U0Q9MMunC8Q/Uk61j3HY/aU0RjRqzP6vvqX0ISu/invQS1mMrmR2LOoPzyEKNij8ygsWvMz/MPToMi9gA8HDcbKk8Vf3izERIhAoQ6jMXOIXcEgIvTncx8AzZuhaR3haajYZEJ5h+uicTNrWNm5wMlKdUJbD81sbdAgJxFxKVH49cvd+G/QJIxzBiIiRBwfIjZBTnhiVp+CiQvVZiXUTk4j5IOBBV6J6Fg6rlyMRL1uXdBGqv4/hPybgOZdOxYMnDwZIZRKJrFqdWIdXlwbhg6vf4w3+rV4+GG474fl7XwxdcZ4jOjfE76LP8O3L00S2z7wnvANwvPJjqEfHpk0HdNGDEGfdoOx/AjJ5DgZDIG8S/j5gwD0/Ooo/Lcvw0CT0/h0wQhhr+KNSZsbYdb4jlB9+0rv5y38eyIY9y3aw9utmBpWA3dMWLcVm1aMg83lb7Bw9GLsiM9Gbo5S8aP0egvO5qUgLjoH94+8LFRJZffPw/H+peyCCUvJWvIS4oSnQ/Hcvdznobvoge8hWCiwZN4uqXiqzG8Hx1a0uEGJrikE9YeOxgBrWuDgpBUCGr/vNBb0x6DJ0zBRSOC691mMjd8slba7tS9YvKLxpE1vTJ45GaOH9UbH3q/jaFpRSZ9WfeHMekJAeByN3onne3uJd8wT3YYvwIfb/BGenofcgA8wtNMKnCrC58XiZXQkouGOSbP6o5lEVBRiYTJX6EVYwLopeTm8hbioTNRp0gTym0idr9O4GVo0tYeHk1VRQ/JmtmjZIBPRcalIObQJP6b2xOTxnqgTLtrJImITCucZU9HfopAVof6gNWIxg9RPC2Bp0hWLPlqB5x/vB8vMKFxLFp3OTkF8ihv69bQtyFSOn4ZN0KTObSQms62UkRCZuwj/9k287tcSz3/wOhZOGQjrxD+x5xSJ8fKQkpCAnNvNMWLtbux+eyDSDvyNADXfvXp1Hj6c5XjM9J7FtG716o8uLzgvYBs+PNsDX5zxx0/LfWFy6nM8N8wHHp6TscViLMZ1Ua57FrapSERocDpMu3WGpzwPyA7FqVNpMO/WCW7yscIC8oYVury4A+ePrhYr/vJIozxn0riJRFIUYQew6WgLQVpGw8O+ER7cjsGR7YcQ030yphXvh1yt/Jsfi6ALd+Dm0wbNxPCZc3E7vjtVD107u2gxcZMrM55fRcJeLFu8HZj5MTbMbS+c7KoksZoddleBVjM34PDGWbDYvxOhwz8X23PgdPFvHI9LRoIwhL3daBQ+PLwdK4fdxqE/rhToMKvUw5tVh0BdBwx4YRme7usMh55TsPTLfTh1NUrYuAhnDld2YrGPVTn7Igjume/w6YE0uE6fgEcKJBxFCjdwRN857+Lnb5+F653T2OuXjnZd2qBOTgjOB2cVyap2p46Y5DSvjwYjP8VF6p/q34F5cFZTqE7TZkI+1ByPfnamaP6YUOyd1x6t3Fxglp+GtEzlBNmkQYOi6qiZ/+L3o40xflofMU6IVCZZp0wFkikzF7iVQy2GStTOVNr3PRXXrt7EnVazsPGPr/CUxV/4NnSQtP200xX8ejweSIlHjAh03Xjk+zi47y0MveWHPwPK8ZzUTjCr8VXdRuDWjTjXa51Qy/wRSwfVwT/rF2JkZw+0G/8zLGaPQeciqyHZiL4SiRzTdujkJdOUDAScDECOeXt0cpOPFb9kEzT2WYzdFw/jf8OLmR+YNIS5hZhMCInO7u9Ow27GdEz0tEODB1m4/vdu7Ir2xswnuhR9t0tUb44Wzc1Qr5UTnJCBNGF7nXXsVwSOXoRppWp3FK+I92UEjIDI0MruWix67yq6Ln8LcztYwLz/FDzhnor9m/5GskLoTwrRovWEWXjMsQHycu9D4eKEVkVeCCVcLRrVw00x4FWHFHcnF85WxVYjq0PHdNSHuo4D8dzK2ehj1xo9pi7D5wf+QYg0oYhC8L7F6NK4GInLikNEvAlcPBwLVlYEQf31Z+y94YSxE7sLQiJ0SotNJsrqqlIfNhVHvv8FsYOewqwuNmjV2g65l7bjm99MMGH+SDhI3ShFAnAjAiFJtujdzRFI88f/3vgZiQoHtPOSJ248GSl5H/7DX2s/xpFb9xC95emHXqZcn8IOodecJ2yh4twm4OlhQltZxBrJtRmGKYMLtk1bwck6DXExLTD+Gbo/+SJLXTi3tlVLHDs1NcMlYftm6EQekSg5WhVVlTJ0v3TWvokD+swYifbF39tyNyDG8XB/7FizABNnb0Ss9zysesanxIRBkSAWPnacFYEi7yImOBxpghY4OzSD7egnMa1VHH5Y8gq+PBGPXEUawoWRfOgdIbEtnup2wKRneqPubx/ilc//kFZ8Qfn9TyP8DknBhbTWTkhrcR2h4TeQc+MGbncajzm98vDHeyvw5R9XhcqcMO9KD8Oxk5FCeUWUcHGHV941hEYqY8TU82iPDnWSEBktJsyK/3By7Re4MHgJFvW1VvamTLJOK213ce3KNeS1cYezmu+VsqLa/n8Z3/f7YqU71hVPzBkgnoT7QkLvKIyk+xZsN4GLUzMxnsQitvkI4QnPBSZ5YjxR2MHJoeQkV1ZB/U98ew2drgspX1uLWjpWaATXFA4DF2CFsD2zc+iJKcu+wN4zVwoWDgKx+8UeKOq2RUhOIpIBV/F+yCqdKUeweU8y7MeNRW9JamIDtzZWyL+ZhuI6Hmq7UU+MJXb1cPfIFmyJ7Y1nZ/ugiYMTnHMDsFVImzFpNsY5KhdEy9T0Ee7WvcwycTP5NL7a3BCLF/Us6H85pIjUOck5iBW83GzUdtWYDhoBkRFxBvr9H/6KPo8fZrVRruzW7YzFf19F6I9TYWeShuiwHHTs7CasFXKRLNSPTIS+pHKCWvRR8BZGwdeFi9ScPDUfv6JZ9bqXKchUpuiDUy0mMib2fTF9TPtiA5NmWBVxQuc81xRN8u4iQ3ELl3e/g2dX+MN25ht4sWByUHwyobm2gjOSPmwsLpxvhpkLh8HWpC4smwlRc0IEImzHYUb/5gUZb2mQAIh4E4FnceFBQ9RPO4r3Fu6G9ZDOUDSog9gt67GXRMo8GVFzG1pg2Ceni61si5XxqE2YIiTvyVFRyOnYDi4mQpc5+hqSPD3Qul6BDRR9tO7GIjzDDZ3aCqmd4qZQE6oLT3ebh6ppKi26C+JAnssMnWSPSNXBkNjQWMjtK6UWydj1dBehSuKBbsOewYd/3EGn+V/i4M6X1LjNV+B2zElsXjkNvp7tMfT1i3Bf/D6WDxTvqXl/vLH1AzxhG4h1M33RzkXY6bzwKfyis+XmVH6FB6yZH2HLm12R9O3z0oov2fWMWvIJ/g4nIiLsXwbNwvzOWdg//xG0H7kBYQ88MWPDRrzW8zq+f5ZU5kglVjgLeP83RIjX3MT5EQxuKwi6f7hS5952FJYud8fJd5/Dc7OexReKudi8ZiRsCtZnyiTrZC+WH45jf9yE96h+cC62rqNyMbV8s4zve0o0wnKE3ZGrWPSjxa5Ee/EsCZIiGYG3EPZajXBTjCeZ3p3RRniPUyQLFUETZ7g7FJEBSxjKngUzqsFi5i0xD/FqVnsXMtU/tA1g33cCRnfQZOdWrJQiGdfCMlHfXGhCiPh/6SG78da8VfCzfQLvvdS3QCW8EZw9nJAXfBnX6HNcZjITEhkFrp27CotZT2GUeA9NLK1hXScZ4eEthdZG74J6y6vpcxeh3xxAnZcXi/AC8mpEOaSIop95kZcRkuckPcNldruWZ5CRq+WXWcrl5YlVsXBTsWpHqkpkZ3FDZVW/aLn2dkq+H5+ZDfdm5TXILFqHLvbiC9xA9m5dzhdaF41W6zqEV6KwUMSb5CDpy8notk4sh5q5YtCCL/DZggGF7nqVk4nPsFNMJpb37AqN2mbytUr6sCZo1JekMUpVNsluBi3wyIJJaC9XkJeqlAB8TBKAHASSBMCDJADZCL8SBROzCGx86wBeXP8uxoa9gs+Ex5nmA6dilFjZKZyMPGnMkxEZ8PL83kWsWGWzF5KxhgLfK5HxMPdyhrVYhIiKjAG8HkXL2HMIt3SEA7ndvRcvCFBzMdgXU0UsaMpXxG9Z7BeLLDE5MaTB/T8FMSG6O/E7LT8F9fquwr8xq+Rdjb+SDnqMfPpN/Hn1TXlH5ZfizzyGt/eJP5Wj0maHnYicV+ygSXN0mbMOh8Sf2tS4BxbvC8Ri1ZNNu+HpTw6KP9WD8rYXJoqV5K/+twvHF/pgoLlwIf3MDzj5jHxe9TevgKz3VSHrfYuSdTEXz/LbhV1pvbFsrLtakq5ao7Fu58WIRSehwtNKrMgrLovFLgtXzLKuB0WU2IYzHnXIR+yOBFg428NSqP5KNhUqK/iquMnvZqz4/hry+08LmdeEVOiFHi1Vu8fbxRG4dQ0hcXmom/gZxnf+SJxtjNZDnsE3X85D38LguQ3g7OuLNu8dwLHgu+jRpax5nQVshHo5Gj8iSWMkmVjhPOFJTG0vl5c1ff5P0vTJDSRNH3c1mj738cD3aTzXVdbQEN0UNnqSFPE9kiKGq0gRo8S2UopIC6Ahwtvazc6TMMi5JOkuDkVt3zcCiUwZt/BmjFAdcFCu0ihSERkGjau3PQomGWE3y+9ZoozWK3Q6VLRvY1oX8sBaoUpqVaEcxEfGCuPfx/H15QK9+6tH8M3iQXBQdddropxM3PpFTCbK4660/kC8L/T4L307UUhjlIApJ03n8M3EgujcdJieIbUSADLst8DCA5cQIfT6F/ZsCYdZPyH84s9YKly0NhAfzqxjysnIdJ6MlPOJTEdCdL54R8mhA3mcyUDr1jaCNMqLEC1xR6ywZkhSGiGQESo6NGFRt8JKDcqLAX+H3yxn+/rJtlvo8c9pW6BWpJ8muFaDIlAPtmOewwtufvjfl+eFf6PSUlGyHq9C1skzI0hjIPc8vlrtB7dlL9aQIH6lXa++zuXhZrywfxV4OQrpLbnnT3JuDXuS3pIRuERYSCPjnhhP7MUYovR8KeFbMN4X79lYsXgYbODvv7yQOdyLx4vi90d1Pz9OkNj7rTDx2/MF0v0QHPn2BQwspjZo4jkWTw3OwK5tp8VXpKykdOgTeXkDJsheNNXME4QeeZmaPor4SERYTsLyBcVsapLLkiKKRbms09j+SwYGzHhULHaU1efaf54lMrZTsTl8asGdboeFv53QeNdpxXZ2G2vsjUzDEJcHMDWAC0RSazt/8y5e7qKFdwuNV1RbTqQjKjxVqASSilFp11Qwmdg5R5pMPLKsRwkd+9JKazpHq35qJQB5obgSnAvH+hrWC3LkycgWnoxoArfEcSdM2eqPKQXHh33ij2GF2ycKtjfhyrSCg56LcEgsTmhKtBhAdjKfnUnC+I6GeaeORNxEUFo2Vg5w0tRNPl4bEGjQHnN3nMHcMq+lgKz3UCHrPqpkXdgBCgPmpUfOlFmTcWcQ4/20TQiRx4Lh6xAyvAARsX25YNtz68nC8cRz0V5cLgW02T62OLBXBEG9dddgUplTiRlob2kKL5uiFiGldNsIT+UjPeoaUkwcxSK1LCXRAIOw3xu9dA5+mfAJvpraA0t91EvvNZRWf7hMTZ9MnP9JOKnp+gI6ygFxC2oqW4qYg4DPPsFh92exf4LKgqr6nhjF0VKnfUaBgJYXubBXK/wgVk8vXM9EH0cVcaCW9VQ0O7VLaUonw0y6KtpvvZbLixMey+6i+RhPlWBVGlos92RCQ/kSh8WqnyQBGC6RqIcqC0LcG38VlzJSgEQhwXNR86yYikGTJyMlEK3qA093tpXUy87HZRhEyrnhTCLsRSybIZ68wlrV9756tlcesl49e17be0XvKGlDnBZkwhDqZWRLR2pl6we2ru1QV/L6lI4w7rcYAC9S4S41CbVTr3nYdrm4fmmphUo/WaDpM5LssRRCvVkspnmOeGinqUgR3vO2/4fub3YSjqBVkyxF7KEiRexSTIpoAc9lB3FJtZiRb5d1h40cnpKXTyu4JF4+JgayjjZNYCGkNFWVSDeW2h3nbGmQCVdVXafW7dTrhTfOheENrQvqooBy1U+tBMC+B0YNO4+E25lCicyK9dh1Abce6niqhz3WnE7Esj+icHReFz20oLlKksbsjs6QJiaGtNHR3EM+wwgwAjIC9I6+8YiDtPBhCKnM4aibsBVEisYsTqUhYI4eK44gckVpefR4rlRNn2xE7NqBII8JeKef8LZZJJVPilikCO8UjfXDeJQPgTfFakiGUPH6UwwqVZn2h/8ntfv+o25V2awRtVUfzvOE4a+GWBFaA2HaCXO/+QZvPerEJEZr8KquAE1O3hPvtN/12/j0RFyVNUwOBmYJNRVSbeOJSZXBzg0xApVCgN5Vcn28Q3yPq9KD6an4dEkas2aQs0Edk1QKvBpZ2BNzDwSIeFCeOuq9GTwX7cTZff+H4Wq84+moEaOqRoPyvlFhoPXFklTmnd6tJFuVf5PK5X1c6zaKF6BBLESIlUmkzLqxxdHhfUagcgg82d0eE10sC1XMKldb+Uo/tfMKkoQb1Y2PefLEpHyQcS5GwOAI0MLH5gleUgiEnaFCdbgKEqmUHYhNk7QxaKzixAgwAg8RYCLzEAuttlYMdUV/4Y55p5DKXE7Vb0A9ql8exF7oxwbBWt0ozswIlBOBTZPbSbYq47ZfgRygspxFtc72ysHwQpUy9j6oNXxcgBEwKAL0ztKiIi0u/hrxn177QgE4twjCZCdUyrZMaafXtrhyRqAmIsBEphJ37eCT3ugrPIdsESJmfUlmqF6qn0gTD2KVuFlclBEoAwFaaT0621vKNeiHSyDjf10nUicjEvNRQIrkeZAXJnSNMNfHCFQNAvTuLulsg+MptyUyow81M5LEbAy+joZ1TeD/VCeW3FbNreVWahgCTGQqccNo4nP4Ke9CycwusWqiq8GM6qH6SOJDJIZIE7XHiRFgBPSHAKltymSmhyAzurSZISnPY1uCC0nMWuFljxMjwAjUXATWjfWSFiSIzGwWhIOkJ7pKpE7+mQqJYZVyXSHL9dQ2BJjIVPKOErnwf8an0GZm7YX4SquakSoZ1UPxYsgWh+pnElPJG8XFGYFyIkAThquLuxfazAzaGFAp6QxJYYgQtfnqIsJEvJg94z3BJKacN4OzMQLVHAF6l+mdzsrLx9qARBABqcyCJklhvhH1yOrk4Ut6sF1sNX8GuHuGRYCX+HWEP9nMPCoi7T69N0xSBWsZl4butubldtFMrpWDBYE5n5KF68IAuIMIePX9eC92s6yj+8PVMALaIEALB7tmemPz+SS87hcLks4MbNkEz/eyl+K9lGdhgSQwG88mYlvoTcmon5wJfCpWcO3Fu82JEWAEag8CFEy3p5MVFu0Pw76YNClMQifrRuhhb4kWjUVMsTISER9y50zBLilODLlY/mGEG9iwvwzg+DQjIBBgIqPDx4AMAIMX98De4BR88o9yRYVWVVqKYHcOYjBr2UQ5gbESk6R0QVwoXb+dgwQxcBF5oeRr2xhfjHA1WJRxqRP8HyPACEgI0ERigrcNNp1LwveBKZgg3CVTIlLjI1Q+nazMpH1HK1PEp+dI28dj0nH6+h2JvNCBOW2tMb9nK16UkNDh/xiB2okALVDsneUtSW+/FEFuKXA2qZxZ1KsDJ/H9d7USwRFFUv3+p2ffR+LtXIm80Ln2og5yIkAunsuzWEJlODECxo4AExk9PAG0OkN/tCL7R9hN+EXTxEZIW4SqWPFEKy+9xaRoXNvmGCqiBvNqbXGEeJ8RMCwCNKEgw176IwcAv4t3Oij5tmTroq5nFBdmhJC+jGpjLa3S8jutDiU+xgjUTgRoQXOT+FudkYOzcen4VRCafxKVnkfVXTEF2H7Su4Wk0cEeDNUhxMcYgdIRYCJTOj6VOku69vRX3DNRkhjgasfkJhOnVozGkz/GA3X6YuWx7zHTsb7ATD5+D49+dgifj7GtFI5cmBGoLgjQRKP4ZOONVWuQBTN8umJxdekm94MRYAQMjAB94+VFTdWu0Pff3KwuS1xUQeFtRqASCLCxfyXAq1yB1OUAAEAASURBVGjR2kFi6OpvICrslhKGB0E47BcHhbQnH7eDh4uF8jz/zwjUUgRMkYfm0G8sqVoKHV8WI2B0CND3n9XGjO628wXrEQEmMnoEt9ZXnZeIyDChLmdqBjOTLPz76ykkEpORjzdoDTcnpQ1BrceCL5ARYAQYAUaAEWAEGAFGoEoRYCJTpXDXssbir+JShgJ1fIZgSKv6eHDeD6dShdOC5GiEZQpG49YWnuYmteyi+XIYAUaAEWAEGAFGgBFgBKoDAkxkqsNdqKF9uB8diQiYwNy9H/p7WwIPAvH3yVTkxUQgQvAYUy93ODCPqaF3l7vNCDACjAAjwAgwAoxA9UaAiYwB7s+PW38yQKu6bjIH0aHhyEYjeHj4wHdwF9RHBi6c+BcRUVHC3N8ULh6OUDqc1HXbXB8jwAgwAowAI1DzEDh46FdkZGTUvI5zjxmBaooAE5kqvjERERGIjo5BXJzw9FWjUxZiIpLEFTSDl6sNmvXoi851FMi6cAZ+UcnC6N8Snu42Ql7DiRFgBBgBRoARYARycnIQEBCIS8EhDAYjwAjoCAEmMjoCsrzVBAZdkrIGXVL+lrdctcunSBWG/mJVycQR7s6NYOLQByO7mwOJ53E8JE10tzXaeQp1M06MACPACDACjAAjgEuXgiUUTp8+w2gwAoyAjhBgIqMjIMtTDYmTQ0OvSllpVaZGi5fvxSMySkQyt3CFq50IR2TihIGjOqGOIgIXLggiY+YCNweKKcOJEWAEGAFGgBFgBM6cOSuBkJ2djWCWyvADwQjoBAEmMjqBsXyVFBcnF98vXy3VI5ci6gpCBI8x8fJAaymsan20GjgUXQueKBPv9vBgHlM9bhb3ghFgBBgBRsCgCJA6eVp6emEfAoOCCrd5gxFgBCqOABOZimOndcni4uRAIZWpmUnYwkRfQ4KwgLHwcoFdwUWYOHRFvzYUN6bo8Zp5jdxrRoARYAQYAUZANwicPXeuSEVkK1ujtTKKXA3vMAKGQ0BaSzdc88bTMomRSZysmmh1hoz/PTw8VA/XgG1BVMZ8jitjinXVpD0WHg7FwmKHeZcRYAQYAUaAETBWBFTVylUxOHf+AoYOGax6iLcZAUZASwRYIqMlYBXNXlyM3NTKSqpKNv6vaL1cjhFgBKoeAVITIQ9E6lJp59Tl52OMACNQuxGQ1cjNzEhj4WEiW1lN48jDXLzFCDACpSHARKY0dHR0jlZjrl9PxsCBAwprfOaZudI+i5cLIeENRqDGIEDv9PpPP8d5saIqJzpGMaL27z8AU1NT+TD/MgKMgJEjQGrkXbp0xnzx3ZfT+HGPoaEgNuHhEfIh/mUEGIEKIMCqZRUATdsiGRmZ0gBmaWkJPz9/qThNdPr17QPvjh2Enmwm6BwnRoARqBkIdBTv7W+//yH9yT0mYkNpxKPD5UP8ywgwAkaOAC1wPPbYWDg5ORZBgsYQT08PEVMurshx3mEEGAHtEGCJjHZ4VSg3DWCaiAodLz7AVagRLsQIMAJVigCtsKpL3t4d1R3mY4wAI2CECJT2jacFzZpnI2uEN5EvuVojUKUSGXdnl2oNRlV0btYcpWiZsagKtLkNRkB/CPTo3g3FPRESuWG1Mv1hzjXXDAS0+b5pk7dmXH3pveQ5QOn48FlGQFsEqozIRMZEa9u3Wpn/nVWrpetiPGrl7eWLMiIEaKXVxcUZZOcmp07e3vIm/zICRomANt82IjHa5K8NgPIcoDbcRb6G6oQAq5ZVp7vBfWEEGIEahUCvnj0K+9uypR2riRaiwRuMACPACDACjID+EWAio3+MuQVGgBGopQiQfrvsSr1Xz5619Cr5shgBRoARYAQYgeqJABOZ6nlfuFeMACNQQxDoLOxiKD4EeSDixAgwAowAI8AIMAJVh0CV2chU3SVxS4wAI8AIVB0C5EI9PT2djfyrDnJuiRFgBBgBRoARkBCoMiJjbJ5JND1f7LGkJDLGZuxZEgE+UpMRIKP/MaNH1eRL4L4zAowAI8AIMAI1EoEqIzKEDk9YAfZYUvQ9YYJbFA/eYwQYAUaAEWAEGAFGgBEoHwJsI1M+nDgXI8AIMAKMACPACDACjAAjwAhUIwSYyFSjm8FdYQQYAUaAEWAEGAFGgBFgBBiB8iFQpapl5esS52IEGAFGoGYgEJZ6B5nZeYWd7e5kWbjNG4wAI8AIyAhk5eThasodJMJKOpSUkQN7S1P5NP8yAoxABRFgIlNB4LgYI8AIGB8CRyJu4rerN3E6MQv/pN5VC4CtaV30tGuCCe2aY6inNU9W1KLEBxmB2o0ALXL8EXYTx2PSsTs6Q+VivaXtb9afk34HtmwCH7vGGNHGGoM9rFXy8SYjwAiUBwEmMuVBifMwAoyA0SJAK6ffnUvE5xeTkZqTL+HQwdIMY1s3hVndOrBt3EA6lp3/ACl3cpGefR/nxcrrgVgxefntmshnidk+thjf0dZoMeQLZwSMBYG9wSn47EwS/K7fli65U1MzvNzFFk5WZmgvCIuFqXLadUWMERlCmktE56OAFOnP3qwenhV55/RoxQsgxvLA8HVWGgEmMpWGkCtgBBiB2orApyfisPpUAlJz80Hk5TG35nBv1kjj5aqeyxSqJMGpt+GfmCGRmrEXU/DBCDd42TTWWJ5PMAKMQM1EgCQwC/aHSwSGCMn6ga0xydtWIyGR1VBf6OckXTBJezecScT/nU7EV4LYLOvdCvK5mokI95oRqBoEmMhUDc7cCiPACNQgBGhS8szeMBwXq6ZEYKZ42cBB/GqTaOW1j6MVurW0wIXrmTgmCE2bry5KExyeoGiDJOdlBKo3ArTgsdgvFjKBeaqHPcwLJC/l7TmpldHf+bgMrDkWK9W3T6ixbp3cTiMZKm/dnI8RqM0IMJGpzXeXr40RYAS0RoBIjO+mIOTkKzDZ1Rpd7S20rkO1gGm9OhKh6WjTBPvD/5MmKNFp97BurJdqNt5mBBiBGojAKwfDJbWwiS6W+FS805U14CdJza6Z3th8PgmzhWpq968v4uhsb5bk1sBng7tcNQiw++WqwZlbYQQYgRqAgERivg9CtiAx8zq2rDSJUb1kktDMFHX62jbBJ4GpePFAmOpp3mYEGIEahoBMYsgGhshHZUmM6uU/2d0eV5/1kQ4N+uESaGzixAgwAiURYCJTEhM+wggwAkaIABn19xeSmOwHCjwjCEeLAiN+XUMxyqNFIZlZ9VeUrqvn+hgBRqAKEFAlMWvHeOqlRbKnI2kMJSIzNEZxYgQYgaIIMJEpigfvMQKMgJEiMG37ZaQIr2T6JDEytERmuls3kgx7yciXEyPACNQcBOidJU9jJInRF4mR0ZDJTJLwcDZj5xX5MP8yAoxAAQJMZPhRYAQYAaNHgIx1ybCfbGL0JYkpDvIYQWZaCu9G0/eEgYLlcWIEGIHqjwC9q7P2hoPcKq8c5lolHSYy84PweEgunWms4sQIMAIPEWAi8xAL3mIEGAEjRIAmJuRimbyTVdawXxv4yAnAJEFmSAq06VySNkU5LyPACBgIAXpXSTqy8TFPrT2TVabLZDNDDgXWCPfMvPBRGSS5bG1DgIlMbbujfD2MACOgFQI0MaE4MQOdmmpVTheZyaUzESgiUjw50QWiXAcjoD8E6B0lIkGEQo4Do7/WSta8rH9riUTxwkdJbHRxJDIiEt9u3IjAgABdVFfpOm7fvo0d23dg7tNz8PbKt0D7nEoiwESmJCY6PUK6tCQKnvTjJQzaGICVCl/pz+SdE9I+HafzrCevU9i5Mkag3Ai8949SGqNtnJhyN1BGRiJQRKT2XEotIyefVotAbhIC/QORlKsoeTp6I8Y7T8a30fdLntP5EQVykwJxLCAJuTqvmyusDgjQO0rSGCIUhkhEnmSpjCHar+ltnjh+AsnJyWovg849OnQo3l/9HsLCwtXmobJVSXICLgbgamgonpw9GyEhwfjow7UgsqXpGtR22ggOchwZPdxkcpO48WwitoXelAY9amJgyyZoZlZXCoYnN3k8Jh23svOluBJ0jIJpTWtrjZd8W+vUjaPcHv8yAoxAUQRoAYFUu4a3blb0RBXuEYEiW5nvLyaD1Ec4aYPATZxc9SSev/4sfu/fWZuCeshrgvr5V/DDrKU4+uV2vN3PWg9tcJWGRGBzYIpkG2MIaYx83dM722J3dLgUONOQ/ZD7U1N+afL/1KxZWP7G65g7b16Jbn+6/hN8+sUXsLdvic5dupQ4TweeX7QIjzzSp/D84V8PY8/u3VLeXr17qa1XXUUvv/gi4uLi8EtBWXV56Fg/337SH22HhV3FmdNn4O/vh683bIDf8eNo0qQJnTL6xBIZHT4C5Bpx7i9XpOjd5NGESMnf09ohc1lvHJ3XRfIzTxG95T/yO0/H6fye8Z4YIcTVVK7V+nMg147salGHN4erqmEIZOLcqqFwb/88Dt3KF32/i6gtc+DtOharz9yAmrX3Cl3fPzEZUjn3Zo0qVF5XhTpaN5acDeiqPmOpRxG1B+u2m2Pe0lGwNTH8VZs4TsBrz5pj58d7EKWrh9Twl1Uze6C4gbPrpqO76xCsPKH0DJh3cgW69VmJk1na3xxSKyNj+4ltDEtQh3gq2z8dqxy7aubNqfpeJ1+/LjX6x++/l2icpBwdOnTEyFEjC0lK8UxEWmKiozFv/jPSKVL5ekEQG0tLCzg6OkqSnHUffVy8mNr94EuX4OTkpPacpoNEYqidqdOmSVm2b9umKavRHWcio6NbTlF4KQLvd0IKQy4ZExf3kNwyDvawLtMg0FwEyhvf0RbfPt5OKkflidBQfXuDU3TUQ66GEahJCFig+/TJ6HTvGH46FI3skE1Y+n4A2r/2Pyzt1Ry6mrNeSLoNNxEvhgzvDZlaC6kMpfNxPDkpvA+KIKwf3A6+r67HF3MHo4OzC9xd+uP5XZEFqlt3EfTLLgT7jMNYTyV+hWUNtmEGj7Hj0DloF3YH3jVYL7hhBbJObsTXt9qjr208Dh4Mwj0BSr1WTnC8HofEu7Q4ol26KrwaUnrE2VK7gjrOTfMF0vAgjQ5O5UeA1MW6dPVBwL8XS6hmkZRj0ODBpVa26fvvMHrM2EIpyNoP1mDAoEH4aN06rHz7LTw2fhy++OyzMu1YyM4l6loU2rZrV2p7qieJIMXFxuDlpa9I7T8xfQZ2bt+umsWotw379a4l0JP0ZPZv1+Al3DFSJF7yK1/RCL9UjspTPVTfBOHmkernxAgYGwImLo9i+iAz/PvLR1i+dCNShq/C+rnt0UCHQJxNvi1UPg2vYWspJieUrhRMlnR4iTW3qnvJiE24h6RfdiOoy0r8Hvw3PhiZj99eXY29KcJdtSICx/5MhHOvTmhVbmZ7FyHrxsJj8DpclhblM3BuzVh0mbMHuormY+LQCb1cEvGXf4TOJIc19yYaqucmaOI9Dx+sWIRJQ2yRefUaUsTdyE6MR0qnR9DdRvt3Xn4329oYXp3H1coUkekcHFObp4tsTV5YvEQqcsz/WJGiJKXp4qNenUzOSASoe48e0i7ZyaTdSsOEiRPl0xg3foK0HRkRUXhM3YZ8vlu3boWnSe2NnAzIf0RcaJsS/f7801Z8+dXXhSRq4KCBEhkiSRIngIlMJZ8C1ei+pCZG/t51kaie/bM6StIdks4wmdEFqlxHjULAxAFDnxiMpsG/4zBm4NN3R8Km3BPW8l0p2ce0bGJavsx6zCXHrskQhsSclAgoEiIRnlMH1uNew/sLfeFg7oYxE/vA7MFVBFwW3nskotMQnu52KhI6sRJ/YiV8XTpj0sYrKLnunoyA0zGweKQbvOhZUsTg9J9xcO3VHjqzkjKxg5tXQyRExCGLb6bBEDCxbI7mDRqhlZMdcOsW0vNv4PjuGIxaPgmuFRhH5HezoouUugTC264JgtKydVlljamLJu9EJFQ9eNF2WUb4ZCxPNicklflu4zeF10tlLS2tCklC4QmVDblusp+hJDsDkPfpmLm5kuBeuHCBdjUm+by7h4eUh1TW+vbqjazMLEnKQipkCQnxkgoZERpyPuDbv79kGyOTG9mG5/ZtHmEIRCYyGh+3sk+okhh9RPclETLVK6uaMZkp+55wjlqEgNBxD/K/iFt0SWaWsGpUgdlHLYKjZl/KXUTvWoK+LqQe5oORC9Zgh18Y0hVZCFwzGl1XnEBRCqfAvehIRMMdk2b1RzPp1itw/36uWFe3gHVTIZdLiUN0Tj00aVyUiNZp3AwtmtrDw8mq5AfubgQCgurCp7MbpDX51FBcjLaGj7e9ChmqLNKmaNykHnITkpXPbmWr4/KVQKA+Wrm5wOzGTSRf2IotpjOxoEdT4L4flrfzxdQZ4zGif0/4Lv4M3740SWz7wHvCNwgvyYAr0QcuqisEaCJPnsUmCenHQF9f0ESfiM3KFSswb84cjc2QxINsYChNenxyEWkGeQYjQ305UV5Nkg6ZQGRlZcrZtf5NTEiEq5urRJyoHbKzWf3++3jx5Zew5KWXJZsbUlcjQ36vNm0k5wSa1NBkUqR1J2pZASYyFbyhZBNDkhIiGfogMardUiUzbDOjigxv114EcpFw8D0s32aGmfMHo3HATmw7V/DxKHMSkg6/V/vhkUnTMW3EEPRpNxjLj7CtmUGflbxL+PmDAPT86ij8ty/DQJPT+HTBCHRz8cakzY0wa3xHJbEo7GQ2oq9EIse0HToJ6YYyZSDgZAByzNujk5t8rLBAwYYJGvssxu6Lh/G/4SXJSX5YIC7mOKNLRzKYzkLAD1vxT7226NTW8OpCxa+E93WIwIMAbPyxPl5aMURJioW0L+yuAq1mbsDhjbNgsX8nQod/LrbnwOni3zgeVxXuunV4fUZSFUkrSKJy8sxpkJ0IqVwRsdm/d5+0rwkGUiWT1cJGjR4lZftp61bp98L581BV8zp08CDkc5rqs7dvpemUkMxYaDxHJ0gy5NTaWcpD7TRt1hRTpk6R9knCQ9ciJ3I+QB7WVP/kc/RbVluqeWvzNhOZCtxd8ib2ul+sZHCnbxIjd2/lMFepved+i2JvZjIo/FtLERDxOMI2Y+lyf9gueRvLnpuG4c3jcGD3eaWqTpmTkGQkCG9ktxuNwoeHt2PlsNs49McVaJqaZOc9MDiOOdWgD3oFoa4DBrywDE/3dYZDzylY+uU+nLoahciYaERe2YnFPlbFms9EdISI9+DqDueGSkmcIuUINu9Jhv24sehtIY45uMPLLBs308prVJ+HG1evIsnGB91c6yL9xCdYsVnYsbi1hae5qE9xFT/Om4DxY8diZK92cO/2Gvwq4N2KPOyl3cyGWRt3aJ7uFLtc3tUvAnlN4Dv/Sfg0Vj5LeYlxiHObgKeHCbWz3Fzk2gzDlMEF26at4GSr2YamOgSuldXc9Ata9at9+Wuv4TPhItnOzk6SYJy/eBG79u6R/kiioSmdO3tGqGf5SqdJ0kGG+T9u3iwZ/f/zz6kinsqILLVyUP/mFlcxS0pSekKjiuVtLy9PTd2QjpOtjSwBio+PR6fOD21zyithkdXqymqr1I7UopNMZCpwMz8+HivFh9nwWOkPbAWq1liE1MzWDHeV2qX2OTECtRUBRZo/Vi/4GJe7vogP53WCqXlvzJjuhVt7f8bh5DyUOQmxTkNcTAuMf2YkHEzyxTylLpxb2xZb8VeiN9rJAkm3DW80+9+dXKlDvVsb1iOS3p4pYe/UZ8ZItC+YSJbZjiIZ18IyUd9cgRyxcJQeshtvzVsFP9sn8N5LfWFOFdSzh3ubfIRciSumlqap9nQEnb2CB+Z1kea3Fou2NMDgXo3RwDwSW1cfQDLaYObGPdjzw/PoVM8Rj69ZggFEcLRNeXEIDc6Hl4e92mdO2+o4f2UQyEH8tXhYTH8J8ztKT42oLA/JUVHI6dgOLibCpir6GpI8PdC6nlBnFAQnUYU8q7bc3k5p/yp7L1M9V9XbQcJJCQXGNLbk7uEukRjV6yZ1L1nlS/W4vE2qYpRUY67MFPFkKH24Zo1kHyPtFPwXFBggSWjeXvkWhglPZlRerl8mK7RP6mGffPxRoa0OeTUj6QqdozJzn54Dsn9RTTIR8vJqo3q4cJs8kc188snCfdqgQJ0ycZHrkx0G2LVU2uwUKWCEO0xktLzpJI2RVcp0Zdhf3i5Q8CvZXoZjzJQXNc35aLCRBxbNufR3hvRjSedXHpz011LNqtmk6UC8fTQUl36cBdcGNJFshA4vHkBExHeYIhZNy5yE3I1FeIabUBcSExfFTcRF1xUG4TZqbSC8rBsiroBEGBKllII+tLI0M2Q3qk/bt64hJC4PdS99hvGd26DbaBH7w+ZpfLNlKfo2LVgtN2kN36HuuPHHMYSUx6ZBkYjQkHswS9iCd7aYY/EH49H89gM0NmmJAbOHwo4eNUU09i57FxcGLceyQbZqn5myQMoPPoa/brTDiMHOFSpfVv18XgsEci5i2w9R8OnhiYdv1l3ECmmffWs7NEQ24iPjYe7lDGvh1DshMgbwchcLICXbkL2Vyd7LSuaouiO7ozPgbPXwiqqu5ZrTEhERIhMUxFL2KCb3nsgGuU4mNS5ZOkLniDCQN7Ift2yRVMD27N9fSJxIinPk77/kKrBC1E9ulCc89phEeEjS8vEn66XzEeER8D96VKh+yeRZWUx2EuAhiDMlapvyEVmh/lpaWUkulpW5AYpVQ4E6N36tdE6wcsWb0im/o34SkSLJFCc29tf6GZClIS/5tta6rC4KyO1+dy5RF9XV6jrklRh1F0lGguQphIwGS8unrqwujhF5WfjsfJDhHw1OsjcSXdRdu+soexLSMjYC4ZaOcLCsKzxbxSMyqrkwMC/6QZEx6iNiQmQKtS5ZIiIfr+rf6Ix7aGthWmG37VXdX323lx8XgYj7rTDx2/NK9bOYEBz59gUMdFC1jRExW4Qd1MC0w9h+7EbZXSLDftP52CPUy079uAg9mnpi5s5AnN/xKgZJ9Yqgqz++i3cTxmDNsgGwUjOZLbsR4Rlr22HcGvQ4xrgUdUJQdlnOoVsE8pByaAt2XG+Lfj3IJkpO6UiIzi/wdncHiSKwZOvWNkJ6loWYiBtw8XAUBKdkIm9lnURIhBMGjt8ix5qisYtT6QgQSaDAk+StrHh6973VkorZgAEDC0/Jkg4iOP97f00RKc7gIUpbHHm+QHWSWtvkqVOlv9//+quwHbK7IYlN8XZJFWz5G68XkiOyfSFD/7Cwq5INzyah7qYqOSLbmTfefBOXL1+WFjznL1ggkS2yDZoz75nCfhv7hmZFUGNHRsP1bxMBL+e0tTbYhIMGUxIpfyUcDawY6qqhl3yYVjLeWL5cmgQVR4MkITQQLHr+edi3aiUNKrRyQxF6yVsIJRqsyOiP0ugxYwoHHulAKf8RQaJUmr4unScjPvqjRPq4pJdL4uaXlizGwcOHy92eVIFR/VcwCelBLncLJiE+qpOQlrgj1EYyPIcLVRGxwB4lXPjCGY86NFCLUk/h2YrSuaQMjPJooTaPvg9miojh52/exTu9W+m7qRpSfz7So0TcDxNHuDs3KrXPJrYj8MqSfZi0+ntM6bMUXUw1s4+8iMsIqesESchXolayy/oJb3x6F3N/mF9oSwEhvZk6fCMyXRshJz4Tbit24muf3zFh6n6YtryH+Lim6DukMS4HhiM2bww2vFsP//vVGUsPjYat5q6UaJ0P6AEBRRh2fx8CjxmvoU+RuDFOmLLVH0rzamDYJ/4YVtD8sE9OFG6r69EQQR5II+MdoZlhKDfMO4JSpK4N8VQlZ+p6a9zHKEilHEBSHRIkzZC/9/J5slEhSY2joyM2fPlFkfP0vd70vY+kjiaXI8kO/RVPvx3+VSI3xY+ryy8b+hfPK+/L6mN7du/GJ5+ux/Zt29C0aVPITgvkfMb8a0SqZZUPhEYrIUkizsOoNoYdQKZ3tpX6EZaqjDRszA+wpmsn4z5KJLItng4eOICN330nkQ0aRCgPrdwsXbZMykr7JK0hfVX6o2119RSvl/aJIGVmaueaMfTKFWngpNUbMvwjvV1OmhBQTkI+H2MrMjSXJiHbZxGhp+0TOLTIG3bTNuHK1qmgHCaei3AobB2GaXDdTJOR2eJ9DhJEwlAG98GpIiaKSJM7UY85kbH8tSvXcL9FG3jZlbXW1gie837EpSOvlkpihL9dJISGIeN6PBKzpUiYRYEWk94ty9fjQt51/Pn6DGHwvwDfhtwV9lixiG3YC0s278N3ixzxz9lIyY4irk5XPP/TL3h3SBoiW7+CPb++h1FJgbja8kX8eXkzZrI0pii+htgzaY+Fv57A7nfIVk43HZjXU7nYsOuSkkzoptby10KOBuTFVLKb5VQ6AqrSjdJzKs/St5jUveYveFZSOyuuek4SE9m+prT6Pli7VooDU1qe8p4jwkXzEwq+SddDEqQtP/1URHJT3rpqaz4jIjKVD4R2WoigKcmruIZ6KOT2zxT0x1D9qM7tZmRkSoZ3R48cKdHN4l5K9gnxMBnYyfqmJBUhF4+kH0t/JCJeJVZ3ykqyfm2btm3Lylp4nlTMjh87Jg2cdPDJ2bOlAVQWXxdm5A29IbCwVytkCPWyC9e1I6C66BCRp2OJGRgnVnqr2uZOF/3XTx3m6LHiCCLPrUAPnc3V6qFl7+EY0rYBbt+4X7LbJm0wd28IIgL9se/Afuw9sAFzOzTAzagY3B80Av2a5SE1+Q48PGxwKyoOFsJzWq/Gt5Ga1EJ4Q3JHg1spuF7XBW4O9UvWzUdqDQL0jpJGxJrTiTCE97JN55KkRcz5BYSq1gBbTS6E1MdkDYxPhXe04omIhDoJTPF8lEdbElW8DnmfyBTZ58gaHOocHsh5jfXXeIhMWYHQSIXA6zkcylSzWlfwdMSlZ8PerJ7BRMryQyqLtKk/nDQjMHrMWKEedqBIBiIIpDMrJyIfpA8r+5inQYOM/Z4SqmY0ENEf6aKSUZ+mIFlyXbJ+bXGXiFSn/EeSHdm4n34pGBYZCMokStapJb/3nKoGAXKiQUTiQGxaldvKHIz4TyJRrw8wjM1d1SBswFZc5mFvzE7MdWkA0w5z8NWWNzFcg5phyV7eQ2xkKtw7OAubiTREh+XCy81cGIrfgrt7S9TNS0JktC3cnMxAamuX27eHB/OYkjDWsiPL+reWyMSLB8Kr9MpIA2OxCPtARIrGLE66R4DIgvwtpu3ykBbd96JojZ9/9jmIYHHSjIDREJmyAqHlxQjjUgc3uJTibjNGEIfeLZUuGDVDWjVnaDAjF4ycSiJApKG9mFQMGjxYIiWqamFEEFQHBZl8eHp6ShXJftzlfTooE5Pbt7NKNqZyRC7r7uEhHSXiQ+4bV7/7ruRUgCIPk7SH6pZJDEmCzM2bFPGeRjq6SYmJKjXzpr4R+OIxL9iY1sXe8P+qTMXsslApk21jeGKi7ztckfqJvDyAl2tz4bFXkJaIlmjvmYXQoDrwdBW2VTdjEC5cQDs0zhee9GLEQOEC9iFUEZxrVhl6V8me7TthL1tVAapJ+rNgf7i0kPrpWK+aBRj3tsII0BwiLjYGPkJDhJNmBIyEyJQRCK1Afzq7Y1u0uvwFJnabjA/P3oBm2YxmQPmM7hAgd4Tuzi7o7uMjefUiaQpJUIgclObli1wcduveXfIYQn7dSXVMTmQ7o25QIHGtaiq+T+dkoqKaT3Wb9GtJDY2kONTXaVMmSwZ/vwgjPXIsQB5HKIAX1R0mPCcRYaGAWLTiQn+qibyUcKo6BEjK+dVIN1wTbpD/jr6p94bJS9r+qJvoK1RVlvg+lBDqvWFuQAsEyB7rV7zdV0TqrtcLb5zdgpkO7TFXqJ4t7SKcENhOxeZjy9C5bj04zPoRF1b1g8404bToJWetegTonR3YsgkoQHVV2Kq+/WcU/K7fxucjXA2uEVL1aBtvizRX+FOox8tSIuNFovQrNxIiU0YgNEUGwi+nol2zIPzf4pPo9cWXeKVnc44BUPqzo9eztBJBkXdJYvHE9Bn4esMGyeiefLaTmpemgFLUqV2/7EQXH6UnEVIvI9UxIkCU4uLiyjUoqLNR6datm1SHpv+CL11CR29v6fTXG76Sfsm9IiWvNm0kxwHSjviPvJp9KwJoqf7J5/jXMAiM72grxWk6nnIbvwqVL30lIjEbg6+jYV0TfDvBC2y0qy+kuV5GQD8I0DsrB8Qe9MMlvZKZVw6GF8auozGKEyPACBRFwDiITFmB0JCKyLBUhP68GYEDXsALTGKKPiUG2Gsi1K3I3zq5T6RJP0kyyPiOfLbTr2xLUrxrsg2MbGg3fcYMKQu5LCRy1KFDx+JFpH2Z6NjbK73SJF+/XphPjuZbeEDDBhGstu3aSWdDQoKFEXD/wpxJSYkSASs8UMYGuYLmVPUIrB3jWUhmfhRkQ9eezEidTCYx/k91YgP/qr/F3CIjoBMEyPD/6GzlwhWRGV2rmZE62aQfLxWSGBqbODECjEBJBIxDEl4YCG0RPAvcMPYQgdBmynjcFUHzolthyFhrHL8YgkRFb7iqcddIkXTJ9WF1SBTZtzbHnSBRqizNkPGWvXbI++p+i9vAkGiWPJCRRIeSbNQvl23SxFzaJFsZMuyT1c7279tfaOhH/ttJRY3OE+H59dCvkt2MqiEg2eVQkiVFMdHReOSRPtIx+u+P33+XPI8UHhAbRKzsWtpJqmhUXq6PdGKJsHEyDAI0YXAS7zoZ1sZdiMcUzxZwb1Z6PJOyekqEiAz7ySaG1MlIEsNeyspCjc8zAtUbAZnMkP3KhL3hmHP1JtaN9ay0lPVIxE3MEvVRuIf1A1vjhX6sflq9nwTunSERMAqJjDIQWgMNgdAoaN4VhJj2wuOvzcOw+O3YfCpd7T2hyQ0NLEkiGJYhk6yTS/3hpESA7GnIqJ/Uynz7+xaB5YXFSySjfyIzMlGRMxDRIbsWv6N+0iEiUGTPQmptVOfLL74o+XAn+xZKx48dlwJtZmUpVdWkg+I/ssuh5OGpNPQnaQwFxSLiQ4b9RGzkODVSRvEf2dDQeSIxr77yinSYJEok2SlLjU2ug3/1gwBNHM6J1VbHxvWx8UoKSDoTeeuu1o1RsMtT8en4SBAi2bD/8FPeTGK0RpILMALVEwEiM/tndSx0ANBm/Xl8eiKuQvMEIjAkhRmy7QpaNKwnjUFMYqrnfedeVR8EjEAiIwdCM5ECoTmbFRe1KJAVfQ2JXj3QumlvzJjeBDN/OIKFfSaWiMzcu7XS5eHZuHQYUldVjh/Tq6A/1edxMkxPiAgQ8aA/UkeT1crk3pAaGhnWZ2Skq7WPIekHBb4kFTZK9GtuYY4zp5VBNUmVTZYGkZE+SWeKq7aZm5tLbchGeW+vWoWVK1ZgyQuLpWCXBw8fLtI2SWMoOi/lP3TwIPr07Se1ve2nnyViJUtnpIP8n0EQIO9Ep5/1AcVueO+fBInQtBTu1ztaN0ZrSzPYNG4ACzVB6RIyspEi7GCiM+5J5IU6T+6dycUyeyczyK3kRhkBvSJANjMrhrriUS9rrDkWK0lzSaI7p601+jlboZ1tY7XvPi2Khgp1039iMrBbSHOC0pQhHkgK81QP+0pLdvR60Vw5I1BNEDBRiFQVfSHvU5Ex0VXRVLE2FMgJ+R6LP7iO8e+9qkUMgWLVFOy2+uA0RgjXx98+rrSFUJ9Lv0dpxSYyPQeBz3fXb0NVULuungsiBuHh4YWEQ5uuk1RkoK8vXnl1GaZMnVJqUfKYRsSnuNpbqYXUnCQpzZG//5KiBE8aP0Gy+yFp0ZiRI/H2qncrdB1qmtHrIV3dO+qkLuvSx0WTvvrf4Tfxw8UUEW9GGRi3rHbaWphipJsVKBp4dVcj0xX+uqqnLGz5fO1AoLY+L6Q1sfFsIv4WBIXIiWrq1NSsxDE6TyEVpne2xRBP6xpIYO4icM14TNpAmglm6PiGCCo7r8CmJ+sIlg98BrtuPADqDMDq0xsxxVbzGnptfSYEMJz0hIDmp0lPDVZ9tSYFgdB00/I0scLyUUAK3hErKXJgSt3UXL5aaAWnttvHlA+JorlIRYz+KpJIgkNBKZOSksosTiRm6rRpZeYrK8P5c+ckD2oUY4ZseIjU2Nu3lMiULP0pqw4+X3UI0IorSWHpj0jN1ZQ7OK2B0DhamYoV2CZVSF4ycWrFaDz5Y7yYKPTFymPfY6ZjfQGOfPweHv3sED4fwx6Pqu6J4ZaMGQFauJCN84nUXBGeEOPF4iOlSyL+28Q21rAU0l1KpOnRRkhsarb3whsIC06Wrqfof0IjZu8P2EMkhlIDG9g0M4Jpp/Jq+f8qQoCfKC2Bfsm3tURkPj4eWzhQaVlFpbJTu5Tm9FB616pUZVy4EIHiqmKFJ4ptVFYSI1dH8WOcnJywYOEi+Pv7YcCAgRIRY5UyGaHq+0sTDlIRqz5qYjcQFXZLCdiDIBz2i8OMWW7Cfbx83AUeLuwFr/o+Udyz2owAkZrqLpGtNP6ZQThxLhP1haq0pbDzjIhIFNH5PFE/JwDbNp9HXQ9PuFwLxzVPd7jQGgsnRkCHCBiFsb8O8ZKkMC93sZXIjGx0r8v6S6vrfFxGoStGQ0iDSusbn9MegY/WrZPIC5GjikqTtG+VS9Q6BPIShft44YjA1AxmJln499dTwvOiuEr5eIPWcHNixyC17r7zBTEC1QSB/GvCYVJuAziOHoNepnKn8pByaBN+vNYUw3zbIUcIZRo42KGZfJp/GQEdIcBEpgJAklTGXoiFyeUiqZlURaJ25on2qN2Vw1yrokluQ08IkD2P/9GjeqqdqzU6BOKv4lKGAnV8hmBIq/p4cN4Pp1LFuJQcjbBMwWjc2sLTvLiTE6NDiS+YEWAE9IJArnBTfxGJsEKHTm5iMQXIiYlHiiIWf+48hbvNfTHQNUdE66sDy5YtUDlH9nq5AK60hiPARKYCN5CkIZ+PEC57r9/G239GVaAG7Yu8eCBcMhDcMr7yPuq1b51L6BIBkr7s2rtHl1VyXUaMwP3oSEQIRTJz937o7y08Kz4IxN8nU5EXE4EIwWNMvdzhwDzGiJ8QvnRGQJ8IpOFyQBQUaI12XlZSQ4rsHORGH8W+88IL22OPwi39OnLRQHjpbAa2Z9DnvTDOupnIVPC+k9GvrGL2ykFlDJEKVlVmMar/OxGIkwJgDvawLjM/Z6j+CLAtTPW/R9r0MC5OGNobJOUgOjQc2WKd08PDB76Du6A+MnDhxL+IiIoS5v6mcPFwREOD9I0bZQQYgeIIGG6sKN4THe3nRSPogrDRs+kIb1dHOLmQblk2In77DZcUHTB1clvciCVHAFbwcrPRUaNcDSPwEAEmMg+x0HqLvJKokhldq5lRfXN/uVJoF0N+6jkxAoxA9UIgODgE+/cfMFCnshATQd72msHL1QbNevRF5zoiNtaFM/CLSharpJbwdLcR8hpOjAAjUB0QoLEiIiKiOnRFJ31QRP2L06kPUL9je7jVq4cG9cVo898J/Lz/KhoOno6Jnpm4dpWCjDdHS5tCAxqdtM2VMAKEABOZSj4HqmTmsS3BIIN8XSSqp983AYWSGNmVoy7q5joYAUZAdwgEBgUhLT1duNM2gFRGkSoM/cWYY+IoYvE0golDH4zsbg4knsfxkDRxkULdw1MZyFd3V8w1MQKMQEUQoDGCxoozZ89VpHg1LJOPW8FBuCbUxhw7uInlFEvYOTQBrp/HqQhXzFw4DLb5KYiPFa6n6zSHXQt2WVYNb2KN7xITGR3cQiIZe4TtSpgIfNXjh0sgVTCK91KRROWoPNXz3z0RhG9aOylicEXq4jKMACOgXwQyMjIQHR0jNRJ06ZJ+G1NX+714REaJscbCFa52QvvcxAkDR3VCHUUELlwQRMbMBW4OPHlQBx0fYwSqGgF5jKAxg8aOmp/u4GrgVeFq2Ra9u7sIya8pGjchKxgTNBr8FGZ1EYsqNxMRkyWM9TiGTM2/3dX0CpjI6OjGkM3M1cXdC1XNWq0/J6mF7Q1OKZPUEHmhfJN+vAQqRwE3SWWN6mObGB3dIK6GEdADAufOXyisNSAgEDk5FVvAKKxEyw1FlHB7Kpo08fJAa8mKtj5aDRyKrgUju4l3e3gwj9ESVc7OCOgeARobaIyQk+rYIR+rcb+KaFz4JwWo3wad2jYW3TdDqw7d0NF7CJ5dJKQxQsssPykWsRQPk2PI1LjbW1M6zA4kdHinKFAeSWfIPTMFrtwmDPTJSJ9Sp6ZmcBcRv62E+2RvuyZSdN/07DxEimi/QUKSQ4lcK5NBPwW75DgxEiT8HyNQrRFQnZhQRy9dCkb37t2qqM/CFib6GhLE6qeFlwvsClo1ceiKfm3McP5KTpHjVdQpboYRYATUIEBjg2qisWPokMGqh2retkknLD4ShsWFPa8Lz1mfYe+swgOo22UZ/GOWPTzAW4yAjhFgIqNjQKk6IiFEaNaOgWQzczo2o5C4XEi+I5Ebmdh0s2uMpzsLsWzr6hQpXAtQErZgar+VuGAxA5v/XYU+9XKRsPtFjH/5MNIadcX8TV/hlZ7NxVSLEyNQuxAgI//sbOUihHxlZ86crUIiIwjMmM9xRYwzRZJJeyw8HIqFRQ7yDiPACBgSARobVBONHTSGdOzYQfUwbzMCjICWCDCR0RIwbbN3d6qhBKWcF3o//DJChPqrUrVFgZyQjVi84jekCV39ke9/xCSmnDhytpqHwJmzRScmdAVkyEseiTw8PGreBXGPGQFGQC8I0JhAY0PxRI5CmMgUR4X3GQHtEGAbGe3w4txFELiPxGvRwmN8HTTv6Am7NH+898JnCLoryNvrX2Lt2NYsiSmCF+/UFgRSU1Nx/XoymlopA8DRdfXu3Uu6vMAgAxj91xZg+ToYgVqIgDwmyGMEXSKNHWT0T2MJJ0aAEag4AkxkKo4dlxSB98IvxwocmsDT7QGOvPM2fo4CXGZ9jA1z2wuHjJwYgdqJQJDQdx/x6HA8//yiwgskfffFLzwnqZvVDo9EhZfGG4wAI1BBBGgsIDUyGhtUbWJo7KAxhMYSTowAI1BxBFi1rOLYcUk5hgUskH9kLZYeiUPDfm/h6zcHwIqNYvj5qMUIqE5IVC/T0tISM2dMVz3E24wAI2DECJQ2JlSdYxAjvgF86bUeASYyBrjFtEJDg1uNT3IMC/yHM0f+ky6nzm3hC5Yi+3JiBLREwN3ZRcsS1SP7rDlzpY7U1P5XDxS5F8aKgLG9NzxeGOuTztetLwSYyOgLWQ31ki/5LVu2FlFJ0ZC12h9WJEQiXAqbYYlOs8eg6e6f4B/4G34Pn4mFXmbVvv/cweqDQGRMdPXpjJY9eWfVaqlETb4G+ZLzA9Zg8PivhEtnkbxfx98H5sFZOnkDfq9OwLyd8WLPAn3+dxCbpzlJZ/g/RqCiCNSGd0bba69N44W21875GQF9IMA2MvpAtZQ6w8OV3kvI7WLNTiKGRVgohEkM6vdbji9WvoDJg20BRQh27ruM/Jp9cdx7RsAIEcjDjatXkaTmyhXxh/HNLiIxlBqhpa2FcpP/ZwQYAUaAEWAEDIgAE5kqBl922UpuF2t2ykZ8ZCxyUR+2HTzQwqQ5fCcNRXPcR8Ku/TiTLXwyc2IEGIEahMBNnD8Rggf1W8C2RX0gPBLR96n7WQj8eScu1HUSwbkbin1HuLtQFG9OjAAjwAgwAoyAYRFgIlOF+MsuW6nJmu92MRPREcniShrDw70l6gpHy2bdhmJ4C/FI/eePg//crEJkuSlGgBGoNAL5CQi9lAE4Dca43k0Lq1Ok/IkNW0LRZPgA+GTnAQ1sYGfNWsmFAPEGI8AIMAKMgMEQYCJThdCfPXe+SGvF94ucrO478qQHDujgVTDpMeuEUWNdRc8T8MeBC2IdlxMjwAjUFAQUcRdxJvE+TDt2Qjsz8WnISUBCyl0k/rEP/ndaYfjg1khPFSIaK1vYNGKHHjXlvnI/GQFGgBGozQjwsloV3V0y8g8ICCzSWmjoVQwbOgSmpqZFjteInbpdsfRkOJYW6awFeqz4C5ErihzkHUaAEaj2CAibt5AghP5/e3cCHlV193H8NwJJWMOehRCykYQ1gKyyCKXWKmhlKSpSRJFWaxF36uuDvpVia1v32ldbWxVs1VagFndEVKhsSkKAANkJISQokBAgC4nz3jsQJBLCJJmb2b7neSAzd+49y+cMZP5z7jnHHqSEfjFqk2FU2H5SFZVZen9lsr7pcZ2mxJVpcaVxPDRU3fnN4fE9SgURQAABfxBgRKaZejm1jk2vzE2yzMn/JAQQQMC9Ase0O2WXMectXEMHxqhHr1BHdezpH+mtlGr1mTlFg77KU65xNCgxTj3cW1lKRwABBBBAwCFAINNMb4SNGzfVKqlPn0TH85rJ/7Ve5AkCCCDQnAL2ffri8/3GEoSx6hPXTgEBxmR/HdBnr76j3W3G66bp0TqQlaNyBSg8rLMYkGnOzqEsBBBAAIHzCRDInE/Ghcfz8vYpqHWQ5tw4+0yuP54+zfG8vKxc5uskBBBAwG0Ch3crOdPYFCqyjxI6B6pzaHcjZMnXhvX5ip59kyaFVGl/nrm4R5DCQjsZS3uQEEAAAQQQcL8AX6w1Qx8EB3fQvFvmnlNSZGRPx8aYJSXGSkEkBBBAwE0CVbuStfWkTcGXDFWCzSZ727ZyfMvVdoJunTNEgcbuMvk55v9T7CHjpi6iWAQQQACBOgSaNZCJi4quowr+dWj23FscDcbCv/qd1iLguQJl2rMlRSUK1oRBsY7bxuwR/TR64CBVXj7PGI0xfk1Uf6W83DKjCQnsIeO5HUnNEEAAAb8TsNmN5HetdmODH1m8xFH6Q4sedGMtKBqBpguYwXhmbk7TM/LyHPg3/W0H8p741oJH/ivwzLo8PbZhvwrMfZcakKZFB2vJ5bFK6M6Gsw1g41Q/F2COjJ+/AWg+AggggAACCLhGYPHqbC1Yu7fBQYxZ+nLj9s3vvZyqghJjvhoJAQScEiCQcYqJkxBAAAEEEEAAgfMLmAHIQ8ZITFOSOYrzxGd7m5IF1yLgVwIEMn7V3TQWAQQQQAABBJwSqNynLZvzjP2VnEv7S8qdO/ECZ+UWuyafCxTDywj4hACBjE90I41AAAEEEEAAgUYLVGbrg1/P1pjEGJlzvRx/EmZpWaFd5q5KJAQQ8EyBZl21zDMJqBUCCDRWwPxl7++JlQj9/R1A+71ewL5Xq+76qX6vn2pZ6otq9fotuurd72nFa3MUzaZJXt+9NMC3BQhkfLt/aR0ClgmwYtkp2ppVy/Cw7K1GxghYKFCtw2//QQ9+2EsPrpuq6ICWOhkRppObP9Xmg7MUbS4/TkIAAY8V4NYyj+0aKoYAAggggAAC1gp8rc/f26jyEZdpfKgZtNhVdvy4vrG2UHJHAAEXCRDIuAiSbBBAAAEEEEDA2wRKVJh/TAHhIersqHqpdqfs0cnEoRrcndEYb+tN6ut/AgQy/tfntBgBBBBAAAEEHAJdFZvYRdUHinTI2B7cXrRWy94K0MwHZqi3Y37MCeW8eafGDJivtw9Xqzr5d/rh3OU6iB4CCHiEAF83eEQ3UAkEEEAAAQQQaH6BThp92x36/qyndNvP16trqU3xS57VgrHd5Ihj7EXKbP0D3ZL0pNanlGpS90AFtW+r1s1fUUpEAIE6BAhk6kBxxaGV24v095Sic7LaZU9yHEtdlnrOa+aBGwaFaMqAkDpf4yACniTAimWneoNVy2q/K1n0oLYHzzxdwKaA6Bl69r8z6q6oLVqXTeqqzVuf01tZWUr5IlejZ9+s9nWfzVEEEGhmAQIZC8DvXZWux5PPDWJOFRXs+JGWU1JnycuN4/fklugPV8XX+ToHEfAkAT60Sqxa9u07kuD2Wwse+ZJAkLqHdtY3ue9qVcj1umcIYYwv9S5t8W4B5si4uP+25JXUE8Q4V5gZBO05eNy5kzkLAQQQQAABBCwWqFR2Zqiuu3WY2lpcEtkjgIDzAgQyF7SyqzI/WVv2nrjgmeYJG/bWPdLi1MVnnfTBnkNnPeMhAggggAACCLhH4Lj257XRdXdfq/gAdsh0Tx9QKgJ1CxDI1HIxgpacd7Vk1jj1N3YsN2+TiIuKUb8fL1VhC+7Cq0XFEwQQQAABBPxAwF60Rq+sDtUlA+u/paxHcJBLNJJC27kkHzJBwB8E+HR+Vi/b8/+te2c9J/tdf9PWZTa9cd0cvTfpr/r77PhTq5ecdS4PEUDAPwXM20fNkde84nLlGn/ygkY4IGoW8BgX1VE9OwZqRGRHhQcH+icSrUbAZwTKlfHmCuVedrMGt65/NMb89/7IqB56aMP+Rrc+PKil7hwX2ejruRABfxMgkDnT4wf0zqO/1eqYu7R2WpwCbMWK6FWlLz7cqoNGIMM6YmegeICA3wkUlFToic/26rVdh1RQXuVov/mBY1RYW0WGdj/jcbi8WgvW7j3zfEJYO80fGc5KhGdEeICAtwkEKf72v+tDJ6u96LIYRXYM0pMb92vbkXInrzp12tw+XfTID2LVPpCPZg2C42S/FuBfS033H/1C739UruG/ukShji9dKnT82KkPLDWn8BMBBPxLoCaAqVmF0PygMcnYPO9Coy3mqM37xjy35bsPaerKdCV9kqeHx0cS0PjX24fW+qnAjcPCZf4hIYCA9QIEMjXGhwq1v7KNEkI6nDpSka1t2yqUMHOAvv2+teZkfiKAgK8LvLKlQP9jjK6YIzD3DA7R3eN6OX2r2LDIYJl/zG9nzT2lfmUEMmZAM83YW+qZqxOczsfXjWkfAggggAACTRFgsn+NXmisEjqUq7CoRHZV6eCHb+g/gdO1cGaCY36Mfc9zumrEYm2usqt03cOaePsqHa25lp8IIOAzAqUVVTL3gprzXpYSOgVp961DHPs6NXa+i7nBbcr8YXp6Qi+Z+0QNe2GrzBEbEgIIIIAAAgg0TYBApsav9Uj97KFLlf34HfrFgtt033uRWvzXezWmkzloVa3DO7Yp9+JBSmxZpqzPt6njoHh29q2x4ycCPiJgBjE/WrrdsReUOQrz8bzBSujuml0j7hgb6QiKTKrhL6c6Rmp8hI1mIIAAAggg4BYBbi07w95G0dOf0mfTzxw468EJZaUVKH6wEbwc2aSVH1RqyG/CWcnsLCEeIuALAjf9M01rDxzTiinxlsxnMYOi3QuGOYIl81azzcZyreYtaCQEEEAAAQQQaLgAIzLOmNn36YvPv9GQxONa+fhz+mh/RwUcy1ex3ZmLOQcBBLxBYPHqbMetX+YtYObtYFYlc0Wit2YPkLnq2TWvp8lcUICEAAIIIIAAAg0XIJBxxuzwbiVnZmrlo/+SfjBRPVuW6vDxVmpT/5LyzuTMOQgg4AEC5pwVc+8Hc1Uy8xYwq5MZzHw8Z6BjIYE7/rPH6uLIHwEEEEAAAZ8U4NYyJ7q1KjND39z/tr6YF+84e+rO25y4ilMQQMBbBBZ+kO0YIXny6lP/xpuj3uZtZuboj7nvzJqMQ5rYu0tzFEsZCCCAAAII+IwAIzIX7MoqFe7ZpfxjZcZqZhdOwcbtIq5I5s7gJAQQsF7AXB7ZnBfzqBFUNPdGdDcND1eSsTLaPe9nW99QSkAAAQQQQMDHBAhkLtihLdRpwPc1vku1TlzwXGnqwO6Ob3adOPW8p5gfbL4fz7ez5wXiBQRcKPDsxgJHMOGODezMwOmukT0cO4CzJLMLO5WsEEAAAQT8QoBA5oLdbFPbwbP0wOwhcmYR1pp7381gpDFpQlg7vXFt32b/ZrgxdeUaBLxdwJxob47GTEt03xcH5pcfZnpjW5G3c7qp/mUqSP5cKQVldZSfrhevHqwpf0mv47XvHKosUMonKSqodGbs/TvX8hQBBBBAwC0CrrkPyi1V99xCzXvfzQ3w9hw8rqPGruDOpg7GbWmu2rPC2TI5DwGvFahO0dOXz9Y7k5bpg7uSZCvfqN9Pvlfpt/1Tf5mjq5Z1AAAT40lEQVQW7lSzVqcfcpw3I8m6VcouVBHzyw9zkYHXdh0yNt680Nm8XlvA3KD4t7ru5wd150fDNaj2iw171qpce/52m+5Y8xu9s3g8+4Q1TI+zEUAAAbcIEMhYyE5QYiEuWSNwIFUbsjpq1LBox55O9swNWp3VQzOGdHXaZl1useNWUHf/Wx0b1VF/NQIZ88sPd9fFaTxPONG+R2888a6Cb31ZU0Ka+OvMFqMZD87Sq5Of1xs3jdItMcxT9IQupg4IIIBAfQLcWlafDq8hgICHCth1YmeytrdMVFIf86bPKh3cnqrcbv01sGeA43n+0hvU7+erdLSeFmQXV2hUmDM3jdaTiQte6htyqg75JeUuyM1HsrBv09MT+2rc/U/ruVsmqn9UtOKiL9X8NzNVebqJ1Slv6dVtiZphrDbnitXwbfE/NALhPXr1XztU7SOMNAMBBBDwZQECGV/uXdqGgM8KlCk9JU0VcUnq37mFVLFVS1/coJZDBynR8cX8Ce3NKFSP3pH13iJkzo8ZZ4yGuDsNiwx2VGFn4XF3V8Vzyi8r1N58Y/7Lv5Zr2+CH9f72j/S7K6v13v1LtLLIvGW3TLs/Wa/86CEaEtHKyXpXqXjTc5ozcrCuW2qsFFeZqVULr9KAqIlasqlUsoVryMgI5X/4mXYzVcZJU05DAAEE3CdAIOM+e0pGAIFGC3ytPdsPqtslFytGX2n9kl9rab5NMf1iTwcuhdq17aT69+2gnc9drxHXPK5NR5yfr9boanGhywTs+ZlKr7hIXa55QL/9+ThFtI/VVdNGK+gbY4PinceMco5r/96DCkiIU8+zh2NKP9HDoxM1YOqflf6dYRV7/tt66q3dOnE4QGEtU/X47S+qePRoxaqN2rU1I+Ag9YzrpYB9WcopJZJxWWeSEQIIIGCRAIGMRbBkiwACFgqc2KVNW06ofasifbLkAS3reolG2APVbu8/9OiKPNlP5CgtvZs6pz+huz8aqmdeWqARnZo4h8LC5vh+1ieU8+adGhNt3h42RFfe9pjeWLtHxfZSpTw2WRcvWmfcHHh2sqssJ1M5itP02ZeqsyNQsevkyUpjP68O6tLJvH3wsPKyj+qidu3U+uxLL2qjzt06K7R3T3X8zm84W8Q1enhmjIorv1HqP9cp4n8W6Ue2fKUHxqlPjLnSpE2t27bVRZUHVXiodo3OLoLHCCCAAAKeIfCd/+Y9o1LUAgEEEKhPwJ6dpp22i7T/hd/r1U636LEp4TpWFShbl0t14+SekuPb/J16/Y97dOkv5xHE1IfZHK9Vpeofv0vWiOc/1ievL9QE2wY9c9sVGho9UNNfaaPZUwaodphZrpy0TFUE9lVSQk2YUqLk9cmqaN9PSbE1x+qofNvhWvDvz7X6sSvU/eyRGsepp+dS2Tpo+Pz7NSPapuy0DFUNG6GkNuecXEfmHEIAAQQQ8CSB2r87PKlm1AUBBBCoU8D8MLpLgfOXa8ftfU9P8h6p17Nnnz7bWAjA+DY/15gYPilsl7amFsg+okOdk8HN/Z5SC83blNybzNXKzNSzo4+ulNUiQuPvWKiOY6IU0TZa9424VvfVS35UOcYcJ8X8UFGtTwUY9qI1emVFocKnXq1RHcxj3RWb2FHVh444FnRwbiego0pLzlCLMb/Qgu+FGO+JbG3/skjhF/fWqbXuqnX0yBFVB0Ur1ul5N/U2hBcRQAABBCwUYETGQlyyRgABKwROKDMtRy0CWtYZnEjmt/lZChx9gx6YO1r5f/6HPi+ve75DnBE4fOEBE+zTik4FUxHBjdtI1wpll+Zpi9DoWVeqX1snRz3shcrac1St2ttVYWxaWrxjuf533mKtDZmpR+8ec3oeVBtFGYs5VG3fqSxn7wKz71Pql0cVO3KgQsyqHN2pTSmtjLlUETKWjDDSCWUZ752qxDhF8TWfQ4S/EEAAAU8WIJDx5N6hbgggUIeAOZH/gA7kFRkhS13J/Da/WL17R6jjpddqZvDHeuWdfGNuxbnJXLFs25FyFRgflt2Z/ptb4ii+ZvUyd9bFI8o+nKUdeVVqkfqspgxK1NDJD2t995v156X3acyZuU4Biho3Tolfrden2084VW17/jZtzOmoi5MiHEFwdVaadlRGqG/C6ZXrqtP16QeHNHDSWEU5GXM5VTAnIYAAAghYIsB3TpawkikCCFgnEKaRV31f/91Xqq+N6CTinA+cIZr8p880+XQFFny0/rxVuTzBuCFp7V6tTj+kG4eFn/c8q194zdgMc24f526OsrounpB/dV6GMk720LSX3tavxnQ4b5Vs8VfrponL9NhrG3Tr4In1LrVtZmILmaxnkmeqW7D5q69KB4y9h/YH91eSY/NLu0o/fVNvHhmlhVfHnWe077xV4QUEEEAAATcIMCLjBnSKRACBpgi0V/95T+mlR66sI4hpWL4J3dvKnCfz5Mb9DbvQhWev3F6kgvIqTUokkDnFWq3i7CwV2XoqLqpN/dLGLWuT75urmHee0vNbS+s/13w1oPPpIMZ8Uqy0rZmyDeinODOuqdii55esVezCuzQlhO/4TCESAggg4OkC/G/t6T1E/RBAwFKBu0b20Jz3smQGFFMGhFhaVl2Z/+qTPIUHtXRL2XXVx/3HTs1TOdltvBJCL/QrymbsIzNPr+2c1/Bq2w8q05iH035oDzlCyMDhum/NxobnwxUIIIAAAm4TYETGbfQUjAACniAwdWB3RyBhBhTNnczgyZyjs3BUj+Yu2oPLa6/hi9Yoc/MiDb9QHNOUVthClHRJH/WODPnO0s9NyZRrEUAAAQSaU8BmN1JzFkhZCCDgGwJxUdHKzM3xicaYAcXUlel6xAgoFl0W0yxtMhcYGPbCVnVr3VIp84c1S5lWF+JL7wmrrcgfAQQQQKDpAozINN2QHBBAwMsFzFvKzMn2D23Y77jFzOrmlFZUadY/0xxzY964tq/VxZE/AggggAACPilAIOOT3UqjEECgoQJPXh2vCWHtHCMzW/JOLYfc0DycOd8MYm4ygpi1B45pxZR4mQsOkBBAAAEEEECg4QIEMg034woEEPBBgfaBLfV/P4p3zJcZ/nKqJSMzZhDzo6XbtTynxHEbmzsWF/DBrqNJCCCAAAJ+KkAg46cdT7MRQOBcAXN0ZMvPhpwZmVm8Oltm8OGKZI7yjP1zsmMk5uUrYpttLo4r6k4eCCCAAAIIeKIAgYwn9gp1QgABtwmEBwfqrdkDzsyZMYMPczGAxiZzUv+9q9JljvJ8VValj67v69bNNxvbDq5DAAEEEEDA0wRYtczTeoT6IOAlAv6wQtWajEO65/1sxxLJ5saZNw8K0eUJXS44r8UcxdlsjMC8llKkv+465OjRewaH6OEfxMi8hc1Xkz+8J3y172gXAggg4I0CBDLe2GvUGQEPEPCnD63miMyzGwsct4WZ9OYGlqPC2mpcVMdaPZFXXK6thcdrnXe9sRra3eN6yRzp8fXkT+8JX+9L2ocAAgh4gwCBjDf0EnVEwAMF/PFDq3mb2Or0Q1qXW6zs4oozAUtN99QEOEmh7XRJVLAm9nbsGV/zshf8rFL+0hs14aEN6vCTV7Rp8Vi1tOdoxU9n6v7VRWo96Ha9+NICjehU96iSP74nvKBTqSICCCDgswJ1/zby2ebSMAQQQKDxAuaoyo3Dwn14jssxZezIll1t1Lt3D2PH+1Lt+NMDenh1oWxh1+jRP84/bxDTeFWuRAABBBBAoHECTPZvnBtXIYAAAj4ocFBZu4uNdoVoQEJnFa97Unf9YZPK2ozRwpeX6KqIAB9sM01CAAEEEPBWAUZkvLXnqDcCCCDgaoETOUrbUy5dFKmY1p9q8Z1/V47idcMLT2huQhtXl0Z+CCCAAAIINEmAQKZJfFyMAAII+I6APT9T6RVGe9of1ce/+bUxB6iDxjzytB4c200232kmLUEAAQQQ8BEBbi3zkY6kGQgg4D6BkpIS9xXuspLtKsvJNEZgjFS6VWs3fG08KDM2BJVauawMMkIAAQQQQMB1AgQyrrMkJwQQ8EMBM4j5bN16H2h5pfIzc2UOyKjNEM2+eZza67hSV65Rht0HmkcTEEAAAQR8ToBAxue6lAYhgEBzCphBTHJyirx/VKZY6TvzDbpgjVn0hBbdeb0mtLfJnvYfvZVyojlJKQsBBBBAAAGnBAhknGLiJAQQQOBcgYqKCu3atdvxQur2Heee4E1H7IXK2nPUqHGI+iUac2I6jNS0ayKN55lavuJLGUsAkBBAAAEEEPAoAQIZj+oOKoMAAt4kkJ6eofLyUx/xU4xRGa9OpXnK2FdpTIjppdjIQKMpwbr48nHqqm/09XvvakMp95d5df9SeQQQQMAHBQhkfLBTaRICCDSPwMZNm84UdKS4WBkZGWeee9uD6qw07TDiGEX2UULnFsYDm4KGXaGrehhT/b/+RKs+Nyf/kxBAAAEEEPAcAZvdSJ5THWqCAALeIhAXFa3MXMcaV95SZZfW8+DBg3r+hb/UyrNPn0T9ePq0Wsf86Ym/vyf8qa9pKwIIIOAJAozIeEIvUAcEEPA6gU2bt5xTZ3O+jPdP+j+nWRxAAAEEEEDAIwUIZDyyW6gUAgh4soA5yd9cqezsFBQU5Hjq9ZP+z24UjxFAAAEEEPBgAQIZD+4cqoYAAp4pkJq6XWFhoZpz4+wzFVxwxy80YcJ4bdiw8cwxHiCAAAIIIICAdQItrcuanBFAAAHfFOjVK1LDhg2t1bjAwECNHTNaAwf0lzliYz4nIYAAAggggIB1AgQy1tmSMwI+L2BO7vb3NHvuLQ4CLPz9nUD7EUAAAQSaW4BAprnFKQ8BHxHw5xXLzu7CRxYvcTzF42wVHiOAAAIIIGC9AHNkrDemBAQQQAABBBBAAAEEEHCxAIGMi0HJDgEEEEAAAQQQQAABBKwXIJCx3pgSEEAAAQQQQAABBBBAwMUCBDIuBiU7BBBAAAEEEEAAAQQQsF6AQMZ6Y0pAAAEEEEAAAQQQQAABFwsQyLgYlOwQQAABBBBAAAEEEEDAegECGeuNKQEBBBBAAAEEEEAAAQRcLEAg42JQskMAAQQQQAABBBBAAAHrBQhkrDemBAQQQAABBBBAAAEEEHCxAIGMi0HJDgEEEEAAAQQQQAABBKwXsNmNZH0xlIAAAgh4t8DK7UV6Z/chFZdX1WrIrpw8x/M+0ZG1jptPkkLbae7wHgoPDjznNQ4ggAACCCCAQNMECGSa5sfVCCDgBwLTl6VqeU5Jo1oaHtRSS6fEa2LvLo26nosQQAABBBBAoG4Bbi2r24WjCCCAgEPglS0FjQ5izAwKjBGc2SvT0UQAAQQQQAABFwsQyLgYlOwQQMC3BFbt/rrJDTKDmS15jRvRaXLhZIAAAggggICPChDI+GjH0iwEEDiPgP1rbX5urkbH3KBl+SdVmfNvPXBFkuKGL9bm2tNfzpMBhxFAAAEEEEDAEwQIZDyhF6gDAgg0k8BJ5a98Uf9JP6wjrTqrZfofNf+ZQ7pkfIzUvp3atmimalAMAggggAACCDRZgECmyYRkgAAC3iPQShFTF+j6qCpVBu/UmyvC9MvHJsm2N1+BA/oq2uY9LaGmCCCAAAII+LsAgYy/vwNoPwJ+J/CVdnyZJ1urUbr9kemKbrFfu1KrNXREH7XxOwsajAACCCCAgPcKEMh4b99RcwQQaIxAWaaSUy/S6F/8VBM6t5QO7NSX+7upf2LXxuTGNQgggAACCCDgJgECGTfBUywCCLhHwJ61TVuPRmn4xaGyya6jyZuV2qq3+sS2dk+FKBUBBBBAAAEEGiVAINMoNi5CAAHvFDip/Vu3Kje4v5JiAo0mlCk7LUOVsX0U354JMt7Zp9QaAQQQQMBfBYz7KkgIIICAvwi0VPcrn9SWn3RVsCNuKdT2Lw8oeOhAxRDH+MubgHYigAACCPiIACMyPtKRNAMBBJwRsCmga00QY5x/IkPJ22zq37eX+FbHGT/OQQABBBBAwHMECGQ8py+oCQIINLOAPT9T6RXBiurZsZlLpjgEEEAAAQQQaKoAgUxTBbkeAQS8VsAWNlCjYqPVswcT/b22E6k4AggggIDfCnA3hd92PQ1HAAG1H6sH14ytF6JjkGv+m+zgonzqrSwvIoAAAggg4EcCjMj4UWfTVAQQaLjAz0b0aPhF37liWnSwErq3/c5RniKAAAIIIIBAUwQIZJqix7UIIODzAsMig7ViSnyj2zkhrJ1emtG30ddzIQIIIIAAAgjULWCzG6nulziKAAIIIFAjUFBSoU15xdpXXFFz6II/R/UKlhkIkRBAAAEEEEDA9QIEMq43JUcEEEAAAQQQQAABBBCwWIBbyywGJnsEEEAAAQQQQAABBBBwvQCBjOtNyREBBBBAAAEEEEAAAQQsFiCQsRiY7BFAAAEEEEAAAQQQQMD1AgQyrjclRwQQQAABBBBAAAEEELBYgEDGYmCyRwABBBBAAAEEEEAAAdcLEMi43pQcEUAAAQQQQAABBBBAwGIBAhmLgckeAQQQQAABBBBAAAEEXC9AION6U3JEAAEEEEAAAQQQQAABiwUIZCwGJnsEEEAAAQQQQAABBBBwvQCBjOtNyREBBBBAAAEEEEAAAQQsFiCQsRiY7BFAAAEEEEAAAQQQQMD1AgQyrjclRwQQQAABBBBAAAEEELBYgEDGYmCyRwABBBBAAAEEEEAAAdcLEMi43pQcEUAAAQQQQAABBBBAwGIBAhmLgckeAQQQQAABBBBAAAEEXC9AION6U3JEAAEEEEAAAQQQQAABiwUIZCwGJnsEEEAAAQQQQAABBBBwvcD/A+tenqaq5zY9AAAAAElFTkSuQmCC" alt="models_abc.png"></p>
<h4 id="6.1-Linear-Factor-Models">6.1 Linear Factor Models<a class="anchor-link" href="#6.1-Linear-Factor-Models">&#182;</a></h4><p>In a factor model, there is a set of hidden components, and each data point is associated with a hidden vector of weights, with one weight for each component.</p>
<p>Suppose the data are $p-$dimensional, the linear factor model contains $K$ components $\mu_{1:k}$, each of which is a p-vector. We can organize the components into a $K \times p$ matrix $\mu$. For each data point n, we draw a $K$-dimensional weight vector $w_n$ and then draw the data point from a distribution parameterized by $w_n^{T} \mu$.</p>
<h4 id="6.2-Mixed-Membership-Models">6.2 Mixed-Membership Models<a class="anchor-link" href="#6.2-Mixed-Membership-Models">&#182;</a></h4><p>In a mixed-membership model, each group is drawn from a mixture , in which the mixture proportions are unique to the group and the mixture components are shared across groups.</p>
<p>Mixed-membership models posit a set of global mixture components. Each data group arises when we first choose a set of mixture proportions and then, for each observation in the group, choose a mixture assignment from the per-group proportions and the data point from its corresponding component. The groups share the same set of components, but each exhibits them with a different proportion.</p>
<p>In figure b above:</p>
<ul>
<li>M groups, N data point, $x_{mn}$ is the n-th observation in the m-th group.</li>
<li>The hidden variable $\mu_k$ is an approiate parameter to a distribution of $x_{mn}$. (if the observation is discrete, then $\mu_k$ is discrete).</li>
<li>$p(. | \eta)$ an appropriate prior with hyperparameter $\eta$</li>
<li>$\theta_m$ is a hidden variable per-group mixture proportions, a point on the simplex (K-vectors positive summing to 1)</li>
<li>$z_{mn}$ per observation mixture assignments.</li>
</ul>
<h4 id="6.3-Matrix-Factorization-Models:">6.3 Matrix Factorization Models:<a class="anchor-link" href="#6.3-Matrix-Factorization-Models:">&#182;</a></h4><p>Recall Netflix challenge: in which each row is a user and each column is a movie ....</p>
<p>A matrix factorization model uses hidden variables to embed both the rows and the columns in a low-dimensional space. Each observed cell is modeled by a distribution whose parameters are a linear combination of the row embedding and column embedding. I.e. cells in single row share the same row embeding but are governed by different column embeddings.</p>
<p>In figure c above: the overlapping plates show how the observations at the nth row share its embedding $w_n$ but use different variables $\gamma_m$ for each column</p>
<p><img src="data:image/png;base64,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LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTc/te7acBEiABEiABEiABEiABEiABGxCgELTJliZKQmQAAmQAAmQAAmQAAmQAAl4LgEKTRv2/d3V76N8UDBKan8dMTHirg1LY9YkQAIkQAIkQAIkQAIkQAIk4BwEKDSdox9YCxIgARIgARIgARIgARIgARJwGwIUmm7TlWwICZAACZAACZAACZAACZAACTgHAQpN5+gH1oIESIAESIAESIAESIAESIAE3IYAhaazdWXEBLRVczrLv7cGj8zoTHbsPmJWfYg6wZXx7IQDuJ9iO2Kw5r1aap5oGnNE767BwDJqPmmrCYhMMa+M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sG7GFpR+6gncuX4R++YvxY32bfFkTkNLaBrF8DAJkAAJeAgBBgPykI52WDNz1sfQjYcx1KAC/VceRH+D79wkARIgARIgAccT8IJP+V74fVMvE1XJhiKBBXBj70xM3FIJr3/2AJu//x3frfNBhxmV4GPiCu4iARIgAU8nQIump98BbD8JkAAJkAAJkEAaBLyQWc3fjFywFvd7vIh6JYuj2P7N2F2hPVoGU2amAY+HSYAEPJQALZoe2vHO3Oxiua3z0LZWPs7MinUjARIgARKwB4HM8C9aFD45/dH7udLwunsA+bMURekX68E/Ba/ZO3fv2qNiLIMESIAEnJaAV7xKTls7VswjCVyPu4fW0/Zizdkb6W5/g0I5sLpnlXRfzwtJgARIgARIID0E4uLisHXbdiz7ZyeGx1ZKTxbJrglAHD7Mcxj169dDhQrlkx3jFxIgARJwZgIUms7cOx5cNxGbr8w+gLkRVy2m0D7YD790LIecPjTYWwyPF5AACZAACaSLgC4wN23ajNjYWC2Phb41sP12xrx02meLRsXYw1p+eXLnpuBMV+/wIhIgAUcQoNB0BHWWaTYBEZyHom8mO3/i1Ona9x5dOyXbL1/K+GenwHyECneQAAmQAAnYioApgVmoUACaNW2K27550XDKHpyJTd/a0eKdM79LBezatgWGApaC01a9yXxJgASsSYBC05o0mZddCHw6bLhWzseDB9mlPBZCAiRAAiRAAsYETAlMUwJQBkzn7TmPveduIDImwdKp53UwIkrbLBscqO/SPisF5ED5gOxoW8E/ab+55SVdwA0SIAEScDABCk0HdwCLt5wAhablzHgFCZAACZCAdQhYU/Cl53lmzfKtQ4S5kAAJkIBpApzEZpoL95IACZAACZAACZBAEgFnEXg+Pj6oW6c2qodW04IOiUvtlZgY/PnXfKxdu45zOJN6jBskQAKOJkCh6egeYPkkQAIkQAIkQAJOS8BZBKYxIApOYyL8TgIk4GwEKDSdrUdYHxIgARIgARIgAacgEL5ho9MH4UlNcG7eskULShQYWMwpeLISJEACnkWAQtOz+putJQESIAESIAESSIPA3r37NDdUcUmVZCrITxpZ2P2wKcF59uw5TJk6DcHBQagXFgYKTrt3CwskAY8mQKHp0d3PxpMACZAACZAACegEXFFg6nXXP00JzoiISMhfcDAF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" alt="time_series.png"></p>
<h4 id="6.4-Hidden-Markov-Models">6.4 Hidden Markov Models<a class="anchor-link" href="#6.4-Hidden-Markov-Models">&#182;</a></h4><p>In an HMM, each observation of the time series is drawn from an unobserved mixture component, and that component is drawn conditional on the previous observation's component. The posterior is similar to a mixture model, but one in chich the model assumes Markovian structure on the sequence of mixture assignments.</p>
<p>In figure d above:</p>
<ul>
<li>the global hidden variables are the mixture components $\mu_{1:k}$</li>
<li>Transition probabilities $\theta_{1:k}$. The transition probabilities provide K conditional distributions over the next component, given the value of the previous one.</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="7.-POSTERIOR-INFERENCE-WITH-MEAN-FIELD-VARIATIONAL-METHODS">7. POSTERIOR INFERENCE WITH MEAN FIELD VARIATIONAL METHODS<a class="anchor-link" href="#7.-POSTERIOR-INFERENCE-WITH-MEAN-FIELD-VARIATIONAL-METHODS">&#182;</a></h3><p>Three common posterior approximation algorithms:</p>
<ul>
<li><strong>Laplace Approxmation</strong>: represent the posterior as a Gaussian, derived from a Taylor approximation. It works well for simple model but are difficult for high-dimentional settings.</li>
<li><strong>MCMC</strong>: include fundamental algorithms such as Metropolis-Hastings, and Gibbs sampling. Such methods form a markov chain over the hidden variables whose stationary distribution is the posterior of interest. The algorithm simulates the chain, drawing consecutive samples from its transition distribution, to collect independent samples from its stationary distribution.</li>
<li><strong>Variational Inference</strong>: a deterministic alternative to MCMC in which sampling is replaced by optimization. In practice, variational inference tends to be faster than sampling methods, especially with large and high-dimensional data sets, but it has been less vigorously studied in the statistics literature. Using stochastic optimization, variational inference scales to massive data sets.</li>
</ul>
<h4 id="7.1-Conditionally-Conjugate-Models">7.1 Conditionally Conjugate Models<a class="anchor-link" href="#7.1-Conditionally-Conjugate-Models">&#182;</a></h4><p>To describe conditionally conjugate models, let $x = x\text{1:N}$ be observations, $\beta$ global latent variables, $z = z_{\text{1:N}}$ local latent variables, and $\eta$ fixed parameters.  We assume that the joint distribution factorizes as</p>
\begin{equation*}
p(\beta, z, x | \eta) = p(\beta | \eta) \prod_{n=i}^{N} p(z_n | \beta)p(x_n | z_n, \beta)
\label{eq:4} \tag{1}
\end{equation*}<p>The posterior inference problem is to compute the condional distribution of the latent variables given the data:</p>
\begin{equation*}
p(\beta, z, | x) = \frac{p(\beta , z, x)}{\int p(\beta, z, x) dz d\beta}
\label{eq:5} \tag{2}
\end{equation*}<p>Recall the posterior is essential becasue (1) it lets us examine the hidden structures that likely generated the data and (2) and it is the
gateway to prediction about new data. <strong>The difficulty in computing the posterior stems from the denominator p(x), the marginal probability of the data.</strong> For example, to compute this quantity in the mixture model we must marginalize out every possible combination of assignments of the data points to mixture components. (There are exponentially many such combinations. Hence we must approximate the posterior.</p>
<p>To complete our definitions, We assume that each complete conditional is in the exponential family. Recall many common distributions are in the exponential family: Gaussian, multinomial/categorical, Poisson, gamma,
Bernoulli, Dirichlet, beta. Also note if the distribution of x is in an exponential family, then its density has the form:</p>
\begin{equation*}
p(x | \eta) = h(x) \exp \{ \eta^{T}t(x) - \alpha(\eta) \}
\label{eq:6} \tag{3}
\end{equation*}<p>where</p>
<ul>
<li>t(x) is the function sufficient statistic</li>
<li>h(x) is the base measure</li>
<li>$\eta$ is the natural parameter</li>
<li>$\alpha (\eta)$ is the log normalizer, ensuring the density integrates to one.</li>
<li>The derivatives of $\alpha(\eta)$ are the cummulants of the sufficient statistic.</li>
</ul>
<p>It follows, the complete conditional for the global variable is</p>
\begin{equation*}
p(\beta | x, z) = h(\beta) \exp \{ \eta_{g}(x, z)^{T}t(\beta) - \alpha(\eta_{g} (x, z)) \}
\label{eq:7} \tag{4}
\end{equation*}<p>The complete conditional for the local variable is</p>
\begin{equation*}
p(z_n | x_n, \beta) = h(z_n) \exp \{ \eta_{l}(x_n, \beta)^{T}t(z_n) - \alpha(\eta_{l} (x_n, \beta)) \}
\label{eq:8} \tag{5}
\end{equation*}<p>Side notes: Requiring complete conditionals in the exponential family is less stringent than requiring full conjugacy. In contrast, consider the
classical Bayesian modeling setting, in which a latent variable is used as a parameter to the observations. The model is fully conjugate if the conditional distribution of the latent variable is in the same family as its prior, a property that depends on both the prior and the data-generating distribution. For example, if $\beta$ is drawn from a Dirichlet and $x_{1:N}$ are drawn from a multinomial with parameter $\beta$, then the conditional distribution of $\beta$ remains in the Dirichlet family. In complex latent variable models, however, the local variables prevent us from choosing priors to make the global variables conjugate to the observations, which is why we resort to approximate
inference. However, conditioned on both the local variables and observations we can often choose prior/likelihood pairs that leave the complete conditional in the same family as the prior.
Continuing with mixtures, we can use any common prior/likelihood pair (e.g., gamma/Poisson, Gaussian/Gaussian, Dirichlet/multinomial) to build an appropriate conditionally conjugate mixture model.</p>
<h4 id="7.2-Mean-Field-Variational-Inference">7.2 Mean Field Variational Inference<a class="anchor-link" href="#7.2-Mean-Field-Variational-Inference">&#182;</a></h4><p>Mean field inference is a fast and effective method for obtaining
approximate posteriors. The idea is to posit a family of distributions over the latent variableswith free parameters (termed variational parameters) and then fit those parameters to find the member of the family that is close to the posterior; closeness is measured by Kullback–Leibler (KL) divergence.</p>
<p><strong>The variational objective function</strong></p>
<p>We denote the variational family over the latent
variables by $q( \beta, z | v)$, where $ν$ are the free variational parameters that index the family. The goal of variational inference is to find the optimal variational parameters by solving</p>
\begin{equation*}
v^{*} = \text{argmin}_{v} \text{KL} (q(\beta, z | v) | | p(\beta, z | x)) 
\label{eq:9} \tag{6}
\end{equation*}<p>Unfortunately, computing the KL divergence implicitly requires computing p(x),which is difficult. Recall for continuous distribution, we have $$ \text{KL} (P || Q) = \int_{- \infty}^{\infty} p(x) \log( \frac{P(x)}{ q(x)}) dx$$</p>
<p>In this case we can rewrite the inner part of  equation (6) as</p>
\begin{align}
\int_{ \beta, z} q(\beta ,z | v) \log (\frac{q (\beta, z | v)}{p (\beta ,z | x)}) d\beta dz &amp;= \int_{ \beta, z} q(\beta ,z | v) \log (q (\beta, z | v)) d\beta dz \\
 &amp; - \int_{ \beta, z} q(\beta ,z | v) \log (p (\beta, z | x)) d\beta dz \\
 &amp; = \mathbb E \log(q(\beta, z | v)) - \int_{ \beta, z} q(\beta ,z | v) \log (\frac{p (\beta, z , x)}{p(x)}) d\beta dz  \\
 &amp; = \mathbb E \log(q(\beta, z | v))- \mathbb E \log(p(\beta, z, x | \eta)) + \log(p(x))
\end{align}<p>Hence variational inference optimzes (maximize) the related objective function</p>
\begin{equation*}
 \mathcal{L} (v) = \mathbb E \log(p(\beta, z, x | \eta)) - \mathbb E \log(q(\beta, z | v))
\label{eq:10} \tag{7}
\end{equation*}<p>Where all expectations are taken with respect to the variational distribution. Intuitively, the first term values variational distributions that place mass on latent variable configurations that make the data likely; the second term, which is the entropy of the variational distribution, values diffuse variational distributions.</p>
<p><strong>The Mean Field Variational Family</strong></p>
<p>Before optimizing the objective, we must specify the variational family, in which each latent variable is independent and governed by its own variational parameter. Let the variational parameters $ν = {\lambda, \phi_{1:N} }$, where $\lambda$ is a parameter to the global variable and $\phi_{1:N}$ are parameters to the local variables. The mean field family is
\begin{equation*}
 q(\beta, z | v) = q(\beta | \lambda) \prod_{n=1}^{N} q(z_n | \phi_n)
\label{eq:11} \tag{8}
\end{equation*}</p>
<p>Note:</p>
<ul>
<li>Each variable is independent but that the variables are not identically distributed</li>
<li>Although it cannot capture correlations between variables, this family is very flexible and can focus its mass on any complex configuration of them.</li>
<li>the data do not appear in the equation above</li>
</ul>
<p>To complete the specification, we set each variational factor to be in the same family as the corresponding complete conditional in the model (Equations 4 and 5). If $p(\beta | x, z)$ is a Gaussian, then λ are free Gaussian parameters; if $p( \phi_n | x_n, z)$ is discrete over K elements, then $\phi_n$ is a free
distribution over K elements.</p>
<p><strong>Coordinate Ascent Variational Inference</strong></p>
<p>Now we want to optimize equation 7 . In coordinate inference, we iteratively optimize each variational parameter while holding all the other variational parameters fixed.</p>
<p><strong>Algorithm</strong>: (Derivations can be found <a href="https://www.jmlr.org/papers/volume14/hoffman13a/hoffman13a.pdf">here</a>)</p>
<ol>
<li>Initialize global parameters $\lambda$ randomly</li>
<li>Repeat until the objective converges:<ul>
<li>for each data point, update local parameter $\phi_n$ using $\phi_n^{*}= \mathbb E_{q} [\eta_{l} (\beta, x_n)]$</li>
<li>Update the global $\lambda$ using $\lambda^{*} = \mathbb E_{q} [\eta_g (z, x)]$</li>
</ul>
</li>
</ol>
<p>This algorithm provably goes uphill in the variational objective function, leading to a local optimum. In practice, one uses multiple random restarts to find a good local optimum. Also note the coordinate-ascent variational inference relates closely to the expectation maximization algorithm of Dempster et al. (1977).</p>
<p><strong>Example</strong></p>
<p>For Gaussian mixture model. The latent variables are the mixture assignments $z_{1:N}$ and the mixture components $\mu_{1:k}$. The mean field variational family is $$q(\mu,z)= \prod_{k=1}^{K} q(\mu_k | \lambda_k) \prod_{n=1}^{N} q (x_n | \phi_n)$$</p>
<p>where</p>
<ul>
<li>$\lambda_k$: global variational paramenters, Gaussian variational means, which describe the distribution over each mixture components</li>
<li>$\phi_n$: local variational parameters, discrte distributions over $K$ elements</li>
</ul>
<p>Sooo</p>
<ul>
<li>In step 2a, we estimate the approximate posterior distribution of the mixture assignment for each data point;</li>
<li>in step 2b, we reestimate the locations
of the mixture components.</li>
</ul>
<p><strong>Extensions</strong>
The coordinate ascent inference algorithm described above is the simplest variational inference algorithm. Structured variational inference (Saul &amp; Jordan 1996) relaxes the mean field assumption; the variational distribution allows some dependencies among the variables. Nonconjugate variational inference (Knowles &amp; Minka 2011, Wang &amp; Blei 2013) relaxes the assumption that the complete conditionals are in the exponential family.These algorithms generalize previous research on nonconjugate models, which required specialized approximations for the particular model at hand.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="8-Model-Criticism">8 Model Criticism<a class="anchor-link" href="#8-Model-Criticism">&#182;</a></h3><p>Typically, we perform two types of tasks with a model:</p>
<ul>
<li>Exploration: use our inferences about the hidden variables—usually through approximate posterior expectations—to summarize the data, visualize the data, or facet the data, that is, divide it into groups and structures dictated by the inferences. Examples of exploratory tasks include using topic models to navigate large collections of documents and using clustering models on microarray data to suggest groups of related genes.</li>
<li>Prediction: forecase future data by using the posterior predictive distribution: $$p(x_{\text{new}} | x) = \int p(\beta | x) (\int p(z_{\text{new}} | \beta) p(x_{\text{new}} | z_{\text{new}}, \beta) dz_{\text{new}}) d \beta$$ Usually, the posterior $p(\beta | x)$ is not available, so we substitute an approximation, $q(\beta)$, which we find by an approximate inference algorithm such as MCMC or variational inference.</li>
</ul>
<p>We review two useful general techniques: <strong>predictive likelihood with
sample-reuse (Geisser 1975)</strong> and <strong>posterior predictive checks</strong> (Box 1980, Rubin 1984, Meng 1994, Gelman et al. 1996).</p>
<h4 id="8.1:-Predictive-Sample-Reuse">8.1: Predictive Sample Reuse<a class="anchor-link" href="#8.1:-Predictive-Sample-Reuse">&#182;</a></h4><p>Geisser (1975) proposed predictive sample reuse (PSR), which amounts to using cross-validation to estimate this probability.
Let $x_{[n]}$ be the data set with the nth item removed. Suppose our model is $p(\beta, z, x)$ and we use variational inference to approximate the posterior $p(\beta, z | x_{[n]})$ with $q_{[n]}(\beta, z)$. The log predictive likelihood for the nth data point is $$l_n= \log p(x_n | x_{[n]})= \log \int (\int p(x_n | z_n)q(z_n) dz_n) q_{[n]}(\beta) d \beta$$</p>
<p>The full predictive likelihood is $\sum_{i=1}^{N} l_n$ It estimates the held-out log probability of new data with leave-one-out cross-validation. In practice, we can use K-fold cross-validation to estimate the score. We divide our data into K groups; we iteratively hold each group out and approximate the posterior over the global variables $\beta$ with the rest of the data; finally, we compute $l_n$ for each data point, integrating
over the approximate posterior estimated from data that do not contain the nth point.</p>
<p>One advantage of PSR is that it does not simply help evaluate the modeling assumptions but also places all approximate inference algorithms on the same playing field. the log predictive probability of Equation above evaluates the predictive distribution no matter how it was
approximated. PSR easily lets us compare two different approximations of the same predictive distribution.</p>
<h4 id="8.2:-Posterior-Predictive-Checks">8.2: Posterior Predictive Checks<a class="anchor-link" href="#8.2:-Posterior-Predictive-Checks">&#182;</a></h4><p>Posterior predictive checks (PPCs) (Guttman 1967, Box 1980, Rubin 1984, Meng 1994, Gelman et al. 1996) help answer the important question, “Is my model good enough in the ways that matter?” In a PPC, we locate the observed data in its posterior predictive distribution. If we find
that our observed data are not typical—that is, they have low probability under the posterior predictive distribution—then there may be an issue with the model.</p>
<p>We define a discrepancy $T(X)$ to be a function of the data that matters to us; it is a property of the data that we hope our model captures in its predictive distribution (The function T(X) is also called a test statistic.) Let $x^{rep}$ be a random set of new hypothetical future
observations, a data set drawn from the posterior predictive distribution. Then, 
$$PPC = P(T (X ^{rep}) &gt; T (x) | x).$$
Note the only random variable is the expression $x^{rep}$. This PPC is the probability that the replicated data are far away (in terms of T ) from the observations.</p>
<p>An important development from Meng (1994) is to define the discrepancy as a function of both the data and the latent variables T (x, β). Then 
$$PPC = P(T (X ^{rep}, \beta) &gt; T (x, \beta) | x).$$
Here, both the hidden variables β and the replicated data x^{rep} are random. Their joint distribution is a product of the posterior and data-generating distribution: $$p(β, x^{rep} | x) = p(β | x) p(x^{rep} | β)$$.
Thus, the PPC can be decomposed as an expectation of an indicator:
$$PPC = \int p(\beta | x) \int p(x^{rep} | \beta) \mathbb 1 [T(x^{rep}, \beta) &gt; T(x, \beta)] dx^{rep}d \beta$$</p>
<p>A key advantage of the PPC methodology is that it is adaptable to the particular needs of the
practitioner. For example, the discrepancy can be themedian of the log probabilities to account for
outliers, a set of conditional probabilities if that is how the model will be used, or weighted toward
the types of observations that are important to model well in the application at hand. Furthermore,
we can look at multiple discrepancies, even reusing computation to do so, to understand trade-offs
involved among various models.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Reference">Reference<a class="anchor-link" href="#Reference">&#182;</a></h3><p>Blei DM. 2014. Build, compute, critique, repeat: data analysis with latent variable models. Annu. Rev. Stat.
Appl. 1:203–32</p>

</div>
</div>
</div>
    </div>
  </div>
</body>

 


</html>
