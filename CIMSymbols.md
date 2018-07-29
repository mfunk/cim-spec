


## CIM3DMarkerGraphic
Represents a 3D marker graphic. A 3DMarkerGraphic contains some properties that describe how the graphic is drawn (such as DiffuseColor, an optional URL to a texture image, and some material properties) and a URL pointing to a ShapeVertices structure that describes the marker's "geometry" (such as the vertex position, normal vector, and texture coordinates). Because multiple 3DMarkerGraphics can reference the same ShapeVertices structure, an OffsetIntoShapeVertices and CountOfShapeVertices are provided to reference what records within the ShapeVertices correspond to this 3DMarkerGraphic. The 3DMarkerGraphic also has an esri3DPrimitiveType that describes how those vertices are used to form shapes. These are analogous to the common primitive types in OpenGL, such as triangle strips and fans. Knowing what type of primitives are contained in this shape lets the reader determine how many Vertices are needed to form each primitive in the shape graphic.


### CIM3DMarkerGraphic

|Property | Type | Description |
|---------|--------|--------|
| primitiveType | [enumeration PrimitiveType3D](CIMEnumerations.md#enumeration-primitivetype3d)|The primitive type.
| diffuseColor | [Color](Types.md#color)|The diffuse color.
| shapeVerticesCollectionIndex | number //int32|The shape vertices collection index.
| isSubstitutionAllowed | boolean|A boolean option indicating whether or not substitution is allowed.
| materialProperties | [CIMMaterialProperties](CIMSymbols.md#cimmaterialproperties)|The material properties.
| entityID | number //int32|The entity ID.
| offsetIntoShapeVertices | number //int32|The offset into the shape vertices collection.
| countOfShapeVertices | number //int32|The count of shape vertices.
| patchPriority | number //int32|The patch priority.
| textureIndex | number //int32|The texture index.






## CIM3DMarkerLOD
Represents a 3D Marker LOD. A 3D Marker LOD contains a set of one or more 3DMarkerGraphics for its defined LOD, and a list of EntityNames for the 3DMarkerGraphics therein. The list of EntityNames is indexed by the EntityID defined on each 3DMarkerGraphic.


### CIM3DMarkerLOD

|Property | Type | Description |
|---------|--------|--------|
| markerGraphics | [CIM3DMarkerGraphic](CIMSymbols.md#cim3dmarkergraphic) |The marker graphics.
| entityNames | string|The entity names.






## CIM3DSymbolProperties
Represents 3D symbol properties, a collection of symbol properties that apply when the symbol is used in a 3D context.


### CIM3DSymbolProperties

|Property | Type | Description |
|---------|--------|--------|
| dominantSizeAxis3D | [enumeration DominantSizeAxis](CIMEnumerations.md#enumeration-dominantsizeaxis)|The dominant size axis.
| rotationOrder3D | [enumeration RotationOrder](CIMEnumerations.md#enumeration-rotationorder)|The rotation order 3D.
| scaleZ | number //double|The scale Z.
| scaleY | number //double|The scale Y.





### Enumeration: AngleAlignment
Angle alignment types.

|Property | Value | Description |
|---------|--------|--------|
| Display| 0| Points remain aligned to the display when the map is rotated.
| Map| 1| Points are rotated with the map.




## CIMBackgroundCallout
Represents a background callout which draws a callout with an optional polygon background and leader line.


### CIMCallout

|Property | Type | Description |
|---------|--------|--------|
| leaderTolerance | number //double|The leader tolerance which is the closest distance (in points) to the text the anchor point can be for the callout to draw.
| leaderOffset | number //double|The leader offset which is an offset value defining the distance (in points) between the anchor point and the beginning of the drawn leader.


### CIMLineCallout

|Property | Type | Description |
|---------|--------|--------|
| leaderLineSymbol | [CIMLineSymbol](CIMSymbols.md#cimlinesymbol)|The line symbol to draw leaders with.
| gap | number //double|The gap (in points) between the point symbol and the beginning of the leader line.
| lineStyle | [enumeration LeaderLineStyle](CIMSymbols.md#enumeration-leaderlinestyle)|The style of line to generate when a Point leader is drawn defined by an enumeration value. Line leaders will always be drawn with their own geometry.


### CIMBackgroundCallout

|Property | Type | Description |
|---------|--------|--------|
| backgroundSymbol | [CIMPolygonSymbol](CIMSymbols.md#cimpolygonsymbol)|The symbol used to draw the background. If null, the background doesn't draw.
| accentBarSymbol | [CIMLineSymbol](CIMSymbols.md#cimlinesymbol)|The symbol used to draw the accent bar. If null, the accent bar doesn't draw.
| margin | [CIMTextMargin](CIMSymbols.md#cimtextmargin)|The text margin defining the space around the text that is accounted for in background creation.






## CIMBalloonCallout
Represents a balloon callout. Balloon callouts are a filled background that is placed behind text. They may or may not have a leader line connecting the callout to an anchor point.


### CIMCallout

|Property | Type | Description |
|---------|--------|--------|
| leaderTolerance | number //double|The leader tolerance which is the closest distance (in points) to the text the anchor point can be for the callout to draw.
| leaderOffset | number //double|The leader offset which is an offset value defining the distance (in points) between the anchor point and the beginning of the drawn leader.


### CIMBalloonCallout

|Property | Type | Description |
|---------|--------|--------|
| balloonStyle | [enumeration BalloonCalloutStyle](CIMSymbols.md#enumeration-ballooncalloutstyle)|The balloon style.
| backgroundSymbol | [CIMPolygonSymbol](CIMSymbols.md#cimpolygonsymbol)|The symbol used to draw the background.
| margin | [CIMTextMargin](CIMSymbols.md#cimtextmargin)|The text margin defining the space around the text that is accounted for in balloon creation.





### Enumeration: BalloonCalloutStyle
Balloon callout styles.

|Property | Value | Description |
|---------|--------|--------|
| Rectangle| 0| Rectangle style.
| RoundedRectangle| 1| Rounded rectangle style.
| Oval| 2| Oval style.




## CIMBarChartMarker
Represents a bar chart marker, a chart made of vertical bars displaying values.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMMarker

|Property | Type | Description |
|---------|--------|--------|
| anchorPoint | [Point](ExternalReferences.md#point)|The specified location where all transformation property operations originate.
| anchorPointUnits | [enumeration SymbolUnits](CIMSymbols.md#enumeration-symbolunits)|A value which specifies if the anchor point location is considered a percentage of the size or as an absolute distance.
| angleX | number //double|The angle the marker is rotated around the X axis. This type of rotation is also referred to as tilt and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Tilt.
| angleY | number //double|The angle the marker is rotated around the Y axis. This type of rotation is also referred to as roll and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Roll.
| dominantSizeAxis3D | [enumeration DominantSizeAxis](CIMEnumerations.md#enumeration-dominantsizeaxis)|Which axis is considered as the Size in 3D. Only applicable when the marker layer is a 3DShapeMarker.
| offsetX | number //double|The value the marker is moved along the X axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetY | number //double|The value the marker is moved along the Y axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetZ | number //double|The value the marker is moved along the Z axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| rotateClockwise | boolean|A boolean indicating whether the rotation is applied clockwise or counterclockwise to the marker layer.
| rotation | number //double|The angle that the marker is rotated around the anchor point, in degrees.
| size | number //double|The height of the marker. Modifying Size changes the marker's height to the specified size and the width is updated proportionally.
| billboardMode3D | [enumeration BillboardMode](CIMEnumerations.md#enumeration-billboardmode)|The billboard mode of the marker.
| markerPlacement | [MarkerPlacement](Types.md#markerplacement)|The marker placements which determine how markers are placed along a line or within a polygon.


### CIMChartMarker

|Property | Type | Description |
|---------|--------|--------|
| display3D | boolean|A boolean value which indicates whether to draw the chart with a 3D perspective.
| parts | [CIMChartPart](CIMSymbols.md#cimchartpart) |The individual components of the chart marker.
| thickness3D | number //double|The thickness or depth of a chart. Only applied when Display3D is true.
| tilt3D | number //double|The tilt (rotation around the X axis) of the chart. Only applied when Display3D is true.


### CIMBarChartMarker

|Property | Type | Description |
|---------|--------|--------|
| axesSymbol | [CIMLineSymbol](CIMSymbols.md#cimlinesymbol)|The axes symbol.
| spacing | number //double|The spacing.
| verticalBars | boolean|A boolean value indicating whether this bar chart marker has vertical bars.
| width | number //double|The width.





### Enumeration: BlendingMode
Blending modes. Determines how the strokes with dash patterns and other patterns (tiled pictures, placement effects) are handled at the end points of the line geometry's segments. If more than one pattern exists (for example, a dashed simple stroke, a hash stroke, and a marker stroke) then the longest pattern's length is affected directly by this option and the rest of the stroke patterns are resized proportionately to match.

|Property | Value | Description |
|---------|--------|--------|
| None| 0| No blending.
| Alpha| 1| Alpha blending.
| Screen| 2| Screen.
| Multiply| 3| Multiply.
| Add| 4| Add.



### Enumeration: BlockProgression
Block progressions.

|Property | Value | Description |
|---------|--------|--------|
| TTB| 0| Top To Bottom.
| RTL| 1| Right To Left (vertical text).
| BTT| 2| Bottom To Top.




## CIMCGAAttribute
Represents a CGA attribute, the symbol attribute as specified by the CGA code in the rule package.


### CIMCGAAttribute

|Property | Type | Description |
|---------|--------|--------|
| name | string|The name.
| CGAAttributeType | [enumeration CGAAttributeType](CIMSymbols.md#enumeration-cgaattributetype)|The CGA attribute type.
| value | VARIANT|The value.





### Enumeration: CGAAttributeType
CGA attribute type.

|Property | Value | Description |
|---------|--------|--------|
| number //float| 0| number //float - Attribute is a numeric attribute that is a number //float value
| String| 1| String - Attribute is a string
| Boolean| 2| Boolean - Attribute is a boolean




## CIMCharacterMarker
Represents a character marker. The shape of a marker is defined by a glyph in a font. The marker is drawn using the specified size and color. Each marker has a defined frame around the glyph that is considered when the size is applied. As a result, character markers of the same size may appear different sizes if the glyphs frames are different sizes.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMMarker

|Property | Type | Description |
|---------|--------|--------|
| anchorPoint | [Point](ExternalReferences.md#point)|The specified location where all transformation property operations originate.
| anchorPointUnits | [enumeration SymbolUnits](CIMSymbols.md#enumeration-symbolunits)|A value which specifies if the anchor point location is considered a percentage of the size or as an absolute distance.
| angleX | number //double|The angle the marker is rotated around the X axis. This type of rotation is also referred to as tilt and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Tilt.
| angleY | number //double|The angle the marker is rotated around the Y axis. This type of rotation is also referred to as roll and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Roll.
| dominantSizeAxis3D | [enumeration DominantSizeAxis](CIMEnumerations.md#enumeration-dominantsizeaxis)|Which axis is considered as the Size in 3D. Only applicable when the marker layer is a 3DShapeMarker.
| offsetX | number //double|The value the marker is moved along the X axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetY | number //double|The value the marker is moved along the Y axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetZ | number //double|The value the marker is moved along the Z axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| rotateClockwise | boolean|A boolean indicating whether the rotation is applied clockwise or counterclockwise to the marker layer.
| rotation | number //double|The angle that the marker is rotated around the anchor point, in degrees.
| size | number //double|The height of the marker. Modifying Size changes the marker's height to the specified size and the width is updated proportionally.
| billboardMode3D | [enumeration BillboardMode](CIMEnumerations.md#enumeration-billboardmode)|The billboard mode of the marker.
| markerPlacement | [MarkerPlacement](Types.md#markerplacement)|The marker placements which determine how markers are placed along a line or within a polygon.


### CIMCharacterMarker

|Property | Type | Description |
|---------|--------|--------|
| characterIndex | number //int32|The Unicode decimal value for the individual glyph of the font that defines the shape of the marker.
| depth3D | number //double|The depth of the marker when drawn in 3D.
| fontFamilyName | string|The font family name of the font. e.g. Comic Sans
| fontStyleName | string|The style name for the font family. e.g. Regular, Bold, or Italic.
| fontType | [enumeration FontType](CIMSymbols.md#enumeration-fonttype)|The font type.
| scaleX | number //double|The width of the symbol without changing the height (or depth in 3D), as a ratio.
| symbol | [CIMPolygonSymbol](CIMSymbols.md#cimpolygonsymbol)|The polygon symbol that is used to renderer the marker.
| verticalOrientation3D | boolean|A boolean value which indicates whether the marker stands a marker upright as though locked in place. The marker can be viewed from all angles.
| scaleSymbolsProportionally | boolean|A boolean value which indicates whether the strokes and/or fills of a marker are scaled proportionally when the symbol size is changed. When enabled, the strokes for the outline or fill of the polygon symbol used to draw the marker will be scaled proportionally with changes to the symbol size. If this property is not enabled, the stroke will draw with the specified width regardless of the marker size.
| respectFrame | boolean|A boolean value which indicates whether the frame of the character marker should be honored when transforming the marker.






## CIMChartPart
Represents a chart part, individual components of the chart marker.


### CIMChartPart

|Property | Type | Description |
|---------|--------|--------|
| value | number //double|The value of the chart part used to size the part.
| polygonSymbol | [CIMPolygonSymbol](CIMSymbols.md#cimpolygonsymbol)|The polygon symbol used to draw the chart part.






## CIMClippingPath
Represents a vector marker clipping path.


### CIMClippingPath

|Property | Type | Description |
|---------|--------|--------|
| clippingType | [enumeration ClippingType](CIMSymbols.md#enumeration-clippingtype)|The the clipping type.
| path | [Polygon](ExternalReferences.md#polygon)|The the clipping path.





### Enumeration: ClippingType
Clipping types.

|Property | Value | Description |
|---------|--------|--------|
| Intersect| 0| Intersect.
| Subtract| 1| Subtract.




## CIMColorSubstitution
Represents color substitution, an ordered list of color substitutes.


### CIMColorSubstitution

|Property | Type | Description |
|---------|--------|--------|
| oldColor | [Color](Types.md#color)|The old color (the color that will be substituted).
| newColor | [Color](Types.md#color)|The new color that will replace the old color.





### Enumeration: ExternalColorMixMode
Options to control how material combines with externally defined colors.

|Property | Value | Description |
|---------|--------|--------|
| Tint| 0| Tint using external color.
| Ignore| 1| Ignore external color.
| Multiply| 99| Multiply components by components of external color.



### Enumeration: ExtremityPlacement
Extremity placement options which specify at which ends of the line a marker will be placed.

|Property | Value | Description |
|---------|--------|--------|
| Both| 0| Both - marker is placed at the beginning and end of the line.
| JustBegin| 1| JustBegin - marker is placed at the beginning of the line, determined by the direction that the line was digitized.
| JustEnd| 2| JustEnd - marker is placed at the end of the line, determined by the direction that the line was digitized.
| None| 3| None - no marker is placed at either end of the marker.



### Enumeration: FillMode
Fill modes.

|Property | Value | Description |
|---------|--------|--------|
| Mosaic| 0| Mosaic fill.
| Centered| 1| Centered fill.



### Enumeration: FontEffects
Font effects.

|Property | Value | Description |
|---------|--------|--------|
| Normal| 0x00| Normal text.
| Superscript| 0x01| Superscript text.
| Subscript| 0x02| Subscript text



### Enumeration: FontEncoding
Font encodings.

|Property | Value | Description |
|---------|--------|--------|
| MSSymbol| 0| Symbol encoding.
| Unicode| 1| Unicode.



### Enumeration: FontType
Font types.

|Property | Value | Description |
|---------|--------|--------|
| Unspecified| 0| Unspecified.
| TrueType| 1| TrueType.
| PSOpenType| 2| OpenType with CFF outlines.
| TTOpenType| 3| OpenType with TrueType outlines.
| Type1| 4| Adobe Type 1.




## CIMGeometricEffectAddControlPoints
Represents the add control points geometric effect. Dynamically adds geometry control points to a feature to dictate the placement of markers or other effect properties that leverage control points. Control points are placed at angles or deflection based on the AngleTolerance value.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectAddControlPoints

|Property | Type | Description |
|---------|--------|--------|
| angleTolerance | number //double|The value below which a control point will be placed. The maximum amount of deflection from one segment to another at a vertex. Angle values between 180 and 360 are interpreted the same as values between 0 and 180. Angle values of 180 and 360 are the same as 0.






## CIMGeometricEffectArrow
Represents the arrow geometric effect which creates a dynamic line along a line feature with an arrow of a specified style and width.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectArrow

|Property | Type | Description |
|---------|--------|--------|
| geometricEffectArrowType | [enumeration GeometricEffectArrowType](CIMSymbols.md#enumeration-geometriceffectarrowtype)|The type of arrow to be displayed.
| width | number //double|The distance between the lines that construct the body of the arrow.





### Enumeration: GeometricEffectArrowType
Geometric effect arrow types.

|Property | Value | Description |
|---------|--------|--------|
| OpenEnded| 0| An open ended arrow.
| Block| 1| A block arrow.
| Crossed| 2| A crossed arrow.




## CIMGeometricEffectBuffer
Represents the buffer geometric effect which creates a dynamic polygon with a specified distance around features.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectBuffer

|Property | Type | Description |
|---------|--------|--------|
| size | number //double|The distance from the feature. This distance is either from the edge of the marker, the edge of the stroke or the edge of the polygon outline.






## CIMGeometricEffectCut
Represents the cut geometric effect which creates a dynamic line that is shorter on one or both ends than the line feature or polygon outline.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectCut

|Property | Type | Description |
|---------|--------|--------|
| beginCut | number //double|The distance from the beginning of a line that the display of the stroke starts. The beginning of the line is determined by the direction in which the line was digitized.
| endCut | number //double|The distance from the end of a line that the display of the stroke starts. The end of the line is determined by the direction in which the line was digitized.
| invert | boolean|A boolean value which indicates that the effect should be applied in the opposite manner. This displays the stroke symbol only at the ends of the line and leaves the rest of the line unsymbolized.






## CIMGeometricEffectDashes
Represents the dashes geometric effect which creates a dynamic multipart line geometry from a line feature or the outline of a polygon based on a template.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectDashes

|Property | Type | Description |
|---------|--------|--------|
| customEndingOffset | number //double|Where the pattern should end relative to the ending point of the geometry. Negative numbers indicate a shift to the left and positive numbers a shift to the right. This property is only applied if the LineDashEnding is set to Custom.
| dashTemplate | [number], //[double],|The distance for each dash and gap. There can be multiple dash and gap values to form a complex pattern.
| lineDashEnding | [enumeration LineDashEnding](CIMSymbols.md#enumeration-linedashending)|The setting which determines how the strokes with dash patterns and other patterns (pictures, placement effects) are handled at the end points of the line geometry's segments.
| offsetAlongLine | number //double|The position where the pattern should begin relative to the starting point of the geometry. It shifts the entire pattern along the line the specified distance. Negative values indicate a shift to the left and positive numbers a shift to the right. This property is only applied if LineDashEnding is set to NoConstraint or Custom.
| controlPointEnding | [enumeration LineDashEnding](CIMSymbols.md#enumeration-linedashending)|The line dash ending position.






## CIMGeometricEffectDonut
Represents the donut geometric effect which creates a dynamic polygon ring of a specified width in relation to the outline of polygon features.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectDonut

|Property | Type | Description |
|---------|--------|--------|
| method | [enumeration GeometricEffectDonutMethod](CIMSymbols.md#enumeration-geometriceffectdonutmethod)|The method which specifies the way the strokes are displayed at convex corners of the polygon.
| option | [enumeration GeometricEffectOffsetOption](CIMSymbols.md#enumeration-geometriceffectoffsetoption)|The option for the way the symbol handles complex geometries.
| width | number //double|The distance from the edge of the polygon that the fill symbol is to be displayed.





### Enumeration: GeometricEffectDonutMethod
Geometric effect donut methods.

|Property | Value | Description |
|---------|--------|--------|
| Mitered| 0| Mitered - matches the exact shape around a convex corner of the polygon.
| Bevelled| 1| Bevelled - follows the shortest straight path across a convex corner of the polygon.
| Rounded| 2| Rounded - follows a path of equal distance around a convex corner of the polygon.
| Square| 3| Square - follows a straight path across the corner of a line or polygon.
| TrueBuffer| 4| TrueBuffer - uses the buffer algorithm to follow a path around convex corners.




## CIMGeometricEffectEnclosingPolygon
Represents the enclosing polygon geometric effect which creates a dynamic polygon from the spatial extent of a line or polygon feature.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectEnclosingPolygon

|Property | Type | Description |
|---------|--------|--------|
| method | [enumeration GeometricEffectEnclosingPolygonMethod](CIMSymbols.md#enumeration-geometriceffectenclosingpolygonmethod)|The method which specifies the way in which the polygon geometry is generated around the feature geometry.





### Enumeration: GeometricEffectEnclosingPolygonMethod
Geometric effect enclosing polygon methods.

|Property | Value | Description |
|---------|--------|--------|
| ClosePath| 0| ClosePath - for polygon input, it generates a polygon that matches the geometry of a polygon feature. For line input, it generates a polygon that connects both ends of the line to each other.
| ConvexHull| 1| ConvexHull - for polygon input, it generates a polygon with a minimum number of sides to surround the feature. For line input, it generates a polygon that approximates the shape of the line.
| RectangularBox| 2| RectangularBox - generates a polygon equal to the spatial envelope of the feature.




## CIMGeometricEffectExtension
Represents the extension geometric effect which creates a dynamic line that is extended from either the beginning or the end of the line feature at a specified deflection angle and length.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectExtension

|Property | Type | Description |
|---------|--------|--------|
| deflection | number //double|The deflection angle used for the extension. A value of 0 indicates no deflection.
| origin | [enumeration GeometricEffectExtensionOrigin](CIMSymbols.md#enumeration-geometriceffectextensionorigin)|The origin of the extension to add to the line. The beginning and end of the line is defined by the direction the line was digitized.
| length | number //double|The length of the extension that is dynamically created.





### Enumeration: GeometricEffectExtensionOrigin
Geometric effectthe extension origins. Specifies the origin of the extension to add to the line. The beginning and end of the line is defined by the direction the line was digitized.

|Property | Value | Description |
|---------|--------|--------|
| BeginningOfLine| 0| BeginningOfLine - extension is added to the end of the line.
| EndOfLine| 1| EndOfLine - extension is added to the end of the line.




## CIMGeometricEffectJog
Represents the jog geometric effect which creates a dynamic line with a jog of a specified angle, position, and width in the line.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectJog

|Property | Type | Description |
|---------|--------|--------|
| angle | number //double|The angle of the jog in the line which is measured in degrees.
| length | number //double|The length of the segment that forms the jog in the line.
| position | number //double|The location of the center of the jog, as a percentage measured from the start of the input geometry.






## CIMGeometricEffectMove
Represents the move geometric effect which creates a point, line or polygon that is offset a specified distance in X and Y.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectMove

|Property | Type | Description |
|---------|--------|--------|
| offsetX | number //double|The distance to move the symbol along the X-axis of the feature geometry.
| offsetY | number //double|The distance to move the symbol along the Y-axis of the feature geometry.






## CIMGeometricEffectOffset
Represents the offset geometric effect which creates a dynamic line or polygon offset at a specified distance perpendicularly from a feature.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectOffset

|Property | Type | Description |
|---------|--------|--------|
| method | [enumeration GeometricEffectOffsetMethod](CIMSymbols.md#enumeration-geometriceffectoffsetmethod)|The way the strokes or fills are displayed at corners.
| offset | number //double|The distance of the symbol perpendicular to the feature geometry.
| option | [enumeration GeometricEffectOffsetOption](CIMSymbols.md#enumeration-geometriceffectoffsetoption)|The way the symbol handles complex geometries.





### Enumeration: GeometricEffectOffsetMethod
Geometric effect offset method which specifies the way the strokes or fills are displayed at corners.

|Property | Value | Description |
|---------|--------|--------|
| Mitered| 0| Mitered - matches the exact shape around a corner of the line or polygon.
| Bevelled| 1| Bevelled - follows the shortest straight path across a corner of the line or polygon.
| Rounded| 2| Rounded - follows a path of equal distance around a corner of the line or polygon.
| Square| 3| Square - follows a straight path across the corner of a line or polygon.



### Enumeration: GeometricEffectOffsetOption
Geometric effect offset options which specify the way the symbol handles complex geometries.

|Property | Value | Description |
|---------|--------|--------|
| Fast| 0| Fast - ignores complex geometries and applies a best fit to the symbol.
| Accurate| 1| Accurate - accommodates complex geometries and applied a true fit to the symbol.




## CIMGeometricEffectOffsetTangent
Represents the offset tangent geometric effect which creates a dynamic line along a line feature offset in the direction defined by either the beginning or the end of the line.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectOffsetTangent

|Property | Type | Description |
|---------|--------|--------|
| method | [enumeration GeometricEffectOffsetTangentMethod](CIMSymbols.md#enumeration-geometriceffectoffsettangentmethod)|The origin of the tangent offset for the line. The beginning and end of the lines are defined by how the line was digitized.
| offset | number //double|The distance the geometry is moved tangent.





### Enumeration: GeometricEffectOffsetTangentMethod
Geometric effect offset tangent methods which specify the origin of the tangent offset for the line. The beginning and end of the lines are defined by how the line was digitized.

|Property | Value | Description |
|---------|--------|--------|
| BeginningOfLine| 0| BeginningOfLine - the tangent offset is applied from the beginning of the line.
| EndOfLine| 1| EndOfLine - the tangent offset is applied from the end of the line.




## CIMGeometricEffectRadial
Represents the radial geometric effect which creates a dynamic line of a specified length and angle originating from a point feature.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectRadial

|Property | Type | Description |
|---------|--------|--------|
| angle | number //double|The orientation of the line from the marker. The angle is calculated in a counterclockwise manner with 0 degrees equal to due east.
| length | number //double|The distance of the line from end to end.






## CIMGeometricEffectRegularPolygon
Represents the regular polygon geometric effect which creates a dynamic polygon around a point feature with a specified number of edges. All edges are equal in length and all angles are equal.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectRegularPolygon

|Property | Type | Description |
|---------|--------|--------|
| angle | number //double|The amount of rotation for the polygon.
| edges | number //int32|The number of sides for the polygon. Specifying a value less than 3 produces a circle.
| radius | number //double|The distance from the center of the polygon.






## CIMGeometricEffectReverse
Represents the reversegeometric effect which creates a dynamic polygon around a point feature with a specified number of edges. All edges are equal in length and all angles are equal.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectReverse

|Property | Type | Description |
|---------|--------|--------|
| reverse | boolean|A boolean value which indicates whether the dynamic output of a previous geometric effect is to be flipped or not.






## CIMGeometricEffectRotate
Represents the rotate geometric effect which creates a dynamic line or polygon rotated a specified angle from the feature.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectRotate

|Property | Type | Description |
|---------|--------|--------|
| angle | number //double|The amount of rotation for the symbol.






## CIMGeometricEffectScale
Represents the rotate geometric effect which creates a dynamic line or polygon scaled by a specified factor. Vertices are moved in relation to the center point of a feature envelope. Values greater than 1 move vertices away from the center point. Values between 0 and 1 move vertices toward the center point. Values less than 0 draw an inverse dynamic line or polygon where the vertices have crossed to the other side of the center point.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectScale

|Property | Type | Description |
|---------|--------|--------|
| XScaleFactor | number //double|The amount of change in size of a symbol in the x-axis. The value is expressed in terms of a ratio/percentage.
| YScaleFactor | number //double|The amount of change in size of a symbol in the y-axis. The value is expressed in terms of a ratio/percentage.






## CIMGeometricEffectSuppress
Represents the supress geometric effect which creates a dynamic line that hides sections of a stroke between pairs control points.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectSuppress

|Property | Type | Description |
|---------|--------|--------|
| suppress | boolean|A boolean value which indicates if the portion of the stroke symbol between control points should be suppressed. Sections that are suppressed draw with no symbol.
| invert | boolean|A boolean value which inverts the suppression process. If this value is true, portions of the stroke symbol between control points are kept and all other portions are suppressed.






## CIMGeometricEffectTaperedPolygon
Represents the tapered polygon geometric effect which creates a dynamic polygon along a line feature, whose width varies by two specified amounts along its length, as defined by a percentage of the line feature's length.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectTaperedPolygon

|Property | Type | Description |
|---------|--------|--------|
| fromWidth | number //double|The width at the start of the line to be used to generate a polygon.
| length | number //double|The distance along the line to be used to generate the polygon.
| toWidth | number //double|The width at the end of the line to be used to generate the polygon.






## CIMGeometricEffectWave
Represents the wave geometric effect which creates a dynamic line or polygon along a feature with a repeating wave pattern.


### CIMGeometricEffect

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMGeometricEffectWave

|Property | Type | Description |
|---------|--------|--------|
| amplitude | number //double|The distance perpendicular to a feature to display the curves for the symbol.
| period | number //double|The distance along the line or polygon to display the curves for the symbol
| seed | number //int32|The staring value for generating a random number. This is only used when the Waveform is set to Random.
| waveform | [enumeration GeometricEffectWaveform](CIMSymbols.md#enumeration-geometriceffectwaveform)|The shape of the curves to be displayed along the symbol.





### Enumeration: GeometricEffectWaveform
Geometric effect offset waveforms.

|Property | Value | Description |
|---------|--------|--------|
| Sinus| 0| Sinus - displays a sinusoidal curve.
| Square| 1| Square - displays a three-sided rectangular shape.
| Triangle| 2| Triangle - displays a two-sided triangular shape.
| Random| 3| Random - displays a sine curve with random variations in the period and amplitude



### Enumeration: GlyphHinting
Glyph hinting options.

|Property | Value | Description |
|---------|--------|--------|
| None| 0| No glyph hinting.
| Default| 1| Default glyph hinting according to the font's settings.
| Force| 2| Force glyph hinting.



### Enumeration: GradientAlignment
Gradient alignment types.

|Property | Value | Description |
|---------|--------|--------|
| Buffered| 0| Buffered - Distributes the color ramp along the line's geometry from the outside in (similar to the effect of creating a buffer of the line, then using the "buffer" fill type).
| Left| 1| Left - Progresses the color ramp from the line's centerline to the outside edge on the left. The gradient will follow any curvature in the line's geometry.
| Right| 2| Right - Progresses the color ramp from the line's centerline to the outside edge on the right. The gradient will follow any curvature in the line's geometry.
| AlongLine| 3| Along line - Distributes the color ramp linearly along the line, following the curvature of the line.




## CIMGradientFill
Represents a gradient fill which fills polygonal geometry with a specified color scheme.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMFill

|Property | Type | Description |
|---------|--------|--------|


### CIMGradientFill

|Property | Type | Description |
|---------|--------|--------|
| angle | number //double|The angle of the gradient when the GradientMethod is set to Linear or Rectangular.
| colorRamp | [ColorRamp](Types.md#colorramp)|The color scheme that is applied to the fill.
| gradientMethod | [enumeration GradientFillMethod](CIMSymbols.md#enumeration-gradientfillmethod)|A value which specifies how the gradient is applied within the fill.
| gradientSize | number //double|A value which determines how much of the feature is covered by the color scheme. This is either a percentage of the total area which the color scheme spans or the number of page units from the starting point at which the gradient displays.
| gradientSizeUnits | [enumeration SymbolUnits](CIMSymbols.md#enumeration-symbolunits)|A value which specifies whether GradientSize is applied with an absolute distance or a relative percentage.
| gradientType | [enumeration GradientStrokeType](CIMSymbols.md#enumeration-gradientstroketype)|A value which specifies if the gradient is applied with discrete intervals or if it is continuous.
| interval | number //int32|How many bands draw when the GradientType is set to Discrete





### Enumeration: GradientFillMethod
Describes the gradient fill method which is how the gradient is applied.

|Property | Value | Description |
|---------|--------|--------|
| Linear| 0| Linear - Change from one color to the next is linear across the geometry.
| Rectangular| 1| Rectangular - Change from one color to the next is rectangular, from the extent of the geometry.
| Circular| 2| Circular - Change from one color to the next is circular, from the extent of the geometry
| Buffered| 3| Buffered - Color changes based on an internal buffering of the geometry outline




## CIMGradientStroke
Represents a gradient stroke which draws linear geometry with a specified color scheme.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMStroke

|Property | Type | Description |
|---------|--------|--------|
| capStyle | [enumeration LineCapStyle](CIMSymbols.md#enumeration-linecapstyle)|How the stroke should draw at the ends of the geometries.
| joinStyle | [enumeration LineJoinStyle](CIMSymbols.md#enumeration-linejoinstyle)|How the symbol is drawn at the stroke segment connections.
| lineStyle3D | [enumeration Simple3DLineStyle](CIMSymbols.md#enumeration-simple3dlinestyle)|How strokes will be rendered in 3D.
| miterLimit | number //double|The maximum 'sharpness' that is allowed for Miter joins. If the spike created by the miter join exceeds the miter limit times the width of the stroke, the sharp angle will be clipped and rendered with a bevel join. This property is only applied to the symbol layer when the JoinType is set to Miter.
| width | number //double|The width of the stroke.
| closeCaps3D | boolean|A boolean indicating whether to close caps when drawing them in 3D. When set to false, the caps are hollow.


### CIMGradientStroke

|Property | Type | Description |
|---------|--------|--------|
| colorRamp | [ColorRamp](Types.md#colorramp)|The color scheme that is applied to the stroke.
| gradientMethod | [enumeration GradientStrokeMethod](CIMEnumerations.md#enumeration-gradientstrokemethod)|How the gradient is applied along the stroke.
| gradientSize | number //double|How much of the feature is covered by the color scheme. This is either a percentage of the total area which the color scheme spans or the number of page units from the starting point at which the gradient displays.
| gradientSizeUnits | [enumeration SymbolUnits](CIMSymbols.md#enumeration-symbolunits)|Whether GradientSize is applied with an absolute distance or a relative percentage.
| gradientType | [enumeration GradientStrokeType](CIMSymbols.md#enumeration-gradientstroketype)|Whether the gradient is applied with discrete or continuous intervals.
| interval | number //int32|How many bands draw when the GradientType is set to Discrete.





### Enumeration: GradientStrokeType
Gradient stroke types.

|Property | Value | Description |
|---------|--------|--------|
| Discrete| 0| Discrete gradient types have distinct lines of separation between each color.
| Continuous| 1| Continuous gradients vary continuously along the color change with no distinct boundary between the colors.




## CIMHatchFill
Represents a hatch fill which fills polygonal geometry with a uniform series of parallel line symbols.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMFill

|Property | Type | Description |
|---------|--------|--------|


### CIMHatchFill

|Property | Type | Description |
|---------|--------|--------|
| lineSymbol | [CIMLineSymbol](CIMSymbols.md#cimlinesymbol)|The line symbol that is used to draw the hatch lines in the fill.
| offsetX | number //double|How much to move the stroke to a new X-position.
| rotation | number //double|The angle of rotation for all the strokes, in degrees.
| separation | number //double|The distance between the line symbols in the hatch pattern.
| offsetY | number //double|How much to move the stroke to a new Y-position.





### Enumeration: HorizontalAlignment
Horizontal alignment types.

|Property | Value | Description |
|---------|--------|--------|
| Left| 0| Left aligned.
| Right| 1| Right aligned.
| Center| 2| Centered.
| Justify| 3| Justified alignment.



### Enumeration: LeaderLineStyle
The style of line to generate when a leader is drawn defined by an enumeration value. Line leaders will always be drawn with their own geometry.

|Property | Value | Description |
|---------|--------|--------|
| Base| 0| The line callout leader is a single line originating from the closest corner of the text box with the gap applied. If the callout has an accent bar it is connected to the closest point at the either top or bottom of the accent bar.
| MidPoint| 1| The line callout leader is a single line originating from the midpoint of the left or right side of the text box with the gap applied or from the midpoint of the accent bar if the callout has one.
| ThreePoint| 2| The line callout leader is a 3-point line originating from the midpoint of the left or right side of the text box with the gap applied or the midpoint of the accent bar if the callout has one.
| FourPoint| 3| The line callout leader is a 4-point line originating from the midpoint of the left or right side of the text box with the gap applied or the midpoint of the accent bar if the callout has one.
| Underline| 4| The line callout draws a line that connects to the closest of the four corners of the text with the gap applied. If the callout has an accent bar it is connected to the closest point at either the top or bottom of the accent bar. Additionally, either and underline or an "overline" is drawn along the closest side (bottom or top) of the text.
| CircularCW| 5| The line callout leader is curved (clockwise) from the anchor point to the closest corner of the text box with the gap applied. If the callout has an accent bar it is connected to the closest point at the either top or bottom of the accent bar.
| CircularCCW| 6| The line callout leader is curved (counter-clockwise) from the anchor point to the closest corner of the text box with the gap applied. If the callout has an accent bar it is connected to the closest point at the either top or bottom of the accent bar.



### Enumeration: LineCapStyle
The style of stroke ending caps.

|Property | Value | Description |
|---------|--------|--------|
| Butt| 0| Stroke ends in butt caps.
| Round| 1| Stroke ends in round caps.
| Square| 2| Stroke ends in square caps.



### Enumeration: LineDashEnding
Determines how the strokes with dash patterns and other patterns (tiled pictures, placement effects) are handled at the end points of the line geometry's segments. If more than one pattern exists (for example, a dashed simple stroke, a hash stroke, and a marker stroke) then the longest pattern's length is affected directly by this option and the rest of the stroke patterns are resized proportionately to match.

|Property | Value | Description |
|---------|--------|--------|
| NoConstraint| 0| No Constraint - no constraint is applied to how the dash is placed.
| HalfPattern| 1| Half Pattern - a half dash will be placed on either side of control points.
| HalfGap| 2| Half Gap - a space equal to the half the gap value will be placed on either side of control points.
| FullPattern| 3| Full Pattern - a full dash will be placed on either side of control points.
| FullGap| 4| Full Gap - a space equal to the gap value will be placed on either side of control points.
| Custom| 5| Custom - the pattern is fit to the length of the feature by adjusting the gaps slightly.



### Enumeration: LineDecorationStyle
Defines simple decorations for lines.

|Property | Value | Description |
|---------|--------|--------|
| None| -1| No decoration.
| Custom| 0| The decoration is defined in the Layers property as a set of SymbolReferences.
| Circle| 1| A circle is added at the end of the line.
| OpenArrow| 2| An open arrow is added to the end of the line.
| ClosedArrow| 3| A closed arrow is added to the end of the line.
| Diamond| 4| A diamond is added at the end of the line.



### Enumeration: LineGapType
Specifies the type of line gap (line spacing) that is applied.

|Property | Value | Description |
|---------|--------|--------|
| ExtraLeading| 0| Extra Leading - Adds the specified value to the line spacing that accommodates the largest font in the line
| Multiple| 1| Multiple - Sets the line spacing based on a multiple of the line.
| Exact| 2| Exact - Sets a fixed line spacing



### Enumeration: LineJoinStyle
Specifies how the symbol is drawn at the stroke segment connections.

|Property | Value | Description |
|---------|--------|--------|
| Bevel| 0| The stroke join is beveled.
| Round| 1| The line join is round.
| Miter| 2| The line join is mitered.




## CIMLineSymbol
Represents a line symbol which is used to draw polyline features or graphics.


### CIMSymbol

|Property | Type | Description |
|---------|--------|--------|


### CIMMultiLayerSymbol

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol.
| symbolLayers | [CIMSymbolLayer](Types.md#cimsymbollayer) |The symbol layers. Symbol layers are the components that make up a symbol. A symbol layer is represented by a stroke, fill, marker, or procedural symbol layer.
| thumbnailURI | string|The representative image of the symbol.
| useRealWorldSymbolSizes | boolean|A boolean indicating whether the symbol size properties are rendered using real world units or page units. When set to true the symbol will draw using real world units (e.g. meters).


### CIMLineSymbol

|Property | Type | Description |
|---------|--------|--------|






## CIMMarker3D
Represents a 3D marker which consists of one or more ShapeGraphics contained within one or more ShapeLODs. A 3DShape Marker is a way to describe a 3D model with different levels of detail at different zoom levels. The ShapeLODs represent the same model at different levels of detail. The ShapeGraphics referent a set of vertices, an optional texture URL, and material properties such as shininess to define a 3D model.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMMarker

|Property | Type | Description |
|---------|--------|--------|
| anchorPoint | [Point](ExternalReferences.md#point)|The specified location where all transformation property operations originate.
| anchorPointUnits | [enumeration SymbolUnits](CIMSymbols.md#enumeration-symbolunits)|A value which specifies if the anchor point location is considered a percentage of the size or as an absolute distance.
| angleX | number //double|The angle the marker is rotated around the X axis. This type of rotation is also referred to as tilt and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Tilt.
| angleY | number //double|The angle the marker is rotated around the Y axis. This type of rotation is also referred to as roll and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Roll.
| dominantSizeAxis3D | [enumeration DominantSizeAxis](CIMEnumerations.md#enumeration-dominantsizeaxis)|Which axis is considered as the Size in 3D. Only applicable when the marker layer is a 3DShapeMarker.
| offsetX | number //double|The value the marker is moved along the X axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetY | number //double|The value the marker is moved along the Y axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetZ | number //double|The value the marker is moved along the Z axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| rotateClockwise | boolean|A boolean indicating whether the rotation is applied clockwise or counterclockwise to the marker layer.
| rotation | number //double|The angle that the marker is rotated around the anchor point, in degrees.
| size | number //double|The height of the marker. Modifying Size changes the marker's height to the specified size and the width is updated proportionally.
| billboardMode3D | [enumeration BillboardMode](CIMEnumerations.md#enumeration-billboardmode)|The billboard mode of the marker.
| markerPlacement | [MarkerPlacement](Types.md#markerplacement)|The marker placements which determine how markers are placed along a line or within a polygon.


### CIM3DMarker

|Property | Type | Description |
|---------|--------|--------|
| LODLevels | [CIM3DMarkerLOD](CIMSymbols.md#cim3dmarkerlod) |The levels of detail.
| LODDistances | [number], //[double],|The level or detail viewing distances.
| width | number //double|The width of the 3D model
| depth | number //double|The depth of the 3D model.
| color | [Color](Types.md#color)|The color which defines the color that is applied to the marker.
| isRestricted | boolean|A boolean value indicating whether the model or textures are restricted. This prevents models or textures from being exported.
| shapeVertices | [string,]|An array of the vertices that define the shape.
| textures | [string,]|An array of the textures applied to the surface of the shape.
| thumbnail | string|The representative image of the marker.






## CIMMarkerGraphic
Represents a marker graphic which is used to define vector graphics in a vector marker.


### CIMMarkerGraphic

|Property | Type | Description |
|---------|--------|--------|
| geometry | [Geometry](ExternalReferences.md#geometry)|The geometry of the marker.
| symbol | [Symbol](Types.md#symbol)|The symbol used to draw the marker graphic, can be a point, line, polygon, or text symbol.
| textString | string|The text that is defined within the marker if drawn with a text symbol.
| primitiveName | string|The primitive name.






## CIMMarkerPlacementAlongLineRandomSize
Represents marker placement along the line which places randomly sized markers evenly along a line or polygon outline.


### CIMMarkerPlacement

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMMarkerStrokePlacement

|Property | Type | Description |
|---------|--------|--------|
| angleToLine | boolean|The angle to the line.
| offset | number //double|The offset.


### CIMMarkerPlacementAlongLine

|Property | Type | Description |
|---------|--------|--------|
| controlPointPlacement | [enumeration PlacementEndings](CIMSymbols.md#enumeration-placementendings)|How markers are placed at control points.
| customEndingOffset | number //double|Where the pattern should end relative to the ending point of the geometry. The entire pattern is shifted along the line for the specified distance. Negative numbers shift to the left and positive numbers shift to the right. This is only applied if the Endings property is set to Custom.
| endings | [enumeration PlacementEndings](CIMSymbols.md#enumeration-placementendings)|How markers are placed at the end points of a line.
| offsetAlongLine | number //double|Where the pattern should begin relative to the starting point of the geometry. The entire pattern is shifted along the line for the specified distance. Negative numbers shift to the left and positive numbers shift to the right. This is only applied if the Endings property is set to No Constraint or Custom.
| placementTemplate | [number], //[double],|The numeric pattern that defines the sequence of placed markers and the length of space between them.


### CIMMarkerPlacementAlongLineRandomSize

|Property | Type | Description |
|---------|--------|--------|
| randomization | [enumeration PlacementRandomlyAlongLineRandomization](CIMSymbols.md#enumeration-placementrandomlyalonglinerandomization)|The amount of randomness to be used for the size and rotation of the markers on the line. The size and rotation of the marker will vary for individual markers.
| seed | number //int32|The starting value for generating a random number. This random number is used by the Randomization property to determine the marker shape.






## CIMMarkerPlacementAlongLineSameSize
Represents marker placement along the line which places markers that are the same size evenly along a line or polygon outline.


### CIMMarkerPlacement

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMMarkerStrokePlacement

|Property | Type | Description |
|---------|--------|--------|
| angleToLine | boolean|The angle to the line.
| offset | number //double|The offset.


### CIMMarkerPlacementAlongLine

|Property | Type | Description |
|---------|--------|--------|
| controlPointPlacement | [enumeration PlacementEndings](CIMSymbols.md#enumeration-placementendings)|How markers are placed at control points.
| customEndingOffset | number //double|Where the pattern should end relative to the ending point of the geometry. The entire pattern is shifted along the line for the specified distance. Negative numbers shift to the left and positive numbers shift to the right. This is only applied if the Endings property is set to Custom.
| endings | [enumeration PlacementEndings](CIMSymbols.md#enumeration-placementendings)|How markers are placed at the end points of a line.
| offsetAlongLine | number //double|Where the pattern should begin relative to the starting point of the geometry. The entire pattern is shifted along the line for the specified distance. Negative numbers shift to the left and positive numbers shift to the right. This is only applied if the Endings property is set to No Constraint or Custom.
| placementTemplate | [number], //[double],|The numeric pattern that defines the sequence of placed markers and the length of space between them.


### CIMMarkerPlacementAlongLineSameSize

|Property | Type | Description |
|---------|--------|--------|






## CIMMarkerPlacementAlongLineVariableSize
Represents marker placement along the line which places markers in either increasing, decreasing or alternating gradations along a line or polygon outline.


### CIMMarkerPlacement

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMMarkerStrokePlacement

|Property | Type | Description |
|---------|--------|--------|
| angleToLine | boolean|The angle to the line.
| offset | number //double|The offset.


### CIMMarkerPlacementAlongLine

|Property | Type | Description |
|---------|--------|--------|
| controlPointPlacement | [enumeration PlacementEndings](CIMSymbols.md#enumeration-placementendings)|How markers are placed at control points.
| customEndingOffset | number //double|Where the pattern should end relative to the ending point of the geometry. The entire pattern is shifted along the line for the specified distance. Negative numbers shift to the left and positive numbers shift to the right. This is only applied if the Endings property is set to Custom.
| endings | [enumeration PlacementEndings](CIMSymbols.md#enumeration-placementendings)|How markers are placed at the end points of a line.
| offsetAlongLine | number //double|Where the pattern should begin relative to the starting point of the geometry. The entire pattern is shifted along the line for the specified distance. Negative numbers shift to the left and positive numbers shift to the right. This is only applied if the Endings property is set to No Constraint or Custom.
| placementTemplate | [number], //[double],|The numeric pattern that defines the sequence of placed markers and the length of space between them.


### CIMMarkerPlacementAlongLineVariableSize

|Property | Type | Description |
|---------|--------|--------|
| maxRandomOffset | number //double|The maximum random offset.
| maxZoom | number //double|The largest size of the marker to be placed on the line. The value is expressed as a ratio.
| minZoom | number //double|The smallest size of the marker to be placed on the line. The value is expressed as a ratio.
| numberOfSizes | number //int32|The number of different sizes of markers to be placed on the line.
| seed | number //int32|The starting value for generating a random number. This random number is used by the Randomization property to determine which size a marker will receive. This is only used if the VariationMethod is set to Random.
| variationMethod | [enumeration SizeVariationMethod](CIMSymbols.md#enumeration-sizevariationmethod)|The order in which the change of size in the markers should occur.






## CIMMarkerPlacementAtExtremities
Represents marker placement at extremities which places markers at only one or both endpoints of a line.


### CIMMarkerPlacement

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMMarkerStrokePlacement

|Property | Type | Description |
|---------|--------|--------|
| angleToLine | boolean|The angle to the line.
| offset | number //double|The offset.


### CIMMarkerPlacementAtExtremities

|Property | Type | Description |
|---------|--------|--------|
| extremityPlacement | [enumeration ExtremityPlacement](CIMSymbols.md#enumeration-extremityplacement)|Which ends of the line a marker will be placed.
| offsetAlongLine | number //double|The distance from the ends of a line that the marker will be placed.






## CIMMarkerPlacementAtMeasuredUnits
Represents marker placement at geometry M values.


### CIMMarkerPlacement

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMMarkerStrokePlacement

|Property | Type | Description |
|---------|--------|--------|
| angleToLine | boolean|The angle to the line.
| offset | number //double|The offset.


### CIMMarkerPlacementAtMeasuredUnits

|Property | Type | Description |
|---------|--------|--------|
| interval | number //double|The interval of measured units used to place markers.
| skipMarkerRate | number //int32|The rate of markers to skip.
| placeAtExtremities | boolean|A boolean indicating if markers should be placed at extremities.






## CIMMarkerPlacementAtRatioPositions
Represents marker placement at ratio positions which places a set number of markers along the line or the outline of a polygon.


### CIMMarkerPlacement

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMMarkerStrokePlacement

|Property | Type | Description |
|---------|--------|--------|
| angleToLine | boolean|The angle to the line.
| offset | number //double|The offset.


### CIMMarkerPlacementAtRatioPositions

|Property | Type | Description |
|---------|--------|--------|
| beginPosition | number //double|The distance from the beginning of a line that the marker will be placed.
| endPosition | number //double|The distance from the end of a line that the marker will be placed. The ending of a line is determined by the direction in which the line was digitized.
| flipFirst | boolean|A boolean indicating whether only the first marker will be rotated 180 degrees.
| positionArray | [number], //[double],|The array of positions.






## CIMMarkerPlacementInsidePolygon
Represents marker placement inside a polygon which defines how a polygon is filled with a pattern of markers.


### CIMMarkerPlacement

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMMarkerFillPlacement

|Property | Type | Description |
|---------|--------|--------|


### CIMMarkerPlacementInsidePolygon

|Property | Type | Description |
|---------|--------|--------|
| gridAngle | number //double|The orientation angle that the markers are placed on within the polygon.
| gridType | [enumeration PlacementGridType](CIMSymbols.md#enumeration-placementgridtype)|The grid type which defines how markers are placed.
| offsetX | number //double|The marker row offset horizontally.
| randomness | number //double|The randomness of the pattern when markers are placed randomly in a polygon.
| seed | number //int32|The starting value for generating a random pattern.
| shiftOddRows | boolean|A boolean value which indicates if every other row of markers should be shifted to create an offset grid.
| stepX | number //double|The distance between each marker on the X-axis of the grid.
| stepY | number //double|The distance between each marker on the Y-axis of the grid.
| offsetY | number //double|The marker row offset vertically.
| clipping | [enumeration PlacementClip](CIMSymbols.md#enumeration-placementclip)|The clipping option which specifies how markers should be clipped at the polygon boundary.






## CIMMarkerPlacementOnLine
Represents a marker placement on the line.


### CIMMarkerPlacement

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMMarkerStrokePlacement

|Property | Type | Description |
|---------|--------|--------|
| angleToLine | boolean|The angle to the line.
| offset | number //double|The offset.


### lCIMMarkerPlacementOnLine

|Property | Type | Description |
|---------|--------|--------|
| relativeTo | [enumeration PlacementOnLineRelativeTo](CIMSymbols.md#enumeration-placementonlinerelativeto)|The location on a line where a marker will be placed. The direction of the line is determined by the direction in which the line was digitized.
| startPointOffset | number //double|The distances from a specified location on a line that a marker will be placed.






## CIMMarkerPlacementOnVertices
Represents a marker placement on vertices which places a single marker on a line or polygon outline at a set distance from the middle or one of the endpoints.


### CIMMarkerPlacement

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMMarkerStrokePlacement

|Property | Type | Description |
|---------|--------|--------|
| angleToLine | boolean|The angle to the line.
| offset | number //double|The offset.


### CIMMarkerPlacementOnVertices

|Property | Type | Description |
|---------|--------|--------|
| placeOnControlPoints | boolean|A boolean indicating whether a marker will be placed on the control points of the line.
| placeOnEndPoints | boolean|A boolean indicating whether a marker will be placed on the endpoints of the line.
| placeOnRegularVertices | boolean|A boolean indicating whether a marker will be placed on the vertices of the line.






## CIMMarkerPlacementPolygonCenter
Represents marker placement polygon center which defines how a single marker will be placed within the polygon.


### CIMMarkerPlacement

|Property | Type | Description |
|---------|--------|--------|
| primitiveName | string|The primitive name.


### CIMMarkerFillPlacement

|Property | Type | Description |
|---------|--------|--------|


### CIMMarkerPlacementPolygonCenter

|Property | Type | Description |
|---------|--------|--------|
| method | [enumeration PlacementPolygonCenterMethod](CIMSymbols.md#enumeration-placementpolygoncentermethod)|The method used to determine the polygon center.
| offsetX | number //double|The value which offsets the marker horizontally from the center.
| offsetY | number //double|The value which offsets the marker vertically from the center.
| clipAtBoundary | boolean|A boolean value which indicates whether the marker should be clipped if it extends pasts the boundary of the polygon.





### Enumeration: MarkerPlacementType
Marker placement types.

|Property | Value | Description |
|---------|--------|--------|
| InsidePolygon| 0| Place inside the polygon.
| PolygonCenter| 1| Place inside the polygon at the center.
| RandomlyInsidePolygon| 2| Place randomly inside the polygon.



### Enumeration: MaterialMode
Material modes.

|Property | Value | Description |
|---------|--------|--------|
| Tint| 0| Tint materials and textures with color property.
| Replace| 1| Replace materials and textures with color property.
| Multiply| 2| Multiply materials and textures with color property.




## CIMMaterialProperties
Represents material properties.


### CIMMaterialProperties

|Property | Type | Description |
|---------|--------|--------|
| specularColor | [Color](Types.md#color)|The specular color.
| shininess | number //float|The shininess.
| externalColorMixMode | [enumeration ExternalColorMixMode](CIMSymbols.md#enumeration-externalcolormixmode)|How this material combines with externally defined colors.






## CIMMaterialSymbolLayer
Represents a material which defines how the multipatch or mesh is drawn.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMMaterialSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| color | [Color](Types.md#color)|The material color.
| materialMode | [enumeration MaterialMode](CIMSymbols.md#enumeration-materialmode)|Represents the mode in which the material is applied.






## CIMMeshSymbol
Represents a mesh symbol which is used to draw multipatch features or mesh features.


### CIMSymbol

|Property | Type | Description |
|---------|--------|--------|


### CIMMultiLayerSymbol

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol.
| symbolLayers | [CIMSymbolLayer](Types.md#cimsymbollayer) |The symbol layers. Symbol layers are the components that make up a symbol. A symbol layer is represented by a stroke, fill, marker, or procedural symbol layer.
| thumbnailURI | string|The representative image of the symbol.
| useRealWorldSymbolSizes | boolean|A boolean indicating whether the symbol size properties are rendered using real world units or page units. When set to true the symbol will draw using real world units (e.g. meters).


### CIMMeshSymbol

|Property | Type | Description |
|---------|--------|--------|






## CIMObjectMarker3D
Represents a marker symbol for 3D objects.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMMarker

|Property | Type | Description |
|---------|--------|--------|
| anchorPoint | [Point](ExternalReferences.md#point)|The specified location where all transformation property operations originate.
| anchorPointUnits | [enumeration SymbolUnits](CIMSymbols.md#enumeration-symbolunits)|A value which specifies if the anchor point location is considered a percentage of the size or as an absolute distance.
| angleX | number //double|The angle the marker is rotated around the X axis. This type of rotation is also referred to as tilt and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Tilt.
| angleY | number //double|The angle the marker is rotated around the Y axis. This type of rotation is also referred to as roll and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Roll.
| dominantSizeAxis3D | [enumeration DominantSizeAxis](CIMEnumerations.md#enumeration-dominantsizeaxis)|Which axis is considered as the Size in 3D. Only applicable when the marker layer is a 3DShapeMarker.
| offsetX | number //double|The value the marker is moved along the X axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetY | number //double|The value the marker is moved along the Y axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetZ | number //double|The value the marker is moved along the Z axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| rotateClockwise | boolean|A boolean indicating whether the rotation is applied clockwise or counterclockwise to the marker layer.
| rotation | number //double|The angle that the marker is rotated around the anchor point, in degrees.
| size | number //double|The height of the marker. Modifying Size changes the marker's height to the specified size and the width is updated proportionally.
| billboardMode3D | [enumeration BillboardMode](CIMEnumerations.md#enumeration-billboardmode)|The billboard mode of the marker.
| markerPlacement | [MarkerPlacement](Types.md#markerplacement)|The marker placements which determine how markers are placed along a line or within a polygon.


### CIMObjectMarker3D

|Property | Type | Description |
|---------|--------|--------|
| modelURI | string|The URI of the binary reference containing the "web resource".
| width | number //double|The marker width.
| depth | number //double|The marker depth.
| tintColor | [Color](Types.md#color)|The color which defines the color that is applied to the marker.
| isRestricted | boolean|A boolean value indicating whether the model can be exported.
| thumbnail | string|The representative image of the marker.
| useAnchorPoint | boolean|A boolean indicating whether to ignore ICIMMarker.AnchorPoint and insert the model directly at the data point.






## CIMPictureFill
Represents a picture fill which fills polygonal geometry with a picture. Supported file types are .bmp, .jpg, .png, and .gif.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMFill

|Property | Type | Description |
|---------|--------|--------|


### CIMPictureFill

|Property | Type | Description |
|---------|--------|--------|
| URL | string|The URL of the image. Typcially a base64 encoded image.
| offsetX | number //double|The distance that the image is offset in the horizontal direction.
| offsetY | number //double|The distance that the image is offset in the vertical direction.
| rotation | number //double|The angle of the image within the fill.
| scaleX | number //double|The width of the symbol without changing the height (or depth in 3D), as a ratio.
| height | number //double|The height of the image.
| textureFilter | [enumeration TextureFilter](CIMSymbols.md#enumeration-texturefilter)|How the image is resampled.
| colorSubstitutions | [CIMColorSubstitution](CIMSymbols.md#cimcolorsubstitution) |The color substitutions which allows colors in the image to be substituted with a different color.
| tintColor | [Color](Types.md#color)|The color that is applied as a tint to the image. The color is applied to the whole image. When the tint is set to white the image appears with its native colors.






## CIMPictureMarker
Represents a picture marker created from a raster (bitmapped) image file. The image can have color substitutions to replace one or more colors in the image or it can have a tint applied to the whole image depending on the picture type. Supported formats are .bmp, .jpg, .png, and .gif.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMMarker

|Property | Type | Description |
|---------|--------|--------|
| anchorPoint | [Point](ExternalReferences.md#point)|The specified location where all transformation property operations originate.
| anchorPointUnits | [enumeration SymbolUnits](CIMSymbols.md#enumeration-symbolunits)|A value which specifies if the anchor point location is considered a percentage of the size or as an absolute distance.
| angleX | number //double|The angle the marker is rotated around the X axis. This type of rotation is also referred to as tilt and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Tilt.
| angleY | number //double|The angle the marker is rotated around the Y axis. This type of rotation is also referred to as roll and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Roll.
| dominantSizeAxis3D | [enumeration DominantSizeAxis](CIMEnumerations.md#enumeration-dominantsizeaxis)|Which axis is considered as the Size in 3D. Only applicable when the marker layer is a 3DShapeMarker.
| offsetX | number //double|The value the marker is moved along the X axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetY | number //double|The value the marker is moved along the Y axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetZ | number //double|The value the marker is moved along the Z axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| rotateClockwise | boolean|A boolean indicating whether the rotation is applied clockwise or counterclockwise to the marker layer.
| rotation | number //double|The angle that the marker is rotated around the anchor point, in degrees.
| size | number //double|The height of the marker. Modifying Size changes the marker's height to the specified size and the width is updated proportionally.
| billboardMode3D | [enumeration BillboardMode](CIMEnumerations.md#enumeration-billboardmode)|The billboard mode of the marker.
| markerPlacement | [MarkerPlacement](Types.md#markerplacement)|The marker placements which determine how markers are placed along a line or within a polygon.


### CIMPictureMarker

|Property | Type | Description |
|---------|--------|--------|
| colorSubstitutions | [CIMColorSubstitution](CIMSymbols.md#cimcolorsubstitution) |The color substitutions for the picture.
| depth3D | number //double|The depth of the image when drawn in 3D.
| invertBackfaceTexture | boolean|A boolean indicating whether the image is right-reading when viewed from behind.
| scaleX | number //double|The scale X which changes the width of the symbol without changing the height (or depth in 3D), as a ratio.
| textureFilter | [enumeration TextureFilter](CIMSymbols.md#enumeration-texturefilter)|How the image is resampled.
| tintColor | [Color](Types.md#color)|The color that is applied as a tint to the image. The color is applied to the whole image. When the tint is set to white the image appears with its native colors
| URL | string|The image that is used in the symbol layer. Typically a base64 encoded image.
| verticalOrientation3D | boolean|A boolean value indicating if the marker stands upright as though locked in place. The marker can be viewed from all angles.






## CIMPictureStroke
Represents a picture stroke which draws linear geometry with a repeating image file. Supported file types are .bmp, .jpg, .png, and .gif.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMStroke

|Property | Type | Description |
|---------|--------|--------|
| capStyle | [enumeration LineCapStyle](CIMSymbols.md#enumeration-linecapstyle)|How the stroke should draw at the ends of the geometries.
| joinStyle | [enumeration LineJoinStyle](CIMSymbols.md#enumeration-linejoinstyle)|How the symbol is drawn at the stroke segment connections.
| lineStyle3D | [enumeration Simple3DLineStyle](CIMSymbols.md#enumeration-simple3dlinestyle)|How strokes will be rendered in 3D.
| miterLimit | number //double|The maximum 'sharpness' that is allowed for Miter joins. If the spike created by the miter join exceeds the miter limit times the width of the stroke, the sharp angle will be clipped and rendered with a bevel join. This property is only applied to the symbol layer when the JoinType is set to Miter.
| width | number //double|The width of the stroke.
| closeCaps3D | boolean|A boolean indicating whether to close caps when drawing them in 3D. When set to false, the caps are hollow.


### CIMPictureStroke

|Property | Type | Description |
|---------|--------|--------|
| colorSubstitutions | [CIMColorSubstitution](CIMSymbols.md#cimcolorsubstitution) |The color substitutions for the picture.
| textureFilter | [enumeration TextureFilter](CIMSymbols.md#enumeration-texturefilter)|How the image is resampled.
| URL | string|The image that is used in the symbol layer. Typically a base64 encoded image.
| tintColor | [Color](Types.md#color)|The color that is applied as a tint to the image. The color is applied to the whole image. When the tint is set to white the image appears with its native colors






## CIMPieChartMarker
Represents a pie chart marker which is a marker that draws numeric values arranged in a circle.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMMarker

|Property | Type | Description |
|---------|--------|--------|
| anchorPoint | [Point](ExternalReferences.md#point)|The specified location where all transformation property operations originate.
| anchorPointUnits | [enumeration SymbolUnits](CIMSymbols.md#enumeration-symbolunits)|A value which specifies if the anchor point location is considered a percentage of the size or as an absolute distance.
| angleX | number //double|The angle the marker is rotated around the X axis. This type of rotation is also referred to as tilt and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Tilt.
| angleY | number //double|The angle the marker is rotated around the Y axis. This type of rotation is also referred to as roll and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Roll.
| dominantSizeAxis3D | [enumeration DominantSizeAxis](CIMEnumerations.md#enumeration-dominantsizeaxis)|Which axis is considered as the Size in 3D. Only applicable when the marker layer is a 3DShapeMarker.
| offsetX | number //double|The value the marker is moved along the X axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetY | number //double|The value the marker is moved along the Y axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetZ | number //double|The value the marker is moved along the Z axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| rotateClockwise | boolean|A boolean indicating whether the rotation is applied clockwise or counterclockwise to the marker layer.
| rotation | number //double|The angle that the marker is rotated around the anchor point, in degrees.
| size | number //double|The height of the marker. Modifying Size changes the marker's height to the specified size and the width is updated proportionally.
| billboardMode3D | [enumeration BillboardMode](CIMEnumerations.md#enumeration-billboardmode)|The billboard mode of the marker.
| markerPlacement | [MarkerPlacement](Types.md#markerplacement)|The marker placements which determine how markers are placed along a line or within a polygon.


### CIMChartMarker

|Property | Type | Description |
|---------|--------|--------|
| display3D | boolean|A boolean value which indicates whether to draw the chart with a 3D perspective.
| parts | [CIMChartPart](CIMSymbols.md#cimchartpart) |The individual components of the chart marker.
| thickness3D | number //double|The thickness or depth of a chart. Only applied when Display3D is true.
| tilt3D | number //double|The tilt (rotation around the X axis) of the chart. Only applied when Display3D is true.


### CIMPieChartMarker

|Property | Type | Description |
|---------|--------|--------|
| clockwise | boolean|A boolean indicating whether the orientation of the wedges of the pie chart are clockwise or counterclockwise.
| outlineSymbol | [CIMLineSymbol](CIMSymbols.md#cimlinesymbol)|The line symbol that is applied to outline of the whole pie chart.





### Enumeration: PlacementClip
Options for how the markers should be clipped at the polygon boundary.

|Property | Value | Description |
|---------|--------|--------|
| ClipAtBoundary| 0| Markers are clipped at the boundary of the polygon.
| RemoveIfCenterOutsideBoundary| 1| Markers are not drawn if their center falls outside of the polygon.
| DoNotTouchBoundary| 2| Markers are not drawn if they touch the boundary of the polygon.
| DoNotClip| 3| Markers are not clipped and may extend past the boundary of the polygon.



### Enumeration: PlacementEndings
Options for how markers are placed at control points.

|Property | Value | Description |
|---------|--------|--------|
| NoConstraint| 0| No constraint on how the markers are placed.
| WithMarkers| 1| A marker is placed at the control point.
| WithFullGap| 2| A space equal to the placement template will be placed at the control point.
| WithHalfGap| 3| A space equal to half the placement template will be placed at the control point.
| Custom| 4| Will fit the pattern to the length of the features by adjusting the gaps slightly.



### Enumeration: PlacementGridType
Options for how markers are placed in a uniform grid or randomly.

|Property | Value | Description |
|---------|--------|--------|
| Fixed| 0| Markers are placed on a uniform grid.
| Random| 1| Markers are placed randomly in the polygon.
| RandomFixedQuantity| 2| Markers are placed randomly with a fixed quanity (dot density).



### Enumeration: PlacementOnLineRelativeTo
Options for the location on a line where a marker will be placed.

|Property | Value | Description |
|---------|--------|--------|
| LineMiddle| 0| Marker is placed in the middle of the line.
| LineBeginning| 1| Marker is placed at the beginning of the line.
| LineEnd| 2| Marker is placed at the end of the line.
| SegmentMidpoint| 3| Marker is at the midpoint of each segment in a line feature.



### Enumeration: PlacementPolygonCenterMethod
Options for how a single marker will be placed within the polygon.

|Property | Value | Description |
|---------|--------|--------|
| OnPolygon| 0| Place on the polygon.
| CenterOfMass| 1| The centroid of the polygon is used.
| BoundingBoxCenter| 2| The bounding box of the polygon is used.



### Enumeration: PlacementRandomlyAlongLineRandomization
Options for the amount of randomness to be used for the size and rotation of the markers on the line.

|Property | Value | Description |
|---------|--------|--------|
| Low| 0| A low amount of randomness is applied
| Medium| 1| A medium amount of randomness is applied
| High| 2| A high amount of randomness is applied



### Enumeration: PlacementStepPosition
Options for the placement step position.

|Property | Value | Description |
|---------|--------|--------|
| MarkerCenter| 0| The marker center.
| MarkerBounds| 1| The marker bounds.




## CIMPointSymbol
Represents a point symbol used to draw point features and point graphics.


### CIMSymbol

|Property | Type | Description |
|---------|--------|--------|


### CIMMultiLayerSymbol

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol.
| symbolLayers | [CIMSymbolLayer](Types.md#cimsymbollayer) |The symbol layers. Symbol layers are the components that make up a symbol. A symbol layer is represented by a stroke, fill, marker, or procedural symbol layer.
| thumbnailURI | string|The representative image of the symbol.
| useRealWorldSymbolSizes | boolean|A boolean indicating whether the symbol size properties are rendered using real world units or page units. When set to true the symbol will draw using real world units (e.g. meters).


### CIMPointSymbol

|Property | Type | Description |
|---------|--------|--------|
| callout | [Callout](Types.md#callout)|The callout of the point symbol.
| haloSize | number //double|The size of the halo that extends beyond the symbol shape.
| haloSymbol | [CIMPolygonSymbol](CIMSymbols.md#cimpolygonsymbol)|The polygon symbol that is used to draw the halo for a point symbol.
| primitiveName | string|The primitive name.
| scaleX | number //double|The X scale which changes the width of the symbol without changing the height (or depth in 3D), as a ratio.
| symbol3DProperties | [CIM3DSymbolProperties](CIMSymbols.md#cim3dsymbolproperties)|The collection of symbol properties that apply when the symbol is used in a 3D context.
| angle | number //double|The amount of variation applied to the symbol, measured in degrees, propagated cumulatively to all marker symbols.
| angleAlignment | [enumeration AngleAlignment](CIMSymbols.md#enumeration-anglealignment)|Whether point symbols align to the map or to the display when a rotation is applied to the map.






## CIMPointSymbolCallout
Represents a point symbol callout which draws a point symbol as the background and a line symbol for leaders. Often used for highway shields.


### CIMCallout

|Property | Type | Description |
|---------|--------|--------|
| leaderTolerance | number //double|The leader tolerance which is the closest distance (in points) to the text the anchor point can be for the callout to draw.
| leaderOffset | number //double|The leader offset which is an offset value defining the distance (in points) between the anchor point and the beginning of the drawn leader.


### CIMLineCallout

|Property | Type | Description |
|---------|--------|--------|
| leaderLineSymbol | [CIMLineSymbol](CIMSymbols.md#cimlinesymbol)|The line symbol to draw leaders with.
| gap | number //double|The gap (in points) between the point symbol and the beginning of the leader line.
| lineStyle | [enumeration LeaderLineStyle](CIMSymbols.md#enumeration-leaderlinestyle)|The style of line to generate when a Point leader is drawn defined by an enumeration value. Line leaders will always be drawn with their own geometry.


### CIMPointSymbolCallout

|Property | Type | Description |
|---------|--------|--------|
| pointSymbol | [CIMPointSymbol](CIMSymbols.md#cimpointsymbol)|The symbol that will be drawn as the background behind the text. The most common use case for this type of symbol is a highway shield. When drawing a highway shield this property will be the shield itself without numbers.
| backgroundScale | [enumeration PointSymbolCalloutScale](CIMSymbols.md#enumeration-pointsymbolcalloutscale)|An enumeration value that defines how the background is scaled to fit the dimensions of the symbol.





### Enumeration: PointSymbolCalloutScale
An enumeration that defines how the background point symbol is scaled to fit the dimensions of the text.

|Property | Value | Description |
|---------|--------|--------|
| None| 0| No scaling.
| PropUniform| 1| Uniform scaling.
| PropNonuniform| 2| Non-uniform scaling.
| DifUniform| 3| Uniform scaling.
| DifNonuniform| 4| Non-uniform scaling.




## CIMPolygonSymbol
Represents a polygon symbol which is used to draw polygon features or polygon graphics.


### CIMSymbol

|Property | Type | Description |
|---------|--------|--------|


### CIMMultiLayerSymbol

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol.
| symbolLayers | [CIMSymbolLayer](Types.md#cimsymbollayer) |The symbol layers. Symbol layers are the components that make up a symbol. A symbol layer is represented by a stroke, fill, marker, or procedural symbol layer.
| thumbnailURI | string|The representative image of the symbol.
| useRealWorldSymbolSizes | boolean|A boolean indicating whether the symbol size properties are rendered using real world units or page units. When set to true the symbol will draw using real world units (e.g. meters).


### CIMPolygonSymbol

|Property | Type | Description |
|---------|--------|--------|






## CIMProceduralSymbolLayer
Represents a procedural symbol layer which defines rendering using script-based logic to construct complex 3D objects and textures from simple geometries. Properties of the symbol are derived from a rule package (.rpk file).


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMProceduralSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| attributes | [CIMCGAAttribute](CIMSymbols.md#cimcgaattribute) |The symbol attributes as specified by the CGA code in the rule package.
| rulePackage | string|The URI of the referenced rule package file.
| rulePackageName | string|The name of the package displayed in the user interface.






## CIMShapeVertex
Represents a shape vertex. Each Vertex in a 3DShapeGraphic is represented by three points, contained in a ShapeVertex. The first point is the actual position of the Vertex. The second represents the normalized vector that describes the orientation of the point. The last point is optional - it defines the coordinates of the texture that correspond with this point in the shape. In this case only x and y are used as the traditional texture coordinates S and T.


### CIMShapeVertex

|Property | Type | Description |
|---------|--------|--------|
| position | [Point](ExternalReferences.md#point)|The position.
| normalVector | [Point](ExternalReferences.md#point)|The normal vector.
| textureCoordinate | [Point](ExternalReferences.md#point)|The texture coordinate.






## CIMShapeVertices
Represents shape vertices.


### CIMShapeVertices

|Property | Type | Description |
|---------|--------|--------|
| indices | number //int32|The indices.
| shapes | string|The shape.





### Enumeration: Simple3DLineStyle
Simple 3D line styles which define how strokes will be rendered in 3D.

|Property | Value | Description |
|---------|--------|--------|
| Tube| 0| Stroke draws as a tube where the width determines the diameter of the tube.
| Strip| 1| Stroke draws flat upon the surface.
| Wall| 2| Stroke is vertically oriented where Width determines the height of the wall.




## CIMSimpleLineCallout
Represents a simple line callout for drawing basic leader lines.


### CIMCallout

|Property | Type | Description |
|---------|--------|--------|
| leaderTolerance | number //double|The leader tolerance which is the closest distance (in points) to the text the anchor point can be for the callout to draw.
| leaderOffset | number //double|The leader offset which is an offset value defining the distance (in points) between the anchor point and the beginning of the drawn leader.


### CIMSimpleLineCallout

|Property | Type | Description |
|---------|--------|--------|
| lineSymbol | [CIMLineSymbol](CIMSymbols.md#cimlinesymbol)|The line symbol used to draw leader lines.
| autoSnap | boolean|A boolean indicating whether or not to autosnap the line leaders to the text.





### Enumeration: SizeVariationMethod
Size variation methods which define the order in which the change of size in the markers should occur.

|Property | Value | Description |
|---------|--------|--------|
| Random| 0| Change in size is applied randomly.
| Increasing| 1| Markers are drawn with a pattern where the markers increase in size.
| Decreasing| 2| Markers are drawn in a pattern where the markers decrease in size.
| IncreasingThenDecreasing| 3| Markers are drawn in a pattern where the size increase and then decrease.




## CIMSolidFill
Represents a solid fill which fills polygonal geometry with a single solid color.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMFill

|Property | Type | Description |
|---------|--------|--------|


### CIMSolidFill

|Property | Type | Description |
|---------|--------|--------|
| color | [Color](Types.md#color)|The color that is applied to the fill.






## CIMSolidStroke
Represents a solid stroke which draws linear geometry with a single solid color.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMStroke

|Property | Type | Description |
|---------|--------|--------|
| capStyle | [enumeration LineCapStyle](CIMSymbols.md#enumeration-linecapstyle)|How the stroke should draw at the ends of the geometries.
| joinStyle | [enumeration LineJoinStyle](CIMSymbols.md#enumeration-linejoinstyle)|How the symbol is drawn at the stroke segment connections.
| lineStyle3D | [enumeration Simple3DLineStyle](CIMSymbols.md#enumeration-simple3dlinestyle)|How strokes will be rendered in 3D.
| miterLimit | number //double|The maximum 'sharpness' that is allowed for Miter joins. If the spike created by the miter join exceeds the miter limit times the width of the stroke, the sharp angle will be clipped and rendered with a bevel join. This property is only applied to the symbol layer when the JoinType is set to Miter.
| width | number //double|The width of the stroke.
| closeCaps3D | boolean|A boolean indicating whether to close caps when drawing them in 3D. When set to false, the caps are hollow.


### CIMSolidStroke

|Property | Type | Description |
|---------|--------|--------|
| color | [Color](Types.md#color)|The color that is applied to the stroke.






## CIMStackedBarChartMarker
Represents a stacked bar chart marker which is a chart made of vertical stacked bars displaying values.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMMarker

|Property | Type | Description |
|---------|--------|--------|
| anchorPoint | [Point](ExternalReferences.md#point)|The specified location where all transformation property operations originate.
| anchorPointUnits | [enumeration SymbolUnits](CIMSymbols.md#enumeration-symbolunits)|A value which specifies if the anchor point location is considered a percentage of the size or as an absolute distance.
| angleX | number //double|The angle the marker is rotated around the X axis. This type of rotation is also referred to as tilt and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Tilt.
| angleY | number //double|The angle the marker is rotated around the Y axis. This type of rotation is also referred to as roll and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Roll.
| dominantSizeAxis3D | [enumeration DominantSizeAxis](CIMEnumerations.md#enumeration-dominantsizeaxis)|Which axis is considered as the Size in 3D. Only applicable when the marker layer is a 3DShapeMarker.
| offsetX | number //double|The value the marker is moved along the X axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetY | number //double|The value the marker is moved along the Y axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetZ | number //double|The value the marker is moved along the Z axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| rotateClockwise | boolean|A boolean indicating whether the rotation is applied clockwise or counterclockwise to the marker layer.
| rotation | number //double|The angle that the marker is rotated around the anchor point, in degrees.
| size | number //double|The height of the marker. Modifying Size changes the marker's height to the specified size and the width is updated proportionally.
| billboardMode3D | [enumeration BillboardMode](CIMEnumerations.md#enumeration-billboardmode)|The billboard mode of the marker.
| markerPlacement | [MarkerPlacement](Types.md#markerplacement)|The marker placements which determine how markers are placed along a line or within a polygon.


### CIMChartMarker

|Property | Type | Description |
|---------|--------|--------|
| display3D | boolean|A boolean value which indicates whether to draw the chart with a 3D perspective.
| parts | [CIMChartPart](CIMSymbols.md#cimchartpart) |The individual components of the chart marker.
| thickness3D | number //double|The thickness or depth of a chart. Only applied when Display3D is true.
| tilt3D | number //double|The tilt (rotation around the X axis) of the chart. Only applied when Display3D is true.


### CIMStackedBarChartMarker

|Property | Type | Description |
|---------|--------|--------|
| fixedLength | boolean|A boolean indicating whether this chart is a fixed length.
| outlineSymbol | [CIMLineSymbol](CIMSymbols.md#cimlinesymbol)|The outline symbol.
| verticalBar | boolean|A boolean indicating whether this chart has a vertical bar.
| width | number //double|The width.





### Enumeration: SymbolUnits
Symbol unit types.

|Property | Value | Description |
|---------|--------|--------|
| Relative| 0| Relative units.
| Absolute| 1| Absolute units.



### Enumeration: TextCase
The letter case used to draw text.

|Property | Value | Description |
|---------|--------|--------|
| Normal| 0| Text is proper/mixed case.
| LowerCase| 1| Text is all lower case.
| Allcaps| 2| Text is all upper case.




## CIMTextMargin
Represents a text margin which defines the margin to apply around text.


### CIMTextMargin

|Property | Type | Description |
|---------|--------|--------|
| left | number //double|The left margin.
| right | number //double|The right margin.
| top | number //double|The top margin.
| bottom | number //double|The bottom margin.





### Enumeration: TextReadingDirection
Text reading directions.

|Property | Value | Description |
|---------|--------|--------|
| LTR| 0| Text is drawn from left-to-right.
| RTL| 1| Text is drawn from right-to-left.




## CIMTextSymbol
Represents a text symbol which is used to draw text graphics, bleeds, and annotation. Text symbols do not contain any symbol layers but can have callouts.


### CIMSymbol

|Property | Type | Description |
|---------|--------|--------|


### CIMTextSymbol

|Property | Type | Description |
|---------|--------|--------|
| angle | number //double|The amount of rotation applied to the text symbol, measured in degrees, around the geometry.
| angleX | number //double|The amount of rotation of the text symbol around the X axis, measured in degrees, around the geometry. This type of rotation is also referred to as tilt. It is applied in 3D.
| angleY | number //double|The amount of rotation of the text symbol around the Y axis, measured in degrees, around the geometry. This type of rotation is also referred to as roll. It is applied in 3D.
| blockProgression | [enumeration BlockProgression](CIMSymbols.md#enumeration-blockprogression)|The direction in which multi-line text is stacked.
| callout | [Callout](Types.md#callout)|The callout or background of the text with optional leader lines.
| compatibilityMode | boolean|A boolean indicating whether to draw the text in a fashion compatible with ArcMap.
| countryISO | string|The ISO code for the base country of the text.
| depth3D | number //double|The depth of the glyph when drawn in 3D. This is an extrusion of the characters of the text in the Z axis.
| drawGlyphsAsGeometry | boolean|A boolean indicating whether fonts that are drawn as rasters at some scales to draw as vectors instead.
| drawSoftHyphen | boolean|A boolean indicating whether soft hyphens should be drawn. Soft hyphens are invisible markers that indicate where a hyphenated break is allowed within the text. They are only drawn if there is word wrapping at the end of a line.
| extrapolateBaselines | boolean|A boolean indicating whether the baseline of the text geometry should be expanded in the same manner as the existing geometry if the text extends beyond the baseline.
| flipAngle | number //double|The angle (in degrees from vertical) at which point rotated text is flipped (mirrored) in place.
| fontEffects | [enumeration FontEffects](CIMSymbols.md#enumeration-fonteffects)|Whether the text is drawn as subscript or superscript.
| fontEncoding | [enumeration FontEncoding](CIMSymbols.md#enumeration-fontencoding)|The font encoding.
| fontFamilyName | string|The font family name of the font. e.g. Comic Sans.
| fontStyleName | string|The style name for the font family. e.g. Regular, Bold, or Italic.
| fontType | [enumeration FontType](CIMSymbols.md#enumeration-fonttype)|The type of font that the font family/style name reference.
| glyphRotation | number //double|An additional rotation that is applied to the individual glyphs contained in the text. This is applied to the individual glyphs whereas Angle, AngleX and AngleY are affect how the entire text string is oriented
| haloSize | number //double|The size of the halo that extends beyond the symbol shape.
| haloSymbol | [CIMPolygonSymbol](CIMSymbols.md#cimpolygonsymbol)|The polygon symbol that is used to draw the halo for a text symbol.
| height | number //double|The size of the text in points.
| hinting | [enumeration GlyphHinting](CIMSymbols.md#enumeration-glyphhinting)|Type of hinting from the font that is used for text rendering. Hinting is information included with most fonts to effectively fit the vector glyphs of the font into the raster grid onto which they are displayed.
| horizontalAlignment | [enumeration HorizontalAlignment](CIMSymbols.md#enumeration-horizontalalignment)|The alignment type used to align the text to the geometry horizontally. Affects which side of a point geometry the point text is drawn or which end of a line it is drawn close to. Commonly used to define how stacked text appears.
| indentAfter | number //double|How many points to indent the text back from the end of the baseline.
| indentBefore | number //double|How many points to indent the text from the beginning of the baseline.
| indentFirstLine | number //double|How many points to indent the text from the beginning of the baseline for the first line only.
| kerning | boolean|A boolean indicating whether the text is drawn with metric kerning, which adjusts the spacing between individual letter forms.
| languageISO | string|Whether the ISO code for the base language of the text
| letterSpacing | number //double|The additional spacing that is added to each glyph beyond what is defined by its character box in the font. Value indicates the percentage of a glyph's width. Also known as tracking.
| letterWidth | number //double|The width that is added to each glyph beyond what is defined by its character box in its font. This is a percentage of the original glyph.
| ligatures | boolean|A boolean indicating whether text is to be drawn with ligatures, which occur when two or more letters or portions of letters are joined to form a single glyph.
| lineGap | number //double|The spacing between lines of text. This is also known as leading or line spacing.
| lineGapType | [enumeration LineGapType](CIMSymbols.md#enumeration-linegaptype)|The type of line gap that is applied.
| offsetX | number //double|The X offset.
| offsetY | number //double|The Y offset.
| offsetZ | number //double|The Z offset.
| shadowColor | [Color](Types.md#color)|The color of the shadow that is defined for the text symbol. The shadow is drawn as an offset copy of the text.
| shadowOffsetX | number //double|The shadow offset from the text symbol in the horizontal direction. If X and Y are zero, not shadow is drawn.
| shadowOffsetY | number //double|The shadow offset from the text symbol in the vertical direction. If X and Y are zero, not shadow is drawn.
| smallCaps | boolean|A boolean indicating whether the text should be drawn as Small Capitals, where lower case text is converted to small caps and upper case text is left as upper case.
| strikethrough | boolean|A boolean indicating whether to draw the text with a strike through it.
| symbol | [CIMPolygonSymbol](CIMSymbols.md#cimpolygonsymbol)|The polygon symbol that is used to draw the glyphs of the text.
| symbol3DProperties | [CIM3DSymbolProperties](CIMSymbols.md#cim3dsymbolproperties)|The collection of properties that are applied to the text symbol only in a 3D context.
| textCase | [enumeration TextCase](CIMSymbols.md#enumeration-textcase)|The letter case used to draw the text.
| textDirection | [enumeration TextReadingDirection](CIMSymbols.md#enumeration-textreadingdirection)|The base text direction to draw the text.
| underline | boolean|A boolean indicating whether to draw the text with an underline.
| verticalAlignment | [enumeration VerticalAlignment](CIMSymbols.md#enumeration-verticalalignment)|The vertical alignment of the text.
| verticalGlyphOrientation | [enumeration VerticalGlyphOrientation](CIMSymbols.md#enumeration-verticalglyphorientation)|The orientation for the non-vertical text in a vertical layout. For example, an English fragment in a Japanese text.
| wordSpacing | number //double|The additional spacing that is added to between the words of the text string. 100% indicates that regular spacing is used.
| billboardMode3D | [enumeration BillboardMode](CIMEnumerations.md#enumeration-billboardmode)|The billboard mode of the text symbol.





### Enumeration: TextureFilter
Texture filter types.

|Property | Value | Description |
|---------|--------|--------|
| Draft| 0| Low draft quality.
| Picture| 1| Higher quality, recommended for pictures.
| Text| 2| Higher quality, recommended when it is important to preserve edges for zoomed in images.




## CIMVectorMarker
Represents a vector marker which can represent vector graphics. It's constructed from MarkerGraphics which are geometries and symbols used as building blocks for the marker.


### CIMSymbolLayer

|Property | Type | Description |
|---------|--------|--------|
| effects | [CIMGeometricEffect](Types.md#cimgeometriceffect) |The geometric effects that are applied to the symbol layer. Effects dynamically alter the feature geometry when the symbology is applied. Multiple effects applied to a symbol layer are rendered sequentially.
| enable | boolean|A boolean indicating whether the symbol layer is visible. The symbol layer draws only when enabled. Currently, an invisible layer is not considered in any transformations when in a 3D context.
| name | string|The internal name of the symbol layer used for symbol level drawing.
| colorLocked | boolean|A boolean indicating whether the color set at the basic properties level is applied to the symbol layer. If the symbol layer is color locked then changes made to the color in the basic properties will not be applied to the symbol layer.
| primitiveName | string|The primitive name.


### CIMMarker

|Property | Type | Description |
|---------|--------|--------|
| anchorPoint | [Point](ExternalReferences.md#point)|The specified location where all transformation property operations originate.
| anchorPointUnits | [enumeration SymbolUnits](CIMSymbols.md#enumeration-symbolunits)|A value which specifies if the anchor point location is considered a percentage of the size or as an absolute distance.
| angleX | number //double|The angle the marker is rotated around the X axis. This type of rotation is also referred to as tilt and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Tilt.
| angleY | number //double|The angle the marker is rotated around the Y axis. This type of rotation is also referred to as roll and is only applied in 3D. The order of how this is applied with respect to other rotations depends on the RotationOrder3D. The name in the user interface is Roll.
| dominantSizeAxis3D | [enumeration DominantSizeAxis](CIMEnumerations.md#enumeration-dominantsizeaxis)|Which axis is considered as the Size in 3D. Only applicable when the marker layer is a 3DShapeMarker.
| offsetX | number //double|The value the marker is moved along the X axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetY | number //double|The value the marker is moved along the Y axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| offsetZ | number //double|The value the marker is moved along the Z axis from the anchor point. This is applied after all rotation, as opposed to anchor point which is applied before the rotation.
| rotateClockwise | boolean|A boolean indicating whether the rotation is applied clockwise or counterclockwise to the marker layer.
| rotation | number //double|The angle that the marker is rotated around the anchor point, in degrees.
| size | number //double|The height of the marker. Modifying Size changes the marker's height to the specified size and the width is updated proportionally.
| billboardMode3D | [enumeration BillboardMode](CIMEnumerations.md#enumeration-billboardmode)|The billboard mode of the marker.
| markerPlacement | [MarkerPlacement](Types.md#markerplacement)|The marker placements which determine how markers are placed along a line or within a polygon.


### CIMVectorMarker

|Property | Type | Description |
|---------|--------|--------|
| depth3D | number //double|The depth of the marker when drawn in 3D.
| frame | [Envelope](ExternalReferences.md#envelope)|The outer boundary of the entire vector marker.
| markerGraphics | [CIMMarkerGraphic](CIMSymbols.md#cimmarkergraphic) |The vector graphics that define the shape of the marker.
| verticalOrientation3D | boolean|A boolean indicating whether the marker stands upright as though locked in place. The marker can be viewed from all angles.
| scaleSymbolsProportionally | boolean|A boolean indicating whether the strokes and or fills of a marker are scaled proportionally when the symbol size is changed. When enabled, the strokes for the outline or fill of the polygon symbol used to draw the marker will be scaled proportionally with changes to the symbol size. If this property is not enabled, then the stroke will draw with the specified width regardless of the marker size.
| respectFrame | boolean|A boolean indicating whether the frame of the vector marker should be honored when drawing the marker.
| clippingPath | [CIMClippingPath](CIMSymbols.md#cimclippingpath)|A clipping path for the vector marker graphics.





### Enumeration: VerticalAlignment
Vertical alignment types.

|Property | Value | Description |
|---------|--------|--------|
| Top| 0| Top of the highest ascender in the text symbol is used to align the text.
| Center| 1| Text is centered on the geometry.
| Baseline| 2| Text is aligned so that the geometry lines up with the baseline of the text symbol. Descenders will go past the baseline.
| Bottom| 3| Bottom of the lowest descender is used to align the text.



### Enumeration: VerticalGlyphOrientation
Vertical glyph orientation.

|Property | Value | Description |
|---------|--------|--------|
| Right| 0| Align right.
| Upright| 1| Align upright.