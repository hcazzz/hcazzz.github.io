---
layout: essay
type: essay
title: "The Web Design Beast"
# All dates must be YYYY-MM-DD format!
date: 2023-10-04
published: true
labels:
  - Web Design
  - Learning
  - HTML
  - CSS
  - Bootstrap

---
## Web Design: A Nightmare
Do you ever sit there and reminisce about your childhood, waking up early in the morning for Christmas, excited to open  presents? Or maybe you were just excited to get home from school to play video games with your friends. I don’t do this often, but after being slapped in the face with how challenging HTML and CSS can be, I find myself missing those simple times. Learning HTML and CSS was a bit of a nightmare, and the sad part is that I’m not even close to being proficient.

Moving on, there's a whole new beast that appeared - <a href="https://getbootstrap.com/docs/5.3/getting-started/introduction/"> Bootstrap<a/>. Now, don’t get me wrong; Bootstrap is not as daunting as the aforementioned technologies, but it still presents its challenges. However, learning new things is always exciting, so that's one thing to be happy about. Besides that, I've found that Bootstrap has proven to be quite beneficial in my short time learning it. Most websites can be easily recreated with Bootstrap, although the same can be said for raw CSS and HTML.

What really sets Bootstrap apart from raw CSS is its quick and easy classes that offer great UI design in less than half the time it would take with CSS. Using Bootstrap, you can easily code up a decent-looking navbar without worrying about different padding and styles, all in just a few minutes. Of course, if one were to be super proficient with CSS, this would be a walk in the park. However, I am not that person, and I think it’s safe to say that I will never be.

If I've learned anything in these past few weeks, it’s that I don’t want to be a UI designer or frontend developer ever. Maybe I’m exaggerating a little, but I find backend work a lot easier than frontend work. But this doesn’t mean I should put off learning HTML, CSS, or Bootstrap. These three technologies are definitely useful to know, and I will definitely keep learning more about them.

## Why Use it?
So, why Bootstrap? What’s the point of learning it and becoming proficient at it instead of just getting good at CSS? Well, it doesn’t have to be one or the other. Bootstrap offers quick and easy design options with its extensive library of classes that can be applied to do pretty much anything. Some things may take 3-4 lines of CSS, but with Bootstrap, you can apply it all by just giving the element the Bootstrap class name. However, it’s not always black and white; you may find yourself needing to change a specific style, which can be done with a bit of CSS.

So, if you’re planning to learn Bootstrap but not CSS, I’d advise against it. It would be far more beneficial to become more proficient at CSS, especially if you want to be a frontend developer. However, for someone like me, who absolutely hates design, Bootstrap and a little bit of CSS is the way to go. Being forced to remember a bunch of little details like how to center a div or random styling components does not sound like fun to me, and I’d much rather have Bootstrap do the heavy lifting for me.

## Designing Made Simple
As mentioned before, Bootstrap makes designing a website a lot easier. With its extensive library of classes, you can easily create a website that looks like it was designed by a professional. However, this doesn’t mean you can’t do the same with CSS. It’s just a lot easier to do it with Bootstrap. 

If you wanted to take it a step further, you could use <a href="https://react-bootstrap.github.io/">react-bootstrap</a>
, which is a library of Bootstrap components that can be used in React. This is what I used to create my final project. It was a lot easier to create a website using react-bootstrap than it was to use raw CSS. If you want more information you can check out my final project using react-bootstrap here, <a href="https://the-manoa-marketplace.github.io/uh-marketplace.github.io/">UH Marketplace</a>.

## Examples

Now that I’ve talked about different ways to do web design, let's look at some examples comparing UI frameworks to raw CSS. If you wanted to create a navbar, you could do it with CSS, but it would take a lot longer than if you were to use Bootstrap. Here is an example of a navbar using react-bootstrap.

```javascript
import React from 'react';
import { Navbar, Nav } from 'react-bootstrap';

const SimpleNavbar = () => {
  return (
    <Navbar bg="light" expand="lg">
      <Navbar.Brand href="#home">Your Logo</Navbar.Brand>
      <Navbar.Toggle aria-controls="basic-navbar-nav" />
      <Navbar.Collapse id="basic-navbar-nav">
        <Nav className="ml-auto">
          <Nav.Link href="#home">Home</Nav.Link>
          <Nav.Link href="#about">About</Nav.Link>
          <Nav.Link href="#services">Services</Nav.Link>
          <Nav.Link href="#contact">Contact</Nav.Link>
        </Nav>
      </Navbar.Collapse>
    </Navbar>
  );
};

export default SimpleNavbar;
```

Here is an example using regular Bootstrap

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Bootstrap Navbar</title>
  <!-- Bootstrap CSS -->
  <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css">
</head>
<body>

<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <a class="navbar-brand" href="#">Your Logo</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNav">
    <ul class="navbar-nav ml-auto">
      <li class="nav-item active">
        <a class="nav-link" href="#">Home</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">About</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Services</a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#">Contact</a>
      </li>
    </ul>
  </div>
</nav>

<!-- Bootstrap JS and jQuery (required for Bootstrap) -->
<script src="https://code.jquery.com/jquery-3.5.1.slim.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js"></script>
<script src="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>

</body>
</html>
```

And here is an example of a navbar using raw CSS and HTML 

``` html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Simple Navbar</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

<nav class="navbar">
  <div class="navbar-logo">
    Your Logo
  </div>
  <ul class="navbar-nav">
    <li class="nav-item"><a href="#home">Home</a></li>
    <li class="nav-item"><a href="#about">About</a></li>
    <li class="nav-item"><a href="#services">Services</a></li>
    <li class="nav-item"><a href="#contact">Contact</a></li>
  </ul>
</nav>

</body>
</html>
```

```css
body {
  margin: 0;
  font-family: Arial, sans-serif;
}

.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #f8f9fa;
  padding: 15px 20px;
}

.navbar-logo {
  font-weight: bold;
  font-size: 24px;
}

.navbar-nav {
  list-style: none;
  display: flex;
  margin: 0;
  padding: 0;
}

.nav-item {
  margin-left: 20px;
}

.nav-item a {
  text-decoration: none;
  color: #333;
  font-weight: bold;
  transition: color 0.3s ease-in-out;
}

.nav-item a:hover {
  color: #007bff;
}
```
As you can see, as you go down the list, more and more code gets added, in my personal opinion as a non UI designer, I would rather use Bootstrap or react-bootstrap. It's a lot easier to use and it's a lot faster to create a website. But that is subjective, some people may prefer to use raw CSS and HTML. Or maybe they may prefer a different UI framework like tailwind or material UI. It's all up to you and what you prefer.

