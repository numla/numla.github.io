# Oseledets group website

# Contributing

## Add an author

In order to add author/speker to the site you need to modify file `/_data/authors.yml`. 

```yaml
dmerkulov:
  short_name: dmerkulov
  name: Daniil Merkulov
  position: PhD student
  affilation: Skoltech
  links:
    - title: Homepage
      url: https://merkulov.top
      icon: fas fa-home
    - title: Mail 
      url: mailto:daniil.merkulov@skolkovotech.ru
      icon: fas fa-envelope
    - title: Google Scholar
      url: https://scholar.google.com/citations?user=BkxI36gAAAAJ&hl=en
      icon: ai ai-google-scholar-square
    - title: Twitter
      url: https://twitter.com/danya_merkulov
      icon: fab fa-twitter
  picture: /assets/pictures/dmerkulov.jpg
```

Note, that:
* All these fields are neccessary
* `short_name` uses the following format: first letter of the first name + family name. For example, John Duo -> `jduo`. However, the `short_name`, which is going to be added should be unique. 
* `name` stands for the full name of the person. Begins with a capital letter.
* `position` stands for the current position of the person (it might be MSc student, BSc student, Researcher, PhD student, Assistant Professor and etc.). Begins with a capital letter.
* `affilation` stands for the current affilation of the person - name of the university or company.
* `links` stands for the contact information of the person. Should contain at least one link. Each link contains 3 field: `title`, `url`, and `icon`. The latter field stands for the id of the icon from the [Font Awesome](https://fontawesome.com/icons?d=gallery) icons collection. For some scientific icons one can also use id of icons from [academicons](https://jpswalsh.github.io/academicons/). The most simple way to fill it is just to copy the entire `links` field from some author, that has target links and just change the url. Try to avoid using of huge amount of links.
* `picture` stands for the photo of the person. All the photos of authors lie in the `/assets/pictures/` folder in bitmap format. Try to avoid using rectangular photo - keeping it square produces more uniform experience.

## Add a seminar talk

In order to add seminar talk you need to add `YYYY-MM-DD-TALK_NAME.md` file to the `/_posts` folder. For example, file `/_posts/2019-06-06-matrix_exp.md` has the following content:

```yaml
---
author: akatrutsa
title:  "Shift optimization for matrix exponential computing"
presentation: "/assets/presentations/shift_matexp_seminar_presentation.pdf"
tags: 
  - Matrix Factorization
  - Krylov Methods
  - Optimization
---
```

where you only need to specify author's short name from the `/_data/authors.yml` file, title of the presentation/talk and path to the `.pdf` file. All presentations should be stored at `/assets/presentations/` folder.

Also, you can include as many tags as you want, but before setting the tags to the talk, it is better to look at the [existing tags](https://numla.github.io/tags/), probably, you can find the similar one, which is already exists. All the words in tag should begins with a capital letter.

![](/images/tags.png)

## Add a publication

In order to add publication you need to add `publication_title.md` file to the `/_publications` folder. For example, file `/_publications/sad_points.md` has the following content:

```yaml
---
type: publication
title: Empirical study of extreme overfitting points of neural networks
date: 2020-02-21 00:00:00
authors:
  - dmerkulov
  - ioseledets
image: 
  path: /images/ResNet_CIFAR10.svg
bibtex: https://link.springer.com/article/10.1134/S1064226919120118#citeasMPgo&hl=en
arxiv: https://arxiv.org/abs/1906.06295
---
```

* Any publication should contain an image, which illustrates the idea of the paper. 
* Images are typically stored at `/images/` folder.
* You can add `bibtex` button to your paper for the simplicity of citing it. This field should include url to any resource, that contains this citation in a bibtex format.
* `authors` field contains authors of the paper
* You can also give a link to the arxiv as `arxiv` button.

If you want to describe the idea of the paper in more details, you can write anything in markdown format after the front matter in the same file.

## Add a course

In order to add course you need to add `course_title.md` file to the `/_courses` folder. For example, file `/_courses/terminal.md` has the following content:

```yaml
---
type: course
title: ISP Computing life with linux
image: 
  path: /images/terminal.jpg
repo: https://bitbucket.org/matseralex/isp_computing_life_with_linux/src/master/
authors:
  - smatveev
---
```

* Any course should contain an image, which illustrates any idea of the course. 
* Images are typically stored at `/images/` folder.
* You can add `repo` button with the url of the course' repo.
* You can add `outer_link` button with the url of the course' page.

If you want to describe the course in more details, you can write anything in markdown format after the front matter in the same file.