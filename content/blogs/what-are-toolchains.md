---
title: What are toolchains and what is their significance?
author: Aditi Shinde
date: 2025-05-14
excerpt: >
  Toolchains are a significant part of a software development process, the toolchain is a chain which binds hardware to the software with the help of a set of tools present in it, in this blog we will discuss about how the toolchains play an important role in the software development part.
image: https://i.pinimg.com/736x/30/70/b8/3070b8406ab06d001445f0ac62b30c9e.jpg
---

## Preface

Every computer contains multiple components in it which are responsible to perform specific tasks.  
There are 7 main components of a computer:


<div align="center">

  1. Input devices
  2. Output devices
  3. Storage devices
  4. Motherboard
  5. Bus
  6. Microprocessor
  7. Math co-processor

</div>

Keyboard and mouse come under the input devices, in which the keyboard is considered a standard input device.  
Whereas console and printer are considered output devices, in which the console is a standard output device.



## The Problem

One of the biggest pain points with using a monorepo in a React Native project was the **Metro bundler**. Metro is the bundler used by React Native to package and serve JavaScript bundles during development. Unfortunately, Metro wasn’t designed with monorepos in mind, and we encountered several issues related to caching, performance, and file watching.

Here’s a list of the most significant problems we faced:

- **Metro Bundler Issues**: 
  Metro bundler’s caching mechanism didn't play well with the shared `node_modules` folder. It caused unpredictable build failures and long startup times.
  
- **Shared Node Modules**:
  Having multiple React Native apps and packages sharing the same `node_modules` directory meant that incompatible versions of dependencies could easily break the build.

- **Development Cycle Slowness**:
  The complexity of handling multiple apps, dependencies, and node modules within the same repo led to slower development cycles. We constantly found ourselves fighting with build issues and dependency version mismatches.

## Solution

After experimenting with a monorepo setup for a few months, we decided to break our project into separate repositories for each application. This allowed us to resolve dependency versioning issues and significantly improve the speed of our development cycles.

We also started using **Lerna** and **Yarn Workspaces** to help manage shared packages, which made it easier to handle common dependencies across projects.

## Conclusion

Monorepos can offer some great benefits for code sharing and dependency management, but they’re not always the best solution, especially when working with React Native. If you’re considering a monorepo for your next project, be prepared for the challenges that come with it — and know when it might be better to split things up.

Feel free to share your thoughts or ask questions in the comments below!
---

