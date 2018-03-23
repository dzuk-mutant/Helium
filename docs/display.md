## Display
Because unfortunately, there is no concrete/watertight way of detecting touch devices in web programming, the naming conventions assume device form factor primarily (as opposed to snapped apps in narrow form factor Windows 8/10 or macOS 10.11+, although they get a mention too). 

Display consolidates various form factors into buckets based on width. It has fine presets which are then grouped into larger buckets.

| display bucket | min width | max width | analogues |
|---|--|--|--|
| @handset-1 | none | 359px | Small handheld devices. |
| @handset-2 | 360px | 399px | Medium handheld devices. |
| @handset-3 | 400px | 519px | Large handheld devices / 'Phablets', Narrow desktop windows in split screen. |
| @medium-1 | 520px | 619px | Small tablets in portrait, Small desktop windows. |
| @medium-2 | 620px | 899px | Regular tablets in portrait, Small desktop windows.
| @wide-1 | 900px | 1299px | Small tablets in landscape, Small desktop displays (1024x768, 1280x800 etc.), Regular tablets in landscape, Large tablets in portrait, 720p Televisions.
| @wide-2 | 1300dp | none | Large desktop displays (~1080p/4K, etc.), Large (13") tablets in landscape.

---

Device examples:

#### Small handheld devices (<4.5")
iPhone SE, iPod touch, Galaxy S1 - 2, various older and compact handsets.

#### Medium handheld devices (4.5 - 5.5")
iPhone >6, Google Pixel, Galaxy S3/S5.

#### Large handheld devices (5.5 - 6.5")  
iPhone >6 Plus, Google Pixel XL, Galaxy S6+/edge+ onwards, Galaxy Note.

#### Small tablets (7 - 8")
Nexus 7, NVIDIA SHIELD, most tablets between 7 and 8".
  
#### Regular tablets (8 - 10")
iPad mini, iPad Air, Nexus 9, Pixel C, most tablets between 8 and 10".

#### Large/'Pro' tablets (>10")
iPad Pro, Surface Pro, most tablets larger than 10".

---

Display modes are then grouped up into larger buckets when you want to make sweeping changes across multiple similar display boundaries.


| display group | display buckets |
|--|--|
| @handset | @handset-1, @handset-2, @handset-3 |
| @medium | @medium-1, @medium-2 |
| @wide | @wide-1, @wide-2 |

These groups are oriented smallest-first, so the ones that are specified by the lowest resolution will be considered first, reducing potential bandwidth impact on mobile devices.

Note: I called the small group 'handset' to emphasise the size's ergonomic importance on phones, where more linear navigation and bitesize information areas are important. handset-1, handset-2 and handset-3 variants are loosely based on the ergonomic implications of their sizes. 

While all 'handset' devices can be held with one hand, a @handset-1 device has a display that is generally completely reachable by the thumb of the hand holding the device, so operation can be entirely one-handed, on handset-2, that may be possible but not guaranteeable, whereas on @handset-3 devices, a user is generally not capable of using the entire screen one-handed.

