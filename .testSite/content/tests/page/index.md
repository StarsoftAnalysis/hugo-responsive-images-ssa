---
title: "Page Resources"
date: 2022-08-28T15:35:39-07:00
draft: false
resources: # for test 8 (metadata)
- src: test1.jpg
  title: Title set via metadata
  params: 
    alt: Alt set via metadata
image:
  renderHook: false
testImages:
- id: js-test1
  title: 1. Basic
  subtitle: Alt and title set
  params:
    alt: Test Image Alt
    title: Test Image Title
  tests:
    img:
      dataSizes: 'auto'
      alt: 'Test Image Alt'
      title: 'Test Image Title'
      dataSizes: 'auto'
      class: ['img-fluid', 'lazyloaded', lazyautosizes]
    source: 
      types: ['webp', 'jpeg']
      dataWidths: ['600w', '900w', '1300w']
- id: js-test2
  title: 2. Formats
  subtitle: original (jpeg), png, webp
  params:
    alt: Formats
    formats: [original, png, webp]
  tests: 
    source:
      types: ['webp', 'png', 'jpeg'] 
- id: js-test3
  title: 3. Width and densities
  subtitle: widths 400, densities 1,2,3
  params:
    alt: Width, densities
    width: 400
    densities: [1,2,3]
  tests:
    img:
      width: 400
    source: 
      dataDensities: ['1x', '2x', '3x']
- id: js-test4
  title: 4. Loading auto, sizes 50vw
  subtitle: no lazysizes
  params:
    alt: loading, sizes
    loading: auto
    sizes: 50vw
  tests:
    img: 
      loading: 'auto'
      sizes: '50vw'
      class: ['img-fluid']
      notClass: ['lazysizes']
- id: js-test5
  title: 5. loading lazy, sizes 60vw
  subtitle: no lazysizes
  params:
    alt: no lazysizes
    loading: lazy
    sizes: 60vw
  tests:
    img: 
      loading: lazy
      sizes: 60vw
      class: [img-fluid]
- id: js-test6
  title: 6. loading lazysizes, sizes lazysizes
  subtitle: lazysizes enabled
  params:
    alt: lazysizes enabled
    loading: lazysizes
    sizes: lazysizes
  tests:
    img:
      dataSizes: 'auto'
      class: ['img-fluid', 'lazysizes']
- id: js-test7
  title: 7. figure
  subtitle: 
  partial: figure
  params:
    alt: figure
    figureTitle: Figure Title
    figureTitleH: 3
    caption: Figure Caption
    attr: Attribution Text
    attrLink: http://www.author.com
    link: /
  tests:
    img:
      dataSizes: auto
      class: ['figure-img', 'img-fluid', 'lazyload']
    figure:
      class: [figure]
    figcaption:
      class: [figure-caption]
- id: js-test8
  title: 8. Image metadata
  subtitle: title and alt set in markup metadata
  params:
    src: test1.jpg
  tests:
    img:
      title: Title set via metadata
      alt: Alt set via metadata
- id: js-test9
  title: 9. Standard resize, larger than original width. orig width 1920px
  subtitle: Width 900, 1200, 2000 down to 1920
  params:
    alt: Test Image Alt
    title: Test Image Title
    widths: [900, 1200, 2000]
  tests:
    source: 
      dataWidths: ['900w', '1200w', '1920w']
- id: js-test10
  title: 10. Fill ratio 9:16, larger than original width/height. orig width 1920px
  subtitle: Width 200, 400, 900 down to  607
  params:
    alt: Test Image Alt
    title: Test Image Title
    widths: [200, 400, 900]
    fillRatio: [9, 16]
  tests:
    source: 
      dataWidths: ['200w', '400w', '607w']
--- 

<!-- ![Alt Text](test1.jpg "Test Title") -->
