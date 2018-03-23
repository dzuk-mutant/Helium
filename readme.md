# Thorium

Thorium is an experimental Less framework made to give a stable toolset to create immersive, responsive interfaces that maximise the use of screen space, while cutting the bullshit as much as possible and keeping everything predictable *and* totally flexible.

Thorium is not *really* a boilerplate system, merely an array of prebuilt pieces and standardised behaviours for you to bring your own JS and make your own boilerplates.

<br/>

This is also like, very much a personal project and isn't structured in the best way. So be careful about that.

This has been used to make things like [Pineapple](https://github.com/dzuk-mutant/pineapple), [Mutant Standard's website](https://mutant.tech) and [instances.noct.zone](http://instances.noct.zone).

---


### More predictable and flexible CSS behaviour.

The main philosophy of this framework is to use flexbox to make creating responsive sites in CSS as painless and as predictable as possible. This can often be at the cost of HTML simplicity (ie. some things create more nested tags).

ie. Buttons in Thorium require extra nested divs, but after that, you can simply position all the content you want and not have to worry about any weird behaviour, and you can also make it really flexible and you don't have to use static dimensions.



### Making full use of Flexbox.
Flexbox (especially the 2013 spec) is a wonderful positioning system that takes out so much pain from web design projects, and provides a lot of new opportunities, especially for responsive design.

One of Thorium's main points is that it makes full use of the modern (2013) Flexbox spec. A lot of Thorium's shortcuts and pieces fully rely on this without fallbacks.

If your projects require legacy browser support, this framework will possibly not be for you. See [http://caniuse.com/#feat=flexbox]( http://caniuse.com/#feat=flexbox) to see whether this is suitable for your project. 


### Not a boilerplate.

It's designed to provide an array of prebuilt pieces to give designers a headstart in making personal boilerplates and UI features. It is not designed to give a basic template to develop from, but give you better tools to create your own templates. 

It does not have a theming system, base iconography or other graphical assets, only examples for designers to get to grips with Thorium and placeholders for their own graphical assets.


### Flexible classes and patterns.

Classes for various shortcuts and patterns can be used in HTML in an object-oriented CSS style, or placed into Less files as mixins so you can for instance, change them with @media queries on the fly.

### Immersive design.

It's designed to emphasise full-screen space as much as possible.

### You can use it in static websites!

Just compile the Less and you are ready to go! :D

----

## Licenses and Credits

Check the licenses folder for all licenses.

- Uses an edited version of [ProLoser's Flexbox Less](https://github.com/ProLoser/Flexbox.less) (Thorium's has way fewer prefixes because nowadays you just don't need as many).
- Thanks to Amphetamine on Mastodon for the name idea. (The original name was far less savoury...)
