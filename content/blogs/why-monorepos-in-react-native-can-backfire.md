---
title: Why Monorepos in React Native Can Backfire
author: Aditi Shinde
date: 2025-03-15
excerpt: >
  Ran into major issues using a monorepo setup with React Native while contributing to RealDevSquad.
  Metro bundler, shared node_modules, and cleanup cycles made dev painful — here’s everything I learned.
image: https://i.pinimg.com/736x/47/69/31/476931c1333a226c179fd62fac248c31.jpg
---

## Introduction

Monorepos have become quite popular in recent years for managing multiple projects under a single repository. While they provide many advantages, such as easier dependency management and code sharing, they can also introduce some significant challenges, especially when working with complex frameworks like React Native.

In this blog post, I'll share my experience using a monorepo setup in a React Native project and discuss why it didn't work well for our team. 

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
