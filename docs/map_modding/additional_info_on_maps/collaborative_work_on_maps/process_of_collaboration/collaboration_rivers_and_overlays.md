# Collaboration: Rivers and Overlays

Rivers and Overlays are created for all map pieces at once. Their data is stored in the `data\River` and `data\Overlay` folders.

Thus, when a modder creates a River or Overlay object, this modder needs to locate the XML file of the necessary River or Overlay in these folders (by their Id, if necessary) and send it to all other modders.

However, there is a nuance with the deletion of River or Overlay objects. When one of the modders deletes the River or Overlay object, this modder needs to tell others to delete this object too.

