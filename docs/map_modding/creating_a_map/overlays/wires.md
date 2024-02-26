# Wires 

*This feature is used in SnowRunner only.*

In *SnowRunner*, there are wires in the list of overlays (their names start with `wire_`).

However, overlays do not contain poles these wires are attached to.

The process of adding poles and their wires is the following:

1.  Add poles, either as separate models, or massively, using the **Brushes** parameter of an overlay. Place them as you need.

2.  Add an overlay of the wires.

3.  Snap each point of the wire overlay to the necessary snapping point on the poles. There may be multiple snapping points there.
    To snap the point of the wire overlay to the snapping point of the pole:

    a.  Select the point of the wire overlay.

    b.  Move it maximally close to the snapping point of the pole, and, while moving it close, hold the **B** button - for snapping. Or, hold the **V** button - for fine-tuning of the snapping.

    c.  After one point is snapped, perform the same operations with the next one.

For example, in the picture below, we placed a set of `us_light_pole` models and have connected them with the `wire_double` overlay.

![](./media/image115.png)

