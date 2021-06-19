# Awesome ReDoS Security

[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)

This is a list of useful info for real world ReDoS (AKA RegEx DoS, AKA
Regular Expression Denial of Service) vulnerabilities.
ReDoS is primarily caused by catastrophic backtracking (AKA evil RegEx).
ReDoS vulnerabilities are interesting because they are fairly easy to verify,
but at the time this repo was created, there is no "go to" tool for identifying
ReDoS vulnerabilities in codebases. However, several researchers have
found multiple vulnerabilities of this type.

------

## Contributions

Contributions are welcome! Updates with new CVEs are particularly helpful.

------

## Contents

- [ReDoS CVEs](#ReDoS_CVEs)
- [ReDoS Tools](#ReDoS_Tools)
- [ReDoS Vulnerable Expressions Lists](#ReDoS_Expressions)

------

## <a name="ReDoS_CVEs"></a>ReDoS CVEs

This table captures a list of real-world security issues along with the actual
commit showing the before (vulnerable) and after (presumably not vulnerable)
regular expressions. This information was manually collected using the
[NVD CVE database](https://nvd.nist.gov/vuln/search) with queries such as
"regex dos", "regex backtrack", and "regular expression denial of service". Other useful lists include [this list](https://github.com/sola-da/ReDoS-vulnerabilities) from TU Darmstadt, [this list](https://github.com/yetingli/PoCs) from Yeting Li, and [this list](https://github.com/doyensec/regexploit#trophy-bugs-reported-trophy) from Doyensec.

To Do: Group CVEs by year, possibly sort by CVE ID or programming language

| CVE | Vulnerable Project | Main Project Language | Fix Commit | Related Links | Advisories |
| :-- | :----------------- | :------- | :--------- | :------- | :------- |
| [CVE-2021-21254](https://nvd.nist.gov/vuln/detail/CVE-2021-21254) | [ckeditor5](https://github.com/ckeditor/ckeditor5) | JavaScript | [5ba3bf5](https://github.com/ckeditor/ckeditor5/commit/5ba3bf5f418e846b74f67e6c29b4aebdbd7ceaab) | | [Advisory](https://github.com/ckeditor/ckeditor5/security/advisories/GHSA-hgmg-hhc8-g5wr) |
| [CVE-2021-21267](https://nvd.nist.gov/vuln/detail/CVE-2021-21267) | [schema-inspector](https://github.com/schema-inspector/schema-inspector) | JavaScript | [PR #92](https://github.com/schema-inspector/schema-inspector/pull/92/files) | | [Advisory](https://github.com/schema-inspector/schema-inspector/security/advisories/GHSA-f38p-c2gq-4pmr) |
| [CVE-2021-21306](https://nvd.nist.gov/vuln/detail/CVE-2021-21306) | [marked](https://github.com/markedjs/marked) | JavaScript | [PR #1864](https://github.com/markedjs/marked/pull/1864)  | [Issue #1927](https://github.com/markedjs/marked/issues/1927) | [Advisory](https://github.com/markedjs/marked/security/advisories/GHSA-4r62-v4vq-hr96) |
| [CVE-2021-21317](https://nvd.nist.gov/vuln/detail/CVE-2021-21317) | [uap-core](https://github.com/ua-parser/uap-core) | JavaScript | [dc9925d](https://github.com/ua-parser/uap-core/commit/dc9925d458214cfe87b93e35346980612f6ae96c) | | [Advisory](https://github.com/ua-parser/uap-core/security/advisories/GHSA-p4pj-mg4r-x6v4) |
| [CVE-2021-21391](https://nvd.nist.gov/vuln/detail/CVE-2021-21391) | [ckeditor5](https://github.com/ckeditor/ckeditor5) | JavaScript | [e36175e](https://github.com/ckeditor/ckeditor5/commit/e36175e86b7f5ca597b39df6e47112b91ab4e0a0) | | [Advisory](https://github.com/ckeditor/ckeditor5/security/advisories/GHSA-3rh3-wfr4-76mj) |
| [CVE-2021-22880](https://nvd.nist.gov/vuln/detail/CVE-2021-22880) | [Ruby on Rails](https://github.com/rails/rails) | Ruby | [eddda4d](https://github.com/rails/rails/commit/eddda4d8fb6b6508e11196b14494ceac37b57339) | [HackerOne Report](https://hackerone.com/reports/1023899) | |
| [CVE-2021-23341](https://nvd.nist.gov/vuln/detail/CVE-2021-23341) | [prismjs](https://github.com/PrismJS/prism) | JavaScript | [PR #2584](https://github.com/PrismJS/prism/pull/2584/files) | [Issue #2583](https://github.com/PrismJS/prism/issues/2583) | |
| [CVE-2021-23343](https://nvd.nist.gov/vuln/detail/CVE-2021-23343) | [path-parse](https://github.com/jbgutierrez/path-parse) | JavaScript | [Fork PR](https://github.com/jbgutierrez/path-parse/pull/10/files) | [Issue #8](https://github.com/jbgutierrez/path-parse/issues/8) | |
| [CVE-2021-23346](https://nvd.nist.gov/vuln/detail/CVE-2021-23346) | [html-parse-stringify](https://github.com/HenrikJoreteg/html-parse-stringify) | JavaScript | [c7274a4](https://github.com/HenrikJoreteg/html-parse-stringify/commit/c7274a48e59c92b2b7e906fedf9065159e73fe12) | | |
| [CVE-2021-23354](https://nvd.nist.gov/vuln/detail/CVE-2021-23354) | [node printf](https://github.com/adaltas/node-printf) | JavaScript | [PR #32](https://github.com/adaltas/node-printf/pull/32) |  |  |
| [CVE-2021-23364](https://nvd.nist.gov/vuln/detail/CVE-2021-23364) | [browserslist](https://github.com/browserslist/browserslist) | JavaScript | [PR #593](https://github.com/browserslist/browserslist/pull/593/files) [c091916](https://github.com/browserslist/browserslist/commit/c091916910dfe0b5fd61caad96083c6709b02d98) | | |
| [CVE-2021-23368](https://nvd.nist.gov/vuln/detail/CVE-2021-23368) | [post-css](https://github.com/postcss/postcss) | JavaScript | [8682b1e](https://github.com/postcss/postcss/commit/8682b1e4e328432ba692bed52326e84439cec9e4) [b6f3e4d](https://github.com/postcss/postcss/commit/b6f3e4d5a8d7504d553267f80384373af3a3dec5) | | |
| [CVE-2021-23371](https://nvd.nist.gov/vuln/detail/CVE-2021-23371) | [chrono](https://github.com/wanasit/chrono) | JavaScript | [98815b5](https://github.com/wanasit/chrono/commit/98815b57622443b5c498a427210ebd603d705f4c) | [Issue #382](https://github.com/wanasit/chrono/issues/382) | |
| [CVE-2021-23382](https://nvd.nist.gov/vuln/detail/CVE-2021-23382) | [postcss](https://github.com/postcss/postcss) | JavaScript | [2b1d04c](https://github.com/postcss/postcss/commit/2b1d04c867995e55124e0a165b7c6622c1735956) |  |  |
| [CVE-2021-23388](https://nvd.nist.gov/vuln/detail/CVE-2021-23388) | [forms](https://github.com/caolan/forms) | JavaScript | [PR #214](https://github.com/caolan/forms/pull/214) | | |
| [CVE-2021-25292](https://nvd.nist.gov/vuln/detail/CVE-2021-25292) | [Python Pillow](https://github.com/python-pillow/Pillow) | Python | [3bce145](https://github.com/python-pillow/Pillow/commit/3bce145966374dd39ce58a6fc0083f8d1890719c) [cbdce6c](https://github.com/python-pillow/Pillow/commit/cbdce6c5d054fccaf4af34b47f212355c64ace7a) |  | [Advisory](https://github.com/advisories/GHSA-9hx2-hgq2-2g4f) |
| [CVE-2021-27290](https://nvd.nist.gov/vuln/detail/CVE-2021-27290) | [ssri](https://github.com/npm/ssri) | JavaScript | [76e2233](https://github.com/npm/ssri/commit/76e223317d971f19e4db8191865bdad5edee40d2) | [Email exchange](https://github.com/yetingli/SaveResults/blob/main/pdf/ssri-redos.pdf) | |
| [CVE-2021-27291](https://nvd.nist.gov/vuln/detail/CVE-2021-27291) | [pygments](https://github.com/pygments/pygments) | Python | [2e7e8c4](https://github.com/pygments/pygments/commit/2e7e8c4a7b318f4032493773732754e418279a14) | | |
| [CVE-2021-27292](https://nvd.nist.gov/vuln/detail/CVE-2021-27292) | [ua-parser-js](https://github.com/faisalman/ua-parser-js) | JavaScript | [809439e](https://github.com/faisalman/ua-parser-js/commit/809439e20e273ce0d25c1d04e111dcf6011eb566) | [Gist](https://gist.github.com/b-c-ds/6941d80d6b4e694df4bc269493b7be76) | |
| [CVE-2021-28092](https://nvd.nist.gov/vuln/detail/CVE-2021-28092) | [is-svg](https://github.com/sindresorhus/is-svg) | JavaScript | [01f8a08](https://github.com/sindresorhus/is-svg/commit/01f8a087fab8a69c3ac9085fbb16035907ab6a5b) | | |
| [CVE-2021-29469](https://nvd.nist.gov/vuln/detail/CVE-2021-29469) | [node-redis](https://github.com/NodeRedis/node-redis) | JavaScript | [PR #1595](https://github.com/NodeRedis/node-redis/pull/1595/files) | | [Advisory](https://github.com/NodeRedis/node-redis/security/advisories/GHSA-35q2-47q7-3pc3) |
| [CVE-2021-32640](https://nvd.nist.gov/vuln/detail/CVE-2021-32640) | [ws](https://github.com/websockets/ws) | JavaScript | [00c425e](https://github.com/websockets/ws/commit/00c425ec77993773d823f018f64a5c44e17023ff) | | [Advisory](https://github.com/websockets/ws/security/advisories/GHSA-6fc8-4gx4-v693) |
| [CVE-2021-33587](https://nvd.nist.gov/vuln/detail/CVE-2021-33587) | [css-what](https://github.com/fb55/css-what) | JavaScript | [4cdaacf](https://github.com/fb55/css-what/commit/4cdaacfd0d4b6fd00614be030da0dea6c2994655) | | |
| [CVE-2021-33503](https://snyk.io/vuln/SNYK-PYTHON-URLIB3-1298661) | [urllib3](https://github.com/urllib3/urllib3) | Python | [2d4a3fe](https://github.com/urllib3/urllib3/commit/2d4a3fee6de2fa45eb82169361918f759269b4ec) | | [Advisory](https://github.com/urllib3/urllib3/security/advisories/GHSA-q2q7-5pp4-w6pg) |
| [CVE-2020-1920](https://nvd.nist.gov/vuln/detail/CVE-2020-1920) | [react-native](https://github.com/facebook/react-native) | JavaScript | [ca09ae8](https://github.com/facebook/react-native/commit/ca09ae82715e33c9ac77b3fa55495cf84ba891c7) | | [Advisory](https://securitylab.github.com/advisories/GHSL-2020-293-redos-react-native/) |
| [CVE-2020-5236](https://nvd.nist.gov/vuln/detail/CVE-2020-5236) | [waitress](https://github.com/Pylons/waitress) | Python | [6e46f9e](https://github.com/Pylons/waitress/commit/6e46f9e3f014d64dd7d1e258eaf626e39870ee1f) | | [Advisory](https://github.com/Pylons/waitress/security/advisories/GHSA-73m2-3pwg-5fgc) |
| [CVE-2020-5243](https://nvd.nist.gov/vuln/detail/CVE-2020-5243) | [uap-core](https://github.com/ua-parser/uap-core) | JavaScript | [0afd61e](https://github.com/ua-parser/uap-core/commit/0afd61ed85396a3b5316f18bfd1edfaadf8e88e1) | | [Advisory](https://github.com/ua-parser/uap-core/security/advisories/GHSA-cmcx-xhr8-3w9p) |
| [CVE-2020-6817](https://snyk.io/vuln/SNYK-PYTHON-BLEACH-561754) | [bleach](https://github.com/mozilla/bleach) | Python | [d6018f2](https://github.com/mozilla/bleach/commit/d6018f2539d271963c3e7f54f36ef11900363c69) | [Mozilla issue](https://bugzilla.mozilla.org/show_bug.cgi?id=1623633) | [Advisory](https://github.com/mozilla/bleach/security/advisories/GHSA-vqhp-cxgc-6wmm) |
| [CVE-2020-7661](https://nvd.nist.gov/vuln/detail/CVE-2020-7661) | [url-regex](https://github.com/kevva/url-regex) | JavaScript | [Fork PR](https://github.com/418sec/url-regex/pull/1/files) | | |
| [CVE-2020-7662](https://nvd.nist.gov/vuln/detail/CVE-2020-7662) | [faye websocket-extensions](https://github.com/faye/websocket-extensions-node) | JavaScript | [29496f6](https://github.com/faye/websocket-extensions-node/commit/29496f6838bfadfe5a2f85dff33ed0ba33873237) |  | [Advisory](https://github.com/faye/websocket-extensions-node/security/advisories/GHSA-g78m-2chm-r7qv) |
| [CVE-2020-7733](https://nvd.nist.gov/vuln/detail/CVE-2020-7733) | [ua-parser-js](https://github.com/faisalman/ua-parser-js) | JavaScript | [233d3ba](https://github.com/faisalman/ua-parser-js/commit/233d3bae22a795153a7e6638887ce159c63e557d) | | |
| [CVE-2020-7754](https://nvd.nist.gov/vuln/detail/CVE-2020-7754) | [npm-user-validate](https://github.com/npm/npm-user-validate) | JavaScript | [PR #15](https://github.com/npm/npm-user-validate/pull/15/files) | | [Advisory](https://github.com/npm/npm-user-validate/security/advisories/GHSA-xgh6-85xh-479p) |
| [CVE-2020-7755](https://nvd.nist.gov/vuln/detail/CVE-2020-7755) | [dat.gui](https://github.com/dataarts/dat.gui) | JavaScript | [PR #279](https://github.com/dataarts/dat.gui/pull/279/files) | [Issue #278](https://github.com/dataarts/dat.gui/issues/278) | |
| [CVE-2020-7760](https://nvd.nist.gov/vuln/detail/CVE-2020-7760) | [codemirror](https://github.com/codemirror/CodeMirror) | JavaScript | [55d0333](https://github.com/codemirror/CodeMirror/commit/55d0333907117c9231ffdf555ae8824705993bbb) | | |
| [CVE-2020-7761](https://nvd.nist.gov/vuln/detail/CVE-2020-7761) | [kafe](https://github.com/absolunet/kafe) | JavaScript | [c644c79](https://github.com/absolunet/kafe/commit/c644c798bfcdc1b0bbb1f0ca59e2e2664ff3fdd0) | | |
| [CVE-2020-7793](https://nvd.nist.gov/vuln/detail/CVE-2020-7793) | [ua-parser-js](https://github.com/faisalman/ua-parser-js) | JavaScript | [6d1f26d](https://github.com/faisalman/ua-parser-js/commit/6d1f26df051ba681463ef109d36c9cf0f7e32b18) | | |
| [CVE-2020-8492](https://nvd.nist.gov/vuln/detail/CVE-2020-8492) | [urllib](https://docs.python.org/3/library/urllib.request.html#module-urllib.request) | Python | [PR #18284](https://github.com/python/cpython/pull/18284) |  |  |
| [CVE-2020-13333](https://nvd.nist.gov/vuln/detail/CVE-2020-13333) | [GitLab](https://gitlab.com/gitlab-org/gitlab) | Ruby | [2e39d006](https://gitlab.com/gitlab-org/gitlab/-/commit/2e39d006cc0171301fb92870920f285afa5bc199) [ad6de575](https://gitlab.com/gitlab-org/gitlab/-/commit/ad6de575fcfba4a3388c7daf9609f591680e67e4) |  |  |
| [CVE-2020-26256](https://nvd.nist.gov/vuln/detail/CVE-2020-26256) | [fast-csv](https://github.com/C2FO/fast-csv) | JavaScript | [4bbd39f](https://github.com/C2FO/fast-csv/commit/4bbd39f26a8cd7382151ab4f5fb102234b2f829e) | [Semmle query](https://lgtm.com/query/8609731774537641779/) | [Advisory](https://github.com/C2FO/fast-csv/security/advisories/GHSA-8cv5-p934-3hwp) |
| [CVE-2020-28493](https://nvd.nist.gov/vuln/detail/CVE-2020-28493) | [Jinja2](https://github.com/pallets/jinja) | Python | [PR #1343](https://github.com/pallets/jinja/pull/1343/files) |  |  |
| [CVE-2020-28496](https://nvd.nist.gov/vuln/detail/CVE-2020-28496) | [three](https://github.com/mrdoob/three.js) | JavaScript | [PR #21143](https://github.com/mrdoob/three.js/pull/21143/files) | [Issue #21132](https://github.com/mrdoob/three.js/issues/21132) | |
| [CVE-2020-28469](https://nvd.nist.gov/vuln/detail/CVE-2020-28469) | [glob-parent](https://github.com/gulpjs/glob-parent) | JavaScript | [PR #36](https://github.com/gulpjs/glob-parent/pull/36/files) | [Issue #32](https://github.com/gulpjs/glob-parent/issues/32) | |
| [CVE-2020-28500](https://nvd.nist.gov/vuln/detail/CVE-2020-28500) | [lodash](https://github.com/lodash/lodash) | JavaScript | [PR #5065](https://github.com/lodash/lodash/pull/5065/files) | | |
| [CVE-2020-28501](https://nvd.nist.gov/vuln/detail/CVE-2020-28501) | [es6-crawler-detect](https://github.com/JefferyHus/es6-crawler-detect) | JavaScript | [PR #27](https://github.com/JefferyHus/es6-crawler-detect/pull/27/files) | | |
| [CVE-2020-29651](https://nvd.nist.gov/vuln/detail/CVE-2020-29651) | [py](https://github.com/pytest-dev/py) | Python | [PR #257](https://github.com/pytest-dev/py/pull/257/files) | [Issue #256](https://github.com/pytest-dev/py/issues/256) | |
| [CVE-2020-36066](https://nvd.nist.gov/vuln/detail/CVE-2020-36066) | [gjson](https://github.com/tidwall/gjson) | Go | [9f58baa](https://github.com/tidwall/gjson/commit/9f58baa7a613f89dfdc764c39e47fd3a15606153) [c2f5341](https://github.com/tidwall/match/commit/c2f534168b739a7ec1821a33839fb2f029f26bbc) | [Issue #195](https://github.com/tidwall/gjson/issues/195) | |
| [CVE-2018-20164](https://nvd.nist.gov/vuln/detail/CVE-2018-20164) | [uap-core](https://github.com/ua-parser/uap-core) | JavaScript | [947f80b](https://github.com/ua-parser/uap-php/commit/947f80b39130c83a3d1c75900ac1b58828ed8aef) | [Issue #332](https://github.com/ua-parser/uap-core/issues/332) | |
| [CVE-2017-15010](https://nvd.nist.gov/vuln/detail/CVE-2017-15010) | [tough-cookie](https://github.com/salesforce/tough-cookie) | JavaScript | [PR #97](https://github.com/salesforce/tough-cookie/pull/97) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-though-cookie.js) |  |
| [CVE-2017-16098](https://nvd.nist.gov/vuln/detail/CVE-2017-16098) | [charset](https://github.com/node-modules/charset) | JavaScript | [PR #11](https://github.com/node-modules/charset/pull/11) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-charset.js) | |
| [CVE-2017-16100](https://nvd.nist.gov/vuln/detail/CVE-2017-16100) | [dns-sync](https://github.com/skoranga/node-dns-sync) | JavaScript | [Fork PR](https://github.com/418sec/node-dns-sync/pull/1) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-dns-sync.js) | |
| [CVE-2017-16113](https://nvd.nist.gov/vuln/detail/CVE-2017-16113) | [parsejson](https://github.com/galkn/parsejson) | JavaScript | [Issue #4](https://github.com/galkn/parsejson/issues/4) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-parsejson.js) | [Advisory](https://github.com/advisories/GHSA-q75g-2496-mxpp) |
| [CVE-2017-16114](https://nvd.nist.gov/vuln/detail/CVE-2017-16114) | [marked](https://github.com/markedjs/marked) | JavaScript | [PR #945](https://github.com/markedjs/marked/pull/945) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-marked.js) | |
| [CVE-2017-16115](https://nvd.nist.gov/vuln/detail/CVE-2017-16115) | [timespan](https://github.com/indexzero/TimeSpan.js) | JavaScript | [Fork PR](https://github.com/418sec/TimeSpan.js/pull/1/files) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-timespan.js) | |
| [CVE-2017-16116](https://nvd.nist.gov/vuln/detail/CVE-2017-16116) | [string](https://github.com/jprichardson/string.js) | JavaScript | [PR #217](https://github.com/jprichardson/string.js/pull/217) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-string.js) | |
| [CVE-2017-16117](https://nvd.nist.gov/vuln/detail/CVE-2017-16117) | [slug](https://github.com/dodo/node-slug) | JavaScript | [PR #91](https://github.com/dodo/node-slug/pull/91) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-slug.js) |  |
| [CVE-2017-16137](https://nvd.nist.gov/vuln/detail/CVE-2017-16137) | [debug](https://www.npmjs.com/package/debug) | JavaScript | [PR #504](https://github.com/visionmedia/debug/pull/504) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-debug.js) | [Advisory](https://github.com/advisories/GHSA-gxpj-cx7g-858c) |
| [CVE-2017-16138](https://nvd.nist.gov/vuln/detail/CVE-2017-16138) | [mime](https://github.com/broofa/mime) | JavaScript | [Issue #167](https://github.com/broofa/mime/issues/167) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-mime.js) | [Advisory](https://github.com/advisories/GHSA-wrvr-8mpx-r7pp) |
| [CVE-2017-18214](https://nvd.nist.gov/vuln/detail/CVE-2017-18214) | [moment](https://github.com/moment/moment) | JavaScript | [PR #4326](https://github.com/moment/moment/pull/4326/files) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-moment.js) | |
| [CVE-2016-4055](https://nvd.nist.gov/vuln/detail/CVE-2016-4055) | [moment](https://github.com/moment/moment) | JavaScript | [PR #2939](https://github.com/moment/moment/pull/2939/files) | [Issue #2936](https://github.com/moment/moment/issues/2936) | |
| [CVE-2016-10527](https://nvd.nist.gov/vuln/detail/CVE-2016-10527) | [riot compiler](https://github.com/riot/compiler) | JavaScript | [c033d2c](https://github.com/riot/compiler/commit/c033d2c63c06fafdaf8b2cdac918c408e8c29166) [783521c](https://github.com/riot/compiler/commit/783521c0aec7dad07040371fef3dbfba0b7a8df9) | [Related Issue](https://github.com/riot/riot/issues/1511) |  |
| [CVE-2016-10540](https://nvd.nist.gov/vuln/detail/CVE-2016-10540) | [minimatch](https://github.com/isaacs/minimatch) | JavaScript | [6944abf](https://github.com/isaacs/minimatch/commit/6944abf9e0694bd22fd9dad293faa40c2bc8a955) | | |
| [CVE-2014-3538](https://nvd.nist.gov/vuln/detail/CVE-2014-3538) | [file](https://github.com/file/file) | C | [4a284c8](https://github.com/file/file/commit/4a284c89d6ef11aca34da65da7d673050a5ea320) [71a8b6c](https://github.com/file/file/commit/71a8b6c0d758acb0f73e2e51421a711b5e9d6668) |  |  |
| [npm:underscore.string:20170908](https://snyk.io/vuln/npm:underscore.string:20170908) | [underscore.string](https://github.com/esamattis/underscore.string) | JavaScript | [PR #517](https://github.com/esamattis/underscore.string/pull/517) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-underscore-string.js) |  |
| [npm:mobile-detect:20170907](https://snyk.io/vuln/npm:mobile-detect:20170907)  | [mobile-detect](https://github.com/hgoebl/mobile-detect.js) | JavaScript | [7222f6e](https://github.com/hgoebl/mobile-detect.js/commit/7222f6e75cf8cd90e1dc53e445716203eaf79d8a) | [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-mobile-detect.js) | |
| [SNYK-JS-ISMOBILEJS-72624](https://snyk.io/vuln/SNYK-JS-ISMOBILEJS-72624) | [ismobilejs](https://github.com/kaimallea/isMobile) | JavaScript | [PR #77](https://github.com/kaimallea/isMobile/pull/77) | [Issue #66](https://github.com/kaimallea/isMobile/issues/66) [PoC](https://github.com/sola-da/ReDoS-vulnerabilities/blob/master/test-ismobilejs.js) | |

------

## <a name="ReDoS_Tools"></a>ReDoS Tools

To Do: Compare these tools against the real world CVEs listed above to find the
strengths and weaknesses of each tool. Or is there a "best" tool?

- https://github.com/doyensec/regexploit (last commit in 2021)
- https://www.regexbuddy.com/debug.html (last updated in 2021)
- https://github.com/jkutner/saferegex (last commit in 2020)
- https://github.com/n4o847/seccamp-redos (last commit in 2020)
- https://github.com/NicolaasWeideman/RegexStaticAnalysis (last commit in 2020)
- https://github.com/davisjam/vuln-regex-detector (last commit in 2019)
- https://github.com/gagyibenedek/ReDoS-checker (last commit in 2018)
- https://github.com/jagracey/RegEx-DoS (last commit in 2016)
- https://github.com/olivo/redos-detector (last commit in 2016)
- https://www.cs.bham.ac.uk/~hxt/research/rxxr.shtml (last updated in 2013)

------

## <a name="ReDoS_Expressions"></a>ReDoS Vulnerable Expressions Lists
- https://owasp.org/www-community/OWASP_Validation_Regex_Repository
- https://github.com/EnDe/ReDoS/blob/master/ReDoS.txt
