---
layout: post
title: Start With Electron
category: Technical
tags: Electron
description: Start With Electron
---

## [Electron官网](http://electron.atom.io/)

### [Electron Documentation](http://electron.atom.io/docs/v0.31.0/)

### Built on Electron

With Electron, creating a desktop application for your company or idea is easy.
 
Electron enables you to create desktop applications with pure JavaScript by providing a runtime with rich native APIs. You could see it as a variant of the io.js runtime which is focused on desktop applications instead of web servers.

This doesn't mean Electron is a JavaScript binding to GUI libraries. Instead, Electron uses web pages as its GUI, so you could also see it as a minimal Chromium browser, controlled by JavaScript.

Initially developed for GitHub's Atom editor, Electron has since been used to create applications by companies like Microsoft, Facebook, Slack, and Docker.

## Start with it 

Build cross platform desktop apps with web technologies , This is very magical and I will start to learn it!

### Main process

In Electron, the process that runs package.json's main script is called the main process. The script that runs in the main process can display a GUI by creating web pages.

### Renderer process

Since Electron uses Chromium for displaying web pages, Chromium's multi-process architecture is also used. Each web page in Electron runs in its own process, which is called the renderer process.

In normal browsers, web pages usually run in a sandboxed environment and are not allowed access to native resources. Electron users, however, have the power to use io.js APIs in web pages allowing lower level operating system interactions.

** Differences between main process and renderer process **

The main process creates web pages by creating BrowserWindow instances. Each BrowserWindow instance runs the web page in its own renderer process. When a BrowserWindow instance is destroyed, the corresponding renderer process is also terminated.

The main process manages all web pages and their corresponding renderer processes. Each renderer process is isolated and only cares about the web page running in it.

In web pages, it is not allowed to call native GUI related APIs because managing native GUI resources in web pages is very dangerous and it is easy to leak resources. If you want to perform GUI operations in a web page, the renderer process of the web page must communicate with the main process to request the main process perform those operations.

In Electron, we have provided the ipc module for communication between main process and renderer process. And there is also a remote module for RPC style communication.
