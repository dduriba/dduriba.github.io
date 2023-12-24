---
title:  "부트스트랩"
excerpt: "bootstrap"
categories: CSS
tag: [CSS, bootstrap]
toc: true
toc_label: "목록"
toc_icon: "bars"
toc_sticky: true
---

# quick start
{: .notice--warning .text-center}

```html
<!-- https://getbootstrap.com/docs/4.6/getting-started/introduction/ -->
<head>
    <!-- ... head contents -->
    <!-- bootstrap css 포함시키기 -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@4.6.2/dist/css/bootstrap.min.css" integrity="sha384-xOolHFLEh07PJGoPkLv1IbcEPTNtaed2xpHsD9ESMhqIYd0nLMwNLD69Npy4HI+N" crossorigin="anonymous">
    <!-- 사용자 정의 css는 최우선 적용을 위해 bootstrap css를 먼저 포함한 후에 포함시키기 -->
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <!-- ... body contents -->
    <!-- body 최하단에 bootstrap js 포함시키기 -->
    <!-- => 페이지가 로드될 때 JavaScript 파일을 다운로드하고 실행하는 동안 사용자가 페이지의 내용을 볼 수 있음 -->
    <!-- jQuery -->
    <script src="https://cdn.jsdelivr.net/npm/jquery@3.5.1/dist/jquery.slim.min.js" integrity="sha384-DfXdz2htPH0lsSSs5nCTpuj/zy4C+OGpamoFVy38MVBnE+IbbVYUew+OrCXaRkfj" crossorigin="anonymous"></script>
    <!-- Bootstrap Separate Popper -->
    <script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.1/dist/umd/popper.min.js" integrity="sha384-9/reFTGAW83EW2RDu2S0VKaIzap3H66lZH81PoYlFhbGU+6BZp6G7niu735Sk7lN" crossorigin="anonymous"></script>
    <!-- bootstrap -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@4.6.2/dist/js/bootstrap.min.js" integrity="sha384-+sLIOodYLS7CIrQpBjl+C7nPvqq+FbNUBDunl/OZv93DB7Ln/533i8e/mZXLi/P+" crossorigin="anonymous"></script>
</body>
```

# container
{: .notice--warning .text-center}

```html
<!-- https://getbootstrap.com/docs/4.6/layout/overview/ -->
<body>
    <!-- <div class="container-fluid"></div> -->
    <!-- <div class="container-sm"></div> -->
    <!-- <div class="container-md"></div> -->
    <!-- <div class="container-lg"></div> -->
    <!-- <div class="container-xl"></div> -->
    <div class="container">
        <h1>header</h1>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Officia corrupti illo vitae nulla rerum reprehenderit assumenda, explicabo temporibus dolor harum laboriosam, sint obcaecati optio libero et ex, ad quas corporis!
    </div>
</body>
```

# button, button group
{: .notice--warning .text-center}

```html
<!-- https://getbootstrap.com/docs/4.6/components/buttons/ -->
<!-- https://getbootstrap.com/docs/4.6/components/button-group/ -->
<body>
    <button type="button" class="btn btn-primary">Primary</button>
    <button type="button" class="btn btn-secondary">Secondary</button>
    <button type="button" class="btn btn-success">Success</button>

    <div class="btn-group">
        <button class="btn btn-warning">first</button>
        <button class="btn btn-warning">second</button>
        <button class="btn btn-warning">third</button>
    </div>
</body>
```

# typography, colors
{: .notice--warning .text-center}

```html
<!-- https://getbootstrap.com/docs/4.6/content/typography/ -->
<!-- https://getbootstrap.com/docs/4.6/utilities/colors/ -->
<body>
    <h1 class="display-1 text-center bg-info text-white">Display 1</h1>
    <blockquote class="blockquote text-center">
        <p class="mb-0">A well-known quote, contained in a blockquote element.</p>
    </blockquote>
</body>
```

# badge
{: .notice--warning .text-center}

```html
<!-- https://getbootstrap.com/docs/4.6/components/badge/ -->\
<body>
    <button class="btn btn-primary">Message <span class="badge badge-light">2</span></button>
</body>
```

# alert
{: .notice--warning .text-center}

```html
<!-- https://getbootstrap.com/docs/4.6/components/alerts/ -->
<body>
    <div class="alert alert-danger alert-dismissible fade show" role="alert">
        <h4 class="alert-heading">Warn!</h4>
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
        <button class="close" data-dismiss="alert" aria-label="Close">
            <span aria-hidden="true">&times;</span>
        </button>
    </div>
</body>
```

# grid
{: .notice--warning .text-center}

```html
<!-- https://getbootstrap.com/docs/4.6/layout/grid/ -->
<body>
    <!-- Grid -->
    <div class="row">
        <!-- total 12 units -->
        <div class="col bg-success">5 UNITS</div>
        <div class="col-2 bg-danger">2 UNITS</div>
        <div class="col bg-success">5 UNITS</div>
    </div>
    <!-- Responsive Grid -->
    <div class="row align-items-center">
        <div class="col-md-6 bg-success">Lorem ipsum dolor sit amet consectetur adipisicing elit.</div>
        <div class="col-md-6 bg-danger">Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste cupiditate maiores, alias ratione harum exercitationem quae magni quis molestiae excepturi. Hic quidem debitis et aliquid exercitationem repudiandae iusto ab obcaecati.</div>
    </div>
    <!-- Responsive Image Grid -->
    <div class="row">
        <div class="col-xl-4 col-md-6">
            <img class="img-fluid" src="https://gyumtriever.github.io/assets/images/avatar.png" alt="">
        </div>
        <div class="col-xl-4 col-md-6">
            <img class="img-fluid" src="https://gyumtriever.github.io/assets/images/avatar.png" alt="">
        </div>
        <div class="col-xl-4 col-md-6">
            <img class="img-fluid" src="https://gyumtriever.github.io/assets/images/avatar.png" alt="">
        </div>
    </div>
</body>
```

# form
{: .notice--warning .text-center}

```html
<!-- https://getbootstrap.com/docs/4.6/components/forms/ -->
<body>
<form action="#nowhere"> 
    <div class="form-row"> <!-- .form-row 빠른 자동완성 -->
        <div class="form-group col-md-6">
            <label for="email">Email</label>
            <input type="email" class="form-control" id="email" placeholder="Email">
        </div>
        <div class="form-group col-md-6">
            <label for="password">Password</label>
            <input type="password" class="form-control" id="password" placeholder="password">
        </div>
    </div>
    <div class="form-group">
        <label for="address">Street Address</label>
        <input type="text" class="form-control" id="address">
    </div>
    <div class="form-row"> 
        <div class="form-group col-md-6">
            <label for="city">City</label>
            <input type="text" class="form-control" id="city">
        </div>
        <div class="form-group col-md-3">
            <label for="state">State</label>
            <select class="form-control" name="state" id="state">
                <option value="AL">Alabama</option>
                <option value="AK">Alaska</option>
            </select>
        </div>
        <div class="form-group col-md-3">
            <label for="zip">Zip Code</label>
            <input type="text" class="form-control" id="zip">
        </div>
    </div>
    <div class="form-group">
        <div class="custom-control custom-checkbox">
            <input class="custom-control-input" type="checkbox" value="" id="tos">
            <label class="custom-control-label" for="tos">
                Sign me up
            </label>
        </div>
    </div>
    <button type="submit" class="btn btn-success">Register</button>
</form>
</body>
```

# navbar
{: .notice--warning .text-center}

```html
<!-- https://getbootstrap.com/docs/4.6/components/navbar/ -->
<body>
    <nav class="navbar navbar-expand-sm navbar-light bg-light fixed-top">
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" data-toggle="collapse" data-target="#expandme">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="expandme">
            <div class="navbar-nav">
                <a href="Home" class="nav-item nav-link">Home</a>
                <a href="Home" class="nav-item nav-link">About</a>
                <a href="Home" class="nav-item nav-link">Contact</a>
            </div>
            <form class="form-inline ml-auto">
                <input class="form-control mr-sm-2" type="search" placeholder="Search" aria-label="Search">
                <button class="btn btn-outline-success my-2 my-sm-0" type="submit">Search</button>
            </form>
        </div>
    </nav>
</body>
```

# icon
{: .notice--warning .text-center}

```html
<!-- https://icons.getbootstrap.com/ -->
<!-- https://fontawesome.com/icons -->
<body>
    <h1 class="display-1 text-primary">airplane <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" fill="currentColor" class="bi bi-airplane" viewBox="0 0 16 16">
        <path d="M6.428 1.151C6.708.591 7.213 0 8 0s1.292.592 1.572 1.151C9.861 1.73 10 2.431 10 3v3.691l5.17 2.585a1.5 1.5 0 0 1 .83 1.342V12a.5.5 0 0 1-.582.493l-5.507-.918-.375 2.253 1.318 1.318A.5.5 0 0 1 10.5 16h-5a.5.5 0 0 1-.354-.854l1.319-1.318-.376-2.253-5.507.918A.5.5 0 0 1 0 12v-1.382a1.5 1.5 0 0 1 .83-1.342L6 6.691V3c0-.568.14-1.271.428-1.849m.894.448C7.111 2.02 7 2.569 7 3v4a.5.5 0 0 1-.276.447l-5.448 2.724a.5.5 0 0 0-.276.447v.792l5.418-.903a.5.5 0 0 1 .575.41l.5 3a.5.5 0 0 1-.14.437L6.708 15h2.586l-.647-.646a.5.5 0 0 1-.14-.436l.5-3a.5.5 0 0 1 .576-.411L15 11.41v-.792a.5.5 0 0 0-.276-.447L9.276 7.447A.5.5 0 0 1 9 7V3c0-.432-.11-.979-.322-1.401C8.458 1.159 8.213 1 8 1c-.213 0-.458.158-.678.599"/>
    </svg></h1>
</body>
```

# input group
{: .notice--warning .text-center}

```html
<!-- https://getbootstrap.com/docs/4.6/components/input-group/ -->
<body>
    <div class="row">
        <div class="col-md-4">
            <div class="input-group">
                <div class="input-group-prepend">
                    <span class="input-group-text"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-search" viewBox="0 0 16 16">
                        <path d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001c.03.04.062.078.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1.007 1.007 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0"/>
                      </svg></span>
                </div>
                <input type="text" class="form-control" placeholder="Search">
            </div>
        </div>
    </div>
</body>
```