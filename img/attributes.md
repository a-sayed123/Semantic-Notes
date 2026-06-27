<!-- # Alt

**Alternative Text**<br>


***Alternative text that describes the image content or purpose.***

*It is primarily used by assistive technologies and also serves as a fallback when the image cannot be displayed.* <br>
*This attribute is the escaper for the image droping state if anything happend this attributr save us from bad UX* <br>


### Usage and benefits:

*   Copying the image: whene the user highlight the image and copy it the brower put this attribute value .

*   In a11y tree this attribute set accessible properte of name so it is absolutly important 
    even if you will let it empty to make notice that this image is just decorative then browser will ignore it
    in a11y tree and will not expect its name .

*   In the Accessibility Tree, alt usually provides the Accessible Name for the image. -->

# Alt

**Alternative Text**

The `alt` attribute provides a textual alternative for an image.

### Usage and Benefits

* In the Accessibility Tree, `alt` usually provides the Accessible Name of the image.

* If the image cannot be loaded or displayed, the browser may use the `alt` text as a fallback.

* Decorative images should use an empty `alt` value:

```html
<img src="decoration.svg" alt="">
```

This tells assistive technologies that the image does not convey meaningful content and can be ignored.

### Mistakes to Avoid

* Do not omit the `alt` attribute unless you have a very specific reason.

* Do not use filenames as alternative text.

```html
<img src="sunny.webp" alt="sunny.webp">
```

* Do not describe decorative images.

```html
<img src="decoration.svg" alt="">
```
<!-- 
# src srcet sizes

*This is an image shaowing team*

**There is a three ways to show image :**<br>

* src :   html``` 
        <img src="">``` this is the first way and the easier old way .

* src srcset : html```
        <img
        src="icon.avif"
        srcset="
            icon.avif 1x, 
            icon@2x.avif 2x,
            icon@3x.avif 3x
        "
        alt="" 
        >``` <br>  this way specify a typogrphy of images for every screen density (DPR) but for secure our  <br>
                            work we put simple src before this .<br>
        srcset =" <br>
                    image-normal.webp /* (normal image -usualy this image that put in simple src -)  persent that browser will use this image in -> **/  1x ,<br> 
                    image@2x.webp /* (this image is suitable for devices with DPR = 2) */ 2x, <br>
                    ...
                "

* src srcset sizes : this way you will do the same steps put add this additional step that is adding sizes attribute 
    that tell the browser how much layout space the image will occupy 
    for examble : 
        sizes="100vw"
            The image will take the full viewport width.
        sizes="50vw"
            The image will take half of the viewport width.




100) src فقط        ← الأكثر شيوعًا

2) srcset + sizes ← الأكثر أهمية احترافيًا

3) srcset 1x/2x   ← موجود لكنه أقل شيوعًا مما كان قبل سنوات
 -->

# src, srcset, sizes

These attributes help the browser choose and display the most appropriate raster image.

--------------------------------------------------

1) src

<img src="hero.avif" alt="">

The traditional way.

The browser loads a single image file.

--------------------------------------------------

2) src + srcset (Density Descriptors)

<img
    src="icon.avif"
    srcset="
        icon.avif 1x,
        icon@2x.avif 2x,
        icon@3x.avif 3x
    "
    alt=""
>

Used for different device pixel densities (DPR).

1x → normal displays

2x → Retina displays

3x → high-density displays

This technique improves image sharpness.
It is NOT related to screen width.

--------------------------------------------------

3) src + srcset + sizes

<img
    src="hero-800.avif"
    srcset="
        hero-480.avif 480w,
        hero-800.avif 800w,
        hero-1600.avif 1600w
    "
    sizes="100vw"
    alt=""
>

Used for responsive raster images.

The browser chooses the most appropriate image according to:

* viewport size
* image display size
* device pixel density

sizes tells the browser how much layout space the image is expected to occupy.

**الطريقة الاول العارض الاعمى** 
<br>

**الطريقة الثانية باحث الكثافة**
<br>

**الطريقة الثالثة المهندس المعماري**
<br>

# Loading

*this attribute specify the behavior that browser will perform with loading img*

### value

* eager (default) : This value order the browser to load image directly after loading page anywhere the image is in .
* lazy : This value order the browser to load image when the be near of it by a specific distance  set by the browser .

**whan i use lazy** :<br>

1) the image is below the viewport or folded undernth the user have to scroll to see it .
2) Product lists.
3) Article cards.
4) Images that the user does not see directly .
5) Pages containing dozens of images.
<br><br>

``Hero, Logo, Above the Fold``<br>
&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp; ``↓`` <br>
&nbsp; &nbsp; &nbsp;&nbsp; &nbsp;  ``eager``<br><br>
``Gallery, Cards, Long Lists, Below the Fold`` <br>
&nbsp; &nbsp; &nbsp;&nbsp; &nbsp; &nbsp; &nbsp;  ``↓`` <br>
&nbsp; &nbsp; &nbsp;&nbsp; &nbsp;   `lazy` <br>