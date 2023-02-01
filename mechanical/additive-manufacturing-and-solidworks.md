# Additive Manufacturing and SolidWorks


**Sincere apologies for any image copyright infringements! These blogs were created at the time I was unaware of the copyrights. If you want me to take down any image, feel free to reach out to me @ technopains@gmail.com. Keep the Subject as 'Image Copyright Issue' Thank you for understanding!**

We all know Additive Manufacturing is booming today’s industrial sector. With the help of Additive manufacturing, there’s now almost no limit to design constraints and material wastage is also reduced by a significant amount. Here’s a small discussion about utilizing additive manufacturing using SolidWorks.

## Types of Additive Manufacturing

Major types of additive manufacturing printers include:

### FDM Printer

FDM (Fused Deposition Modelling) is the very basic and the most common in today’s market. The printer uses layer by layer extrusion can be generally carried out in an open area. FDM printers are easier to maintain compared to other printers and also least expensive, with the flexibility to use multiple spool types in order to have better printing experience.

![FDM Printer](/mechanical/assets/additive-manufacturing-and-solidworks.png)
<p><strong>Source: <a style="color: #BF4925;" href="https://www.amazon.in/Creality-3D-Ender-V2-Motherboard/dp/B087LZKC96/ref=asc_df_B087LZKC96/?tag=googleshopdes-21&linkCode=df0&hvadid=397008383227&hvpos=&hvnetw=g&hvrand=5848838857692422575&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9061646&hvtargid=pla-1123652573192&psc=1&ext_vrnc=hi">Amazon</a></strong></p>

### SLA Printer

SLA (Stereolithography) printers are the next when it comes to cost and size efficient printers. These printers carry out the printing process in enclosed areas to avoid any foreign contamination and regulate the appropriate temperature, which otherwise will lead to poor part quality and sometimes even damaging printer hardware. In this process, the resin pool is hardened using a laser source and the consistency of the floating resin is a must to ensure well quality printing.

![SLA Printer](https://5.imimg.com/data5/XX/VR/MY-11054848/form-2-sla-3d-printer-image-500x500.jpg)
<p><strong>Source: <a style="color: #BF4925;" href="https://www.amazon.in/Creality-3D-Ender-V2-Motherboard/dp/B087LZKC96/ref=asc_df_B087LZKC96/?tag=googleshopdes-21&linkCode=df0&hvadid=397008383227&hvpos=&hvnetw=g&hvrand=5848838857692422575&hvpone=&hvptwo=&hvqmt=&hvdev=c&hvdvcmdl=&hvlocint=&hvlocphy=9061646&hvtargid=pla-1123652573192&psc=1&ext_vrnc=hi">Google Images</a></strong></p>

### SLM And SLS Printers

These types of printers are mainly for industrial purposes and consume a lot of resources and power as well. Parts printed within these printers are of very high quality and they eliminate the need for any other post-processing. The most complex and intricate parts can be easily printed with these printers. Metals like Aluminium and Steel alloys which are currently in high demand can be easily printed within these printers as well.

![SLM And SLS Printer](https://www.slm-solutions.com/fileadmin/new-home/images/service1.png)
<p><strong>Source: <a style="color: #BF4925;" href="https://www.slm-solutions.com/fileadmin/new-home/images/service1.png">Google Images</a></strong></p>

## Importance of Material Selection

One of the major factors contributing to overall manufacturing effectiveness in a 3D printing process is material in operation. In the case of FDM Printers, the major printing material used is PLA or ABS. SLA uses a pool of liquid resin which hardens on laser exposure. Depending upon the printer type and desired material properties, SLA printers can be used to print resins which include clear, white, tough, castable, flexible, and dental SG, etc. Note that these resins are termed based on Formlabs standards and can be used according to their specific purposes. SLA printers use the process of photopolymerization to perform the print operation. These resins are typically loaded in the cartridges that slide into the machines and can be reloaded into the machine once they are over.

### PLA Properties
Polylactic acid is the major material used in FDM printers. Some important properties include:

- Softens at a temperature that is very easy to regulate.
- It is a bioplastic polymer, which means that it can be reused and recycled easily.
- Fumes of PLA are very less toxic as compared to other plastics, which again makes it an ideal candidate for the FDM process.


### ABS Properties
Acrylonitrile Butadiene Styrene is the second most used material in FDM printers. Some important properties of ABS include:

- ABS also softens at an easily regulatable temperature.
- Compared to PLA, ABS is more durable due to its better toughness properties. This comes out as a result of higher glass transition temperature which makes ABS a better candidate for durability.
- It gives better-finished products and ideal for shock loading applications.

## Printing Coniderations

There are many critical aspects to take care of while printing a model as a physical entity. Let’s go and discuss the effect of part orientation.

- **Part Orientation**: The strength of the part should be optimal around all three axes. Along with this, to minimize overhangs within the model and generate a suitable support structure is decided in part orientation. The model has the least strength along the z-axis. Minimizing overhangs ensures the layers have well adhered to each other and geometry is correctly aligned. Any overhang more than 60 degrees must require support material to prevent layers from collapsing due to gravity.

![3D Printing Orientation of the Part](https://i0.wp.com/cdn.shopify.com/s/files/1/0714/6487/articles/overhangs_1200x1200.jpg)
<p><strong>Source: <a style="color: #BF4925;" href="https://i0.wp.com/cdn.shopify.com/s/files/1/0714/6487/articles/overhangs_1200x1200.jpg">Google Images</a></strong></p>

Cura is a good software for preparing stl files for FDM process. On the other hand, Formlabs’s Preform software is one of the ideal choices for SLA part preparation.

- **Infill**: Infill density decides the internal density of the part and how strong it needs to be. Note that with high infill, you may get better toughness but at the same time the part will take more time and material to print.

- **Wall Thickness**: Wall thickness affects majorly the part’s strength and durability, amount of material needed, the total time needed to print and about the final finished part’s appearance. In most of the FDM printers, it is ideal to select wall thickness equivalent to the size of the extruder’s nozzle opening or in simple terms, an integral multiple of nozzle diameter.

- **Scaling**: After the part is finished printing, scaling is an important factor especially in the SLA process, where shrinkage happens. In the slicer software, one can scale it to be slightly bigger so, after all the shrinkage effects, it comes down to the exact same size.
Let’s now go and dive into export functionalities provided at the end of CAD software to ensure a smooth stl file and efficient print setup.

## STL Export Configuration in SolidWorks

Stl setting at CAD software end can be done by adjusting roughness and smoothness, checking the orientation, adjusting the layer thickness and also including the support structures to the part.

The simplest way to export the file to stl is by just going to file-> save as-> stl and save.

![STL Export Configuration in Solidworks](https://technopain.files.wordpress.com/2019/12/part.png)

To make advanced changes go-to options icon as shown below:

![STL Export Configuration Options](https://technopain.files.wordpress.com/2019/12/2019-12-25-1.png)

Let’s start by changing the resolution. Here you can change the mesh type, which may be coarse and fine or you can go to custom and make the changes accordingly, by clicking show preview.

![Solidworks STL system options](https://technopain.files.wordpress.com/2019/12/2019-12-25-1-1.png)

Other supported file types are .3MF files and .AMF files.

## Role of build plate in FDM and SLA Machines

Build Plate plays a very crucial role in both SLA and FDM machines, but more prominently, we need to ensure well build plate conditions in case of an FDM machine. Most of the build plates in FDM machines are made up of glass and hence it serves as an ideal material to which the first layer of the print can adhere on. Using hair-spray, blue tape or a small amount of glue stick can be handy to get started for an amazing print setup.

In the case of an SLA printer, it is ideal to ensure that the build plate is clean and free from any debris, in the same way, the resin tank is supposed to be clean and free of any foreign objects to ensure smooth printing experience.

## Print 3D Feature | Solidworks

Solidworks has partnered with many other 3D software to take ease of 3D printing to another next level. Go to file-> Print 3D where you can find some cool options to check the sustainability of your part and prepare it for the print. You can also check for the support structure and other settings in there. Generative Designs is another advanced feature that guides the user to develop the strength parts which may be difficult to machine but can easily be 3D printed.

So this was all about basics of 3D printing and using Solidworks features in 3D printers. I will soon update with the new advancements in Solidworks regarding additive manufacturing.








