# Frames

Frames are foundational to standardising sizing behaviour, constraining internal content and exterior boundaries. They are often the equivalent of clears, but they do a lot more in Thorium. 

I wish this wasn't necessary, but it totally is in Thorium-land.

`````

<div class='frame'>
	<div class='container'>
		<!-- content -->
	</div>
</div>

`````

Frames have two components:

### .frame
The exterior shell. The thing that is sized and constrains borders and padding on the container. For gutters, it will clear the negative margins. For other objects, it could define the active scrollable area.
    
### .container
The interior component that houses items. Use this area to apply borders, padding, flex container styles and gutter mixins.

