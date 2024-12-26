sourceforge.net 下载加速（中国）.js

Copyright (c) 2024 九欲

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
// ==UserScript==
// @name        sourceforge.net 下载加速（中国）
// @description 在sourceforge.net直接显示下载连接并替换为国内镜像进行加速
// @namespace   czyt
// @include     http*://sourceforge.net/*/files/*
// @version     1.5
// @grant       none
// @downloadURL https://update.greasyfork.org/scripts/440530/sourceforgenet%20%E4%B8%8B%E8%BD%BD%E5%8A%A0%E9%80%9F%EF%BC%88%E4%B8%AD%E5%9B%BD%EF%BC%89.user.js
// @updateURL https://update.greasyfork.org/scripts/440530/sourceforgenet%20%E4%B8%8B%E8%BD%BD%E5%8A%A0%E9%80%9F%EF%BC%88%E4%B8%AD%E5%9B%BD%EF%BC%89.meta.js
// ==/UserScript==

var href, links = document.querySelectorAll('a[href$="/download"]');
var mirrorHost = 'hole.czyt.tech/magic/https/udomain.dl.sourceforge.net/sourceforge/';

for (var i = 0, l = links.length; i < l; i++) {
    href = links[i].getAttribute("href").replace("sourceforge.net/projects/", mirrorHost).replace("/files/", "/").replace(/\/download$/, "");
    links[i].setAttribute("href", href);
}