# 19. Water as Cargo

Starting with the DLC 9 ("*Season 9: Renew & Rebuild*"), you can create your own, custom addons, trailers, and semitrailers that will allow the player to work with Water as cargo.

Their ceation is similar to the creation of these entities for Fuel as cargo, you just need to add some properties to the XML files.

**TIP**: The XML files of classes of default addon, trailer and semitrailer that can work with water as cargo are available in the **initial.pak** archive, at the following paths:

-   *initial.pak\\\[media\]\\\_dlc\\dlc_9\\classes\\trucks\\addons\\**frame_addon_watertank.xml***

-   *initial.pak\\\[media\]\\\_dlc\\dlc_9\\classes\\trucks\\trailers\\**semitrailer_watertank.xml***

-   *initial.pak\\\[media\]\\\_dlc\\dlc_9\\classes\\trucks\\trailers\\**trailer_watertank.xml***

Let's cover the water-related sections of these XMLs using the ***frame_addon_watertank.xml**:*

**1. WaterCapacity attribute**

First of all, you need to specify the water capacity (in liters) of the water tank in your addon/trailer/semitrailer. It can be specified in the WaterCapacity attribute of the \<TruckData\> tag:

\<TruckAddon IsChassisFullOcclusion=\"true\"\>\
    \<TruckData WaterCapacity=\"1800\"\>\
        \...\
    \</TruckData\>\
    \...\
\</TruckAddon\>

**2. \<LimitedFluid\> tag**

Then, you need to specify the dimensions of your water tank in the \<LimitedFluid\> tag:

\<TruckAddon IsChassisFullOcclusion=\"true\"\>\
    \<TruckData WaterCapacity=\"1800\"\>\
        \<LimitedFluid\
            Color=\"(86; 186; 255; 255)\"\
            Center=\"(0.636; 1.174; 0)\"\
            LengthX=\"4.693\"\
            RadiusY=\"0.934\"\
            RadiusZ=\"1.167\"\
            Type=\"Cylinder\"\
        /\>\
    \</TruckData\>\
    \...\
\</TruckAddon\>

**NOTE**: This tag now contains Color as an attribute. It specifies the color of the water within the tank that will be displayed when the player will be filling it. Its an RGBA value, with Alpha corresponding for visibility of the water (0 -- not visible, 255 -- maximum visibility).

**3. Mass of the Water Tank itself in the \<PhysicsModel\>**

Then, in the \<PhysicsModel\> section, you need to specify the mass of the water tank itself (without water in it):

    \<PhysicsModel Mesh=\"trucks/addons/frame_addon_watertank\"\>\
        \<Body CenterOfMassOffset=\"(1; 0; 0)\" Mass=\"1500\"\>\
            \<Constraint Type=\"Rigid\" /\>\
            \<Body \_template=\"Wire\" ModelFrame=\"BoneWireLeft_cdt\" /\>\
            \<Body \_template=\"Wire\" ModelFrame=\"BoneWireRight_cdt\" /\>\
            \<Body \_template=\"Wire\" ModelFrame=\"BoneWireRear_cdt\"\>\
                \<Constraint AxisLocal=\"(0; 1; 0)\" /\>\
            \</Body\>\
            \<Body Collisions=\"None\" Mass=\"5\" ModelFrame=\"BoneFrameR_cdt\"\>\
                \<Constraint ExplicitParentFrame=\"0\" Type=\"Fixed\" /\>\
            \</Body\>\
            \<Body Collisions=\"None\" Mass=\"5\" ModelFrame=\"BoneFrameL_cdt\"\>\
                \<Constraint ExplicitParentFrame=\"1\" Type=\"Fixed\" /\>\
            \</Body\>\
        \</Body\>\
    \</PhysicsModel\>

**4. Mass of the Water Tank filled with Water in the \<WaterMass\>**

Similarly to Fuel, you need to specify the mass of the full water tank in the \<WaterMass\> tag (in the \<Body\> tag within it). This will affect the physics of the addon (truck)/trailer/semitrailer. The mass of the partially full water tank will be calculated based on mass of the full water tank and WaterCapacity (see 1 above).

\<TruckAddon\>\
    \...\
    \<WaterMass\>\
        \<Body Mass=\"1800\" /\>\
    \</WaterMass\>\
    \...\
\</TruckAddon\>

**To be continued :)**

