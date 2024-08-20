# Overnight Sensation Speakers

![Overnight Sensations](bookshelf/assets/desktop.jpg?raw=true)

This repository contains my build plans for [Paul Carmody](https://sites.google.com/site/undefinition/diy?authuser=0)'s **Overnight Sensations** speakers. It is intended to compliment Paul's designs, plans, and notes with manufacturable components. That is herein lie full CNC-able and PCB-producable components.

This currently includes details for the [original bookshelf speakers](https://sites.google.com/site/undefinition/bookshelf-speakers/diy-overnightsensations), the [floorstanding TMM's](https://sites.google.com/site/undefinition/floorstanding-speakers/overnightsensationtmm?authuser=0), and the [center speaker](https://sites.google.com/site/undefinition/home-theater-speakers/overnightsensationcenterchannelbipolewhatwhen?authuser=0). I have future plans to include the [surround speakers](https://sites.google.com/site/undefinition/home-theater-speakers/overnightsensationcenterchannelbipolewhatwhen?authuser=0).

This is a work in progress, bear with me as I build the speakers and add the components.

### A few notes on the designs

- Designed for 1/2" material. Using the 1/2" plans in all cases.
- Uses miter joints at the box corners, so can use already faced plywood.
- Uses painted MDF for the baffle. Could use faced plywood but the fillet on the outside edges would need to be removed.
- Does not use rabbet for back. Seems an overly complicated addition.

If you are using something else, it should be easily adapted.

## Bookshelf TM

No build files available.

I built these a few years ago and did not document things very well, save for a few photos and the build documents.

## Floorstanding TMM

![TMM Glamor Shot](/floorstanding/assets/tmm-glamor-shot.jpg?raw=true)

Includes:

- Cabinet Plans in FreeCAD
- Crossover PCB in KiCad with Gerbers for PCB manufacture
- 2"x3" port in FreeCAD for 3D printing

These are the most well developed plans as they are the most recent I've worked on.

NOTE: The version I have designed for uses the HiVi T20 tweeter and 1/2" thick wood for the cabinet. I've made some attempt at making the design general and adaptable, but you will likely have to tweak if you build the alternate version.

The cabinet design was reproduced from Paul's SketchUp screen capture into FreeCAD. The full FreeCAD files are in the [floorstanding[(floorstading)] directory. Here's a snapshot of the major dimensions. Perhaps enough to build from.

![Cabinet Drawing](/floorstanding/assets/cabinet-drawing.png?raw=true)

My crossover PCB is for the HiVi T20 tweeter. You can use the same PCB, just substitute the different value components.

**NOTE**: I started working on alternate crossovers with thicker traces but stopped. See the notes below about **Power Handling**. I think the 3mm traces I have are "thick enough" for this configuration under normal use. It would be nice to have thicker traces (5-6mm), and 9.5mm spaced screw terminals. If I ever do make another PCB, I'll make those changes. Oh, I also forgot to put in additional holes for the wire ties on the 1.5 mH coil.

## Center MMTM

![Cabinet Drawing](/center/assets/cabinet-drawing.svg?raw=true)

Next to be built!

## Surround

Yet to be built!

## Software Tools

I use the following software in the production of these. These are all open-source freely available products.

- [Inkscape](https://inkscape.org) for basic drawing and to generate SVG files for patterns.
- [KiCad](https://www.kicad.org) for schematic capture and PCB design.
- [FreeCAD](https://www.freecad.org) for cabinet design and CAM toolpath generation.
- [LibreOffice](https://www.libreoffice.org) for spreadsheets, bill of materials (BOM).

In the past I used the following software in parts of the process but am quickly moving away from them as I migrate to FreeCAD and other more open and interchangable software.

- [Carbide Create](https://carbide3d.com/carbidecreate/) / [Carbide Motion](https://carbide3d.com/carbidemotion/) for 2D CAD/CAM on Shapeoko 3
- [Autodesk Fusion 360](no link, autodesk keeps taking features away and I don't want to support that) for cabinet design and CAM toolpath generation

## Power Handling

To calculate what the power rating of the speaker is, and the appropriate trace width for the crossover boards.

- HiVi B4N is rated 25W RMS (50W max) at 8 Ohms, 60 - 4,000 Hz
- HiVi B3N is rated 10W RMS (30W max) at 8 Ohms, 80 - 12,000 Hz
- HiVi T20-8 is rated 15W RMS (no max specified) at 8 Ohms, 4,000 - 20,000 Hz

From some random source on the Internet:

    roughly 40-40-20 percentage for woofer, mid, tweeter

From [celestion](https://celestion.com/blog/power-handling-all-you-need-to-know/)

    As a rule of thumb, the cabinet power handling should be calculated as a multiple of the lowest rated speaker. For example in a 2×12 containing a 60-watt speaker and a 30-watt speaker, overall cabinet power handling is 2×30-watt = 60-watt. In a 4×12 containing 2×60-watt speakers and 2×30-watt speakers, overall cabinet power handling is 4×30-watt = 120-watt.

By this measure:

The TMM is either 25*.4+25*.4+14*.2 23W (43W max) or 3x15W = 45W (90W max) into an 8 Ohm speakers. With `I = E/R`, `23/8 = 2.875A` or `43/8 = 5.73A` max.

Using [Digikey Trace Size Calculator](https://www.digikey.com/en/resources/conversion-calculators/conversion-calculator-pcb-trace-width) and looking at "Required Trace Width" for "External Layers in Air":

- 2.7A, 22 degrees-C, 1 Oz weight, 4 inches, 20 degree rise gives **0.78 mm trace width**
- 5.73A max, 22 degrees-C, 1 Oz weight, 4 inches, 20 degree rise gives **2.19mm trace width**

I also calculated voltage drop and resistance of these traces, but not sure how to evaluate these in an objective way. Citations needed.

- 0.78mm trace width, 0.07 Ohms, 0.18V voltage drop, 0.49W power loss
- 2.19mm trace width, 0.02 Ohms, 0.13V voltage drop, 0.79W power loss

## NOTE: About The Files

There may be extraneous generated files in the directories, like generated GCode, Gerber files, and such. These are outputs from processes and may not be suited to your manufacturing equipment. You should regenerate these for your own equipment, don't use mine. I warned you.

The `Common-Crossover` directory is not used. This is a work-in-progress of designing a common crossover PCB that could work on all the Overnight Sensation speakers. It started when I thought my trace widths were not sufficient. **It is incomplete**.
