---
layout: splash
header:
  overlay_color: "#5e616c"
  overlay_image: splash.png
  actions:
      - label: "GITHUB"
        url: "https://github.com/kwiecinski"
excerpt: "Welcome to my website. You'll find here projects, documentation, and other hobby-related things. <br> Feel free to check out my GitHub as well"

feature_row:
  - image_path: /images/electronics.jpg
    title: "Electronics"
    excerpt: "Electronics projects from concept to PCB designs, mechanical and microcontroller programming"
    btn_class: "btn--primary"
    btn_label: "Learn more"
    url: "/pages/electronics/"
  - image_path: /images/mechanical.jpg
    title: "Mechanical"
    excerpt: "Mechanical projects mainly involving metalworking, cutting, welding."
    btn_class: "btn--primary"
    btn_label: "Learn more"
    url: "/pages/mechanical/"
  - image_path: /images/programming.jpg
    title: "Programming"
    excerpt: "Programming espacially non-embedded stuff and tutorials"
    btn_class: "btn--primary"
    btn_label: "Learn more"
    url: "/pages/programming/"
  - image_path: /images/repair.webp
    title: "Repairs"
    excerpt: "Repairs I made for me and for other people"
    btn_class: "btn--primary"
    btn_label: "Learn more"
    url: "/pages/repairs/"
---
{% include feature_row %}