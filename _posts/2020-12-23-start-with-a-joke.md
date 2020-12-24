<!DOCTYPE html>
<html>
<head><meta charset="utf-8" />

<title>revenue_prediction</title>

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
<h2 id="Henry-and-Henry's-Research">Henry and Henry's Research<a class="anchor-link" href="#Henry-and-Henry's-Research">&#182;</a></h2><h3 id="Suppose-Henry's-boss-wants-Henry-to-predict-next-year-revenue.-Henry-decided-to-make-a-regression-model-to-impress-his-boss.-Henry-decided-to-plot-the-year-revenue-curve-and-fit-a-regression-line.">Suppose Henry's boss wants Henry to predict next year revenue. Henry decided to make a regression model to impress his boss. Henry decided to plot the year-revenue curve and fit a regression line.<a class="anchor-link" href="#Suppose-Henry's-boss-wants-Henry-to-predict-next-year-revenue.-Henry-decided-to-make-a-regression-model-to-impress-his-boss.-Henry-decided-to-plot-the-year-revenue-curve-and-fit-a-regression-line.">&#182;</a></h3><p>Henry spent the morning finding this <a href="https://www.macrotrends.net/stocks/charts/SCGLY/societe-generale-group/revenue">extremely reliable source</a>: the revenues between 2010 and 2019 were: 79619, 29458, 29920, 30530, 31603, 28726, 28138, 27179, 29833, 27487 millions.</p>
<p>Henry was excited but he forgot how to do regression, so he asked his intern (from Emory University?) to do this instead. Here is the plot his intern presented to him:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Coefficients: 
 [[-3119.60606061]]
r-square: [0.67403379]
</pre>
</div>
</div>

<div class="output_area">



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Henry was happy. When the intern asked him how to improve the plot, Henry replied for two words: "<strong>Bigger Plot</strong>" . The intern looks concerned but went ahead to make this:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Coefficients: 
 [[-3119.60606061]]
intercept: [50593.33333333]
r-square: [0.67403379]
</pre>
</div>
</div>

<div class="output_area">



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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atSoQMdF0lVGRqyf+ooVMGgQtNpqTXrZMrjnHmjWDI45BoYM8aUz6SDyJN3MyuAT9Bzn3Kjg8I9BmUte3fqq4PgyoGG+L28QHNvR8QYJjouIiBRLAwcOpGL+u+zwNekDBw6MKCKRole9eqyf+vTp/mbSPfeMH/PFF3DJJVCnjr8Z9eOPITc3knB3SdTdXQwYAsx2zv0n36kxQF6Hll7A6/mOXxh0eTkCWBuUxbwLnGJm1YNOMKcA7wbn1pnZEcH3ujDftURERIqdHj16MHjwYDIzMzEzMjMzddOolCgHHuj7qS9d6ts0du0KpUvHzm/YAM89ByecAE2a+HaPCW7jiFzU3V2OAT4DpgN5v8v8HV+X/jLQCFgEnOOcWxMk2o8DHYANQB/n3KTgWhcFXwsw0DmXHRxvBQwFKgBvA1e7nTxp3TgqIiIiUnysWgUvvOC7w8yYse15M5gwYdtymaKWNt1dUoWSdBEREZHixzmYPNkn68OH+x1NARo18psolUpyjUladHcRERERESlKZn61fNAgf7PpiBH+5tOLLkp+gr4zpXc+RERERESkeClf3rdvPPdcv8KealLsdwYRERERkeQyizqCbSlJFxERERFJMUrSRURERERSjJJ0EREREZEUoyRdRERERCTFKEkXEREREUkxStJFRERERFKMknQRERERkRSjJF1EREREJMUoSRcRERERSTFK0kVEREREUoySdBERERGRFKMkXUREREQkxShJFxERERFJMUrSRURERERSjJJ0EREREZEUoyRdRERERCTFKEkXEREREUkxStJFRERERFKMknQRERERkRSjJF1EREREJMUoSRcRERERSTHmnIs6hpRjZj8BiyL41rWA1RF831Sl+YjRXMTTfMTTfMRoLuJpPmI0F/E0HzFRzkWmc652ohNK0lOImU1yzrWKOo5UofmI0VzE03zE03zEaC7iaT5iNBfxNB8xqToXKncREREREUkxStJFRERERFKMkvTUMjjqAFKM5iNGcxFP8xFP8xGjuYin+YjRXMTTfMSk5FyoJl1EREREJMVoJV1EREREJMUoSRcRERERSTFK0ouQmTU0s4/MbJaZzTSza4LjNczsfTObG/xbPTi+n5mNN7ONZnbDVtfqYGbfm9k8M+sfxfMprJDn41kzW2VmM6J4LmEIaz62d510EuJclDezCWY2LbjOHVE9p8II8/9KcD7DzKaY2ZvJfi6FFfL7xkIzm25mU81sUhTPp7BCno9qZvaKmX1nZrPN7MgontPuCvF9o1nwmsh7rDOza6N6Xrsr5NfGdcE1ZpjZi2ZWPorntLtCnotrgnmYmezXhWrSi5CZ1QXqOue+MbMqwGTgdKA3sMY5d6/5hLu6c+5mM9sTyAzG/OKc+3dwnQxgDnAysBSYCHR3zs1K+pMqhLDmI7hWW2A98Jxz7sBkP5cwhPj6SHiddHp9hDgXBlRyzq03szLA58A1zrmvInhauy3M/yvB9a4HWgF7OOc6J/O5FFbI7xsLgVbOubTdwCXk+RgGfOace8bMygIVnXO/Jvs57a6w/58E18wAlgFtnHNRbGq420J8H62Pf+9s7pz7w8xeBsY654Ym/1ntnhDn4kBgBNAa2AS8A1zunJuXjOehlfQi5Jxb4Zz7Jvj4N2A2UB/oCgwLhg3Dvyhwzq1yzk0E/trqUq2Bec65H5xzm/AvmK5JeAqhCnE+cM59CqxJRtxFJaz52MF10kaIc+Gcc+uDT8sEj7RbiQjz/4qZNQBOBZ5JQuihC3MuioOw5sPMqgJtgSHBuE3plKBDkb022gHz0y1Bh9DnozRQwcxKAxWB5UUcfqhCnIv9ga+dcxucc5uBT4Azk/AUACXpSWNmWcChwNfAXs65FcGplcBeO/ny+sCSfJ8vJc2SsK0Vcj6KnbDmY6vrpKXCzoX50o6pwCrgfedc2s4FhPLaeBi4CcgtiviSKYS5cMB7ZjbZzPoWSZBJVMj5aAz8BGSbL4V6xswqFVWsRS3EnynnAS+GGlwECjMfzrllwL+BxcAKYK1z7r0iC7aIFfK1MQM41sxqmllFoBPQsIhC3YaS9CQws8rAq8C1zrl1+c855xxpuNJXGJqPeGHNx46uky7CmAvn3BbnXAugAdA6+HNlWirsfJhZZ2CVc25y0UWZHCH9PznGOXcY0BG4MiibS0shzEdp4DDgCefcocDvQLre7xTWe2hZ4DRgZOhBJlEI7xvV8SvOjYF6QCUz61lE4Rapws6Fc242cB/wHr7UZSqwpWii3ZaS9CIW1MW+CuQ450YFh38M6qXy6qZW7eQyy4j/za1BcCzthDQfxUZY87Gd66SVsF8bwZ/uPwI6hB1rMoQ0H0cDpwW12COAE83shSIKuciE9doIVghxzq0CXsOXEqadkOZjKbA031+aXsEn7Wkl5PeNjsA3zrkfw480OUKaj5OABc65n5xzfwGjgKOKKuaiEuL7xhDnXEvnXFvgF/w9gkmhJL0IBTexDQFmO+f+k+/UGKBX8HEv4PWdXGoi0NTMGge/6Z8XXCOthDgfxUJY87GD66SNEOeitplVCz6ugL/Z+rvwIy5aYc2Hc+4W51wD51wW/n1jnHMurVbEQnxtVApuICMo6zgF/6fstBLia2MlsMTMmgWH2gFpc7M5FMnPlO6kcalLiPOxGDjCzCoG12yHr+lOG2G+NoKbSjGzRvh69OHhRrsDzjk9iugBHIP/U8q3+D+RTMXXM9UEPgTmAh8ANYLxdfCrG+uAX4OP9wjOdcL/9jYfGBD1c0uB+XgRXyv3V3D84qifX1Tzsb3rRP38IpqLg4EpwXVmALdH/dyinI+trnk88GbUzy3C18bewLTgMVPvow6gBTApuNZofKeLyJ9jRHNRCfgZqBr180qR+bgDv8AxA3geKBf184twLj7D/wI7DWiXzOehFowiIiIiIilG5S4iIiIiIilGSbqIiIiISIpRki4iIiIikmKUpIuIiIiIpBgl6SIiIiIiKUZJuoiIiIhIilGSLiIiIiKSYv4fKG14l1lWOmEAAAAASUVORK5CYII=
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Henry was excited, not only because of the larger plot which can impress his manager, but because he could now apply his solid quantitative skills developped from Midd to predict 2020 revenue. Based on the coefficient, Henry did this:</p>
<p><strong>y_2020= -3119*2020+50593= 19403 millions dollars</strong></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Henry felt crestfallen: "bellow 20000 Millions!!! my boat, my bonus, my new Tesla model XXX! No I wouldn't show this to my manager". Henry never gave up; he thought the intern must have done something fundamentally stupid. And the plot looked urgly anyway, because there was no clear trend of going up or going down. Not good!</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Suddenly, there was a violent lightening strike in his office and a light bulb appeared in Henry's head. The Intern later claimed he did see the actual light bulb in Henry's head himself, as if seeing the face of god. It still remained unclear whether that was a mystical experiences for both Henry and his intern (and this is still under dabate by many famous theologists), but Henry's ideas had fundamentally revolutionalized the sciences forever:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h1 id="Henry's-BIG-idea:-what-if-we-sort-the-year-and-revenus-independently-and-in-increasing-order?-Will-we-have-a-better-2020-revenue?-Will-my-boss-love-me-again-because-of-this?">Henry's BIG idea: what if we sort the year and revenus independently and in increasing order? Will we have a better 2020 revenue? Will my boss love me again because of this?<a class="anchor-link" href="#Henry's-BIG-idea:-what-if-we-sort-the-year-and-revenus-independently-and-in-increasing-order?-Will-we-have-a-better-2020-revenue?-Will-my-boss-love-me-again-because-of-this?">&#182;</a></h1>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Henry asked his intern to make another plot based on his new idea, though the intern looked very suspicious of Henry's new idea. But as always, the Emory intern had to listen to his boss. Here is the new plot the intern generated for Henry:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">

<div class="output_wrapper">
<div class="output">

<div class="output_area">

<div class="output_subarea output_stream output_stdout output_text">
<pre>Coefficients: 
 [[3431.58181818]]
intercept: [14811.8]
r-square: [0.59639035]
</pre>
</div>
</div>

<div class="output_area">



<div class="output_png output_subarea ">
<img src="data:image/png;base64,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
"
>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Henry was in ecstacy, not only because now there was a clear increasing trend in the plot, but because he could now apply his math skills developped from Midd again to predict 2020 revenue. Based on the coefficient, Henry did this:</p>
<p><strong>y_2020= 3431*2020+14811= 6945431 millions dollars !!!!!!!!!!!!</strong></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="prompt input_prompt">
</div><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h4 id="Sometimes-just-a-small-modifications-of-conventional-ideas-could-lead-to-BIG-advance-in-sciences.--Henry-reported-his-predictions-to-his-boss,-and-everyone-was-super-excited.-The-very-next-day,-the-Nobel-committe-called,-and-Henry-was-awarded-a-Nobel-prize-in-Economics-due-to-his-special-contribution-to-coporate-finance.-Nowadays,-Henry's-sorting-method-is-known-as-&quot;stochastic-monte-Carlo-mystical-reordering-method&quot;,-which-has-been-widely-adopted-in-both-academia-and-industry.-He-later-accepted-a-Tenure-position-at-UChicago-and-became-so-rich-that-he-bought-best-friend-a-new-house-in-Hyde-Park,-Chicago,-IL.">Sometimes just a small modifications of conventional ideas could lead to BIG advance in sciences.  Henry reported his predictions to his boss, and everyone was super excited. The very next day, the Nobel committe called, and Henry was awarded a Nobel prize in Economics due to his special contribution to coporate finance. Nowadays, Henry's sorting method is known as "stochastic monte Carlo mystical reordering method", which has been widely adopted in both academia and industry. He later accepted a Tenure position at UChicago and became so rich that he bought best friend a new house in Hyde Park, Chicago, IL.<a class="anchor-link" href="#Sometimes-just-a-small-modifications-of-conventional-ideas-could-lead-to-BIG-advance-in-sciences.--Henry-reported-his-predictions-to-his-boss,-and-everyone-was-super-excited.-The-very-next-day,-the-Nobel-committe-called,-and-Henry-was-awarded-a-Nobel-prize-in-Economics-due-to-his-special-contribution-to-coporate-finance.-Nowadays,-Henry's-sorting-method-is-known-as-&quot;stochastic-monte-Carlo-mystical-reordering-method&quot;,-which-has-been-widely-adopted-in-both-academia-and-industry.-He-later-accepted-a-Tenure-position-at-UChicago-and-became-so-rich-that-he-bought-best-friend-a-new-house-in-Hyde-Park,-Chicago,-IL.">&#182;</a></h4>
</div>
</div>
</div>
    </div>
  </div>
</body>

 


</html>
