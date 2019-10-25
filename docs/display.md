## Display

![](images/display_portrait.png)
![](images/display_landscape.png)

This is Helium's display boundary stuff.

Because Helium is designed with full-screen software design in mind, screen size boundaries are relatively granular (but can also be more generic if you wish) and are oriented around ergonomic considerations.

The boundaries were developed from researching a lot of different devices' virtual display sizes as would be seen by a web browser.

Due to a quirk in Stylus' handling of @media variables, you have to access display boundary variables from arrays. There are two different arrays, one for width, and one for height.

**sw** (array of width variables)  
ie. `@media sw.handset-3`

**sh**	(array of height variables)  
ie. `@media sh.limited`

### Display width groups

| display bucket | min width | max width | analogues |
|---|--|--|--|
| sw.handset | none | 499px | Handheld devices (ie. phones) |
| sw.portable | 500px | 1049px | Most tablet contexts |
| sw.wide | 1050px | none | Large landscape tablet, laptop, desktop, or TV contexts.  |


### Display width areas

| display bucket | min width | max width | analogues |
|---|--|--|--|
| sw.handset-1 | none | 349px | Small devices that can be held in one hand, and are entirely operable with one hand. |
| sw.handset-2 | 350px | 389px | Medium devices that can be held in one hand, and are mostly (but not completly) operable with one hand. |
| sw.handset-3 | 390px | 499px | Large devices that can be held in one hand, but are not entirely operable with one hand. |
| sw.portable-1 | 500px | 649px | Small tablets. Narrow desktop windows. |
| sw.portable-2 | 650px | 849px | Regular tablets (ie. iPad 9.7") in portrait, Small desktop windows. |
| sw.portable-3 | 850px | 1049px | Large tablets in portrait. Small and regular tablets in landscape. 1024x768. |
| sw.wide-1 | 1050px | 1499px | Large tablets in landscape and laptops. 720p, 1366x768, 1280x800.  |
| sw.wide-2 | 1500px | none | Desktop and other large displays. 1680x1050, 1080p/4K. |



### Display height groups

| display bucket | min height | max height | analogues |
|---|--|--|--|
| sh.limited | none | 499px | Handheld devices (ie. phones) in landscape. The amount of vertical space is very limited. |
| sh.medium | 500px | 849px | Small and regular tablets in landscape. The amount of vertical space is restricted. |
| sh.tall | 850px | none | Large landscape tablet, laptop or desktop contexts. The amount of vertical space is ample. |



---

### Device examples:

##### handset-1
Typically devices below 4.7".

| Device(s) | Viewport resolution (portrait) |
| -- | -- |
| Apple iPhone 1-4 | 320 x 480 |
| Apple iPhone 5, 5c, 5s, SE | 320 x 568 |

##### handset-2
Typically devices between 4.7 - ~6"

| Device(s) | Viewport resolution (portrait) |
| -- | -- |
| Apple iPhone 6-8 | 375 x 687 |
| Apple iPhone X, XS, 11 Pro | 375 x 812 |
| Sony Xperia XZ2 Compact | 360 x 720 |

##### handset-3
Typically devices between ~6 - 7".

| Device(s) | Viewport resolution (portrait) |
| -- | -- |
| Google Pixel XL | 412 x 732 |
| Apple iPhone 6-8 Plus | 414 x 736 |
| Google Pixel 3 | 411 x 823 (x2.625) |
| Google Pixel 3 XL | 411 x 846 (x3) |
| Apple iPhone XR, XS Max, 11, 11 Pro Max | 414 x 896 |
| Samsung Galaxy S9+, Google Pixel 3 XL | 411 x 846 |
| Sony Xperia 1 | 411 x 960 |

##### portable-1
Devices between 7 - 8".

| Device(s) | Viewport resolution (portrait) |
| -- | -- |
| Google Nexus 7 (2013) | 600 x 960 |


##### portable-2
Devices between 8 - 10".

| Device(s) | Viewport resolution (portrait) |
| -- | -- |
| Apple iPad 9.7", mini | 768 x 1024 |
| Apple iPad 10.2" | 810 x 1080 |
| Apple iPad Pro (2015-2017) 10.5" | 834 x 1112 |
| Apple iPad Pro (2018) 11" | 834 x 1194 |
| Google Nexus 10 | 800 x 1280 |
| Google Pixel C | 900 x 1280 |


##### portable-3
Portable devices larger than 10".

| Device(s) | Viewport resolution (portrait) |
| -- | -- |
| Apple iPad Pro (2015-2017, 2018) 12.9" | 1024 x 1366 |
| Microsoft Surface Pro 2017 | 912 x 1368 |

---
