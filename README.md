# Overnight Sensation Speakers

![Overnight Sensations](blob/master/bookshelf/assets/desktop.jpg?raw=true)

This repository contains my build plans for Paul Carmody's Overnight Sensations speakers. It is intended to compliment Paul's designs, plans, and notes with manufacturable components. That is herein lie full CNC-able and PCB-producable components.

This currently includes details for the [original bookshelf speakers](https://sites.google.com/site/undefinition/bookshelf-speakers/diy-overnightsensations), the [floorstanding TMM's](https://sites.google.com/site/undefinition/floorstanding-speakers/overnightsensationtmm?authuser=0), and the [center speaker](https://sites.google.com/site/undefinition/home-theater-speakers/overnightsensationcenterchannelbipolewhatwhen?authuser=0). I have future plans to include the [surround speakers](https://sites.google.com/site/undefinition/home-theater-speakers/overnightsensationcenterchannelbipolewhatwhen?authuser=0).

## Bookshelf TM

I built these a few years ago and did not document things very well, save for a few photos and the build documents.

## Floorstanding TMM

These are the most well developed plans as they are the most recent I've worked on.

NOTE: The version I have designed for uses the HiVi T20 tweeter and 1/2" thick wood for the cabinet. I've made some attempt at making the design general and adaptable, but you will likely have to tweak if you build the alternate version.

The cabinet design was reproduced from Paul's SketchUp screen capture into FreeCAD. The full FreeCAD files are in the [floorstanding[(floorstading)] directory. Here's a snapshot of the major dimensions. Perhaps enough to build from.

![Cabinet Drawing](blob/master/floorstanding/assets/cabinet-drawing.png?raw=true)

My crossover PCB is for the HiVi T20 tweeter. You can use the same PCB, just substitute the different value components.

## Software Tools

I use the following software in the production of these

- Inkscape for basic drawing and to generate SVG files for patterns.
- KiCad for schematic capture and PCB design.
- FreeCAD for cabinet design and CAM toolpath generation.
- LibreOffice for spreadsheets, bill of materials (BOM).

I have used the following software in parts of the process but am quickly moving away from them as I migrate to FreeCAD and other more open and interchangable software.

- Carbide Create / Carbide Motion for 2D CAD/CAM on Shapeoko 3
- Autodesk Fusion 360 for cabinet design and CAM toolpath generation

## The Files

NOTE: There may be extraneous generated files in the directories, like generated GCode, Gerber files, and such. These are outputs from processes and may not be suited to your manufacturing equipment. You should regenerate these for your own equipment, don't use mine. I warned you.

- bookshelf
    - os_bookshelf_crossover
    - os_bookshelf_cabinet
- floorstanding
    - os_floorstanding_crossover
    - os_floorstanding_cabinet
- center
    - os_center_crossover
    - os_center_cabinet

- surround
    - os_surround_crossover