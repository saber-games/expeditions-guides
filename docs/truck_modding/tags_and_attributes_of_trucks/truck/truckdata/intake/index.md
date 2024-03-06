# Intake

The `<Intake>` tag describes the visualization of the air intake.

Typically, this visualization is set up for large vehicles and is located in the middle of the radiator grille. Along with the visualization, some elements of this setup are also used for gameplay features.

Particularly, the `Origin` attribute of this tag specifies the point of dangerous immersion in water. If the water level is above this point and the truck (or an addon installed to it) has no [`<Snorkel>`](./../../snorkel/index.md) located above it, the truck will start to receive damage.

-   `Origin="(2.8; 1.612; 0)"`  
    *(Mandatory.)* Position.

-   `Dir="(1; 0; 0)"`  
    *(Mandatory.)* Direction vector. Has as opposite direction to the air stream.

-   `Size="1.2"`  
    *(Mandatory.)* Size.

