---
layout: project
type: project
image: img/coding-tracker/codingTracker.png
title: "Coding Tracker"
date: 2023
published: true
labels:
  - C#
  - EF Core
  - SQLite
summary: "A simple C# console application that uses SQLite to store how long you code for"
---



This coding tracker project is a CRUD console application developed using C# that allows the user to track how long they code for. Upon startup the application should check if you have a SQLite database initialized and if not, it will create one. When adding a coding time, the user will be prompted to add the date and the time they started and the time they finished. From there the application will automatically store the amount of time they coded for in a neat table. 

This simple project was created to learn the basics of C# and SQLite. Below are some images on what the application looks like.

<div class="text-center p-4">
  <img width="500px" src="../img/coding-tracker/codingTimeMenu.png" class="img-thumbnail" >
  <img width="500px" src="../img/coding-tracker/codingTimeAdd.png" class="img-thumbnail" >
  <img width="500px" src="../img/coding-tracker/codingTimeUpdate.png" class="img-thumbnail" >
  <img width="500px" src="../img/coding-tracker/codingTimeDisplayAll.png" class="img-thumbnail" >
</div>



To view the source code you can visit: https://github.com/hcazzz/CodingTracker
