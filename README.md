# 프로젝트 Build 과정

## 사전 설치

프로젝트를 시작하기 전, 아래와 같이 github blog를 위한 프로그램을 설치 과정을 진행했다.

- 노트북의 OS가 window이기 때문에, Git에 접근하기 위한 Git bash 설치 후 Token으로 로그인
- Ruby 설치


## Jekyll의 기본 활용

Github page의 기초를 만들기 위해, Git에 미리 만들어놨던 repository를 clone하였다.

repository에 Jekyll을 설치하였고, Git 원격 repository에 Push하기 전, 

``` jekyll serve``` 명령어를 통해 local에서 잘 작동하는지 확인하였다. 

이후 _config.yml을 간단하게 수정하여 dummy data를 내 정보로 교체하였고,  

_post directory에 Post Upload를 테스트하기 위한 게시글을 작성 한 뒤, Git에 Push했다.

## Theme 변경

#####  Trouble 1

Jekyll의 Theme을 변경하기 위해 "https://jekyllthemes.io" 사이트에서 검색을 하다가 

https://github.com/CloudCannon/hydra-jekyll-template

해당 템플릿으로 결정을 한 뒤, 상위 directory에 clone을 하고 _post directory를 제외한 나머지 파일들을 붙여넣었다.

하지만 Push를 하려고 시도를 했을 때 error가 발생했었고, 확인을 해보니 theme를 clone하여 

remote repository가 나의 repository가 아니라, hydra의 repositoy로 되어있었다.

따라서

``` 

git remote remove origin

git remote add origin 원격 repository

```

와 같은 명령어를 통해 remote reposity를 변경하고, push를 하였다.


#####  Trouble 2














## Usage

Lanyon is a theme built on top of [Poole](https://github.com/poole/poole), which provides a fully furnished Jekyll setup—just download and start the Jekyll server. See [the Poole usage guidelines](https://github.com/poole/poole#usage) for how to install and use Jekyll.


## Options

Lanyon includes some customizable options, typically applied via classes on the `<body>` element.


### Sidebar menu

Create a list of nav links in the sidebar by assigning each Jekyll page the correct layout in the page's [front-matter](http://jekyllrb.com/docs/frontmatter/).

```
---
layout: page
title: About
---
```

**Why require a specific layout?** Jekyll will return *all* pages, including the `atom.xml`, and with an alphabetical sort order. To ensure the first link is *Home*, we exclude the `index.html` page from this list by specifying the `page` layout.


### Themes

Lanyon ships with eight optional themes based on the [base16 color scheme](https://github.com/chriskempson/base16). Apply a theme to change the color scheme (mostly applies to sidebar and links).

![Lanyon with red theme](https://f.cloud.github.com/assets/98681/1825270/be065110-71b0-11e3-9ed8-9b8de753a4af.png)
![Lanyon with red theme and open sidebar](https://f.cloud.github.com/assets/98681/1825269/be05ec20-71b0-11e3-91ea-a9138ef07186.png)

There are eight themes available at this time.

![Available theme classes](https://f.cloud.github.com/assets/98681/1817044/e5b0ec06-6f68-11e3-83d7-acd1942797a1.png)

To use a theme, add any one of the available theme classes to the `<body>` element in the `default.html` layout, like so:

```html
<body class="theme-base-08">
  ...
</body>
```

To create your own theme, look to the Themes section of [included CSS file](https://github.com/poole/lanyon/blob/master/public/css/lanyon.css). Copy any existing theme (they're only a few lines of CSS), rename it, and change the provided colors.


### Reverse layout

![Lanyon with reverse layout](https://f.cloud.github.com/assets/98681/1825265/be03f2e4-71b0-11e3-89f1-360705524495.png)
![Lanyon with reverse layout and open sidebar](https://f.cloud.github.com/assets/98681/1825268/be056174-71b0-11e3-88c8-5055bca4307f.png)

Reverse the page orientation with a single class.

```html
<body class="layout-reverse">
  ...
</body>
```


### Sidebar overlay instead of push

Make the sidebar overlap the viewport content with a single class:

```html
<body class="sidebar-overlay">
  ...
</body>
```

This will keep the content stationary and slide in the sidebar over the side content. It also adds a `box-shadow` based outline to the toggle for contrast against backgrounds, as well as a `box-shadow` on the sidebar for depth.

It's also available for a reversed layout when you add both classes:

```html
<body class="layout-reverse sidebar-overlay">
  ...
</body>
```

### Sidebar open on page load

Show an open sidebar on page load by modifying the `<input>` tag within the `sidebar.html` layout to add the `checked` boolean attribute:

```html
<input type="checkbox" class="sidebar-checkbox" id="sidebar-checkbox" checked>
```

Using Liquid you can also conditionally show the sidebar open on a per-page basis. For example, here's how you could have it open on the homepage only:

```html
<input type="checkbox" class="sidebar-checkbox" id="sidebar-checkbox" {% if page.title =="Home" %}checked{% endif %}>
```

## Development

Lanyon has two branches, but only one is used for active development.

- `master` for development.  **All pull requests should be to submitted against `master`.**
- `gh-pages` for our hosted site, which includes our analytics tracking code. **Please avoid using this branch.**


## Author

**Mark Otto**
- <https://github.com/mdo>
- <https://twitter.com/mdo>


## License

Open sourced under the [MIT license](LICENSE.md).

<3
