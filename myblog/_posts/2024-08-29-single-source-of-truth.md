---
title: Single source of truth
author: Sunhee Cho
date: 2024-09-17 09:33:00 +0800
categories: [Blogging, Demo]
tags: [typography]
pin: true
math: true
mermaid: true
image:
  path: /commons/devices-mockup.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Responsive rendering of Chirpy theme on multiple devices.
---

## What is Single source of truth?

Single source of truth(SSOT) is an approach of that data or information used through a project is aggregated and managed in a central repository. This ensures consistency, accuracy, and prevents data duplication or discrepancies.

## Example of a Single source of truth?

If we're using external API data and the API provider manages updates without notification, it can indeed be inefficient and potentially risky to maintain a local copy of that data in our database.
Because of

1. Data redundancy : storing the same data in multiple locations cna lead to inconsistencies and increased maintenance overhead
2. Potential for outdated data
3. Increased complexity : managing both local and external data source can add complexity to the project

## A bettter approach for a Single source of truth

1. Fetch data from the API as needed : only retrieve data required when it needed, rather than storing a complete copy. This ensures we always have the most up-to-date information
2. Implement caching : for frequently accessed data, we can use caching mechanisms to improve performance while minimizing the need for frequent API calls

## Reference

Wikipedia : https://en.wikipedia.org/wiki/Single_source_of_truth
