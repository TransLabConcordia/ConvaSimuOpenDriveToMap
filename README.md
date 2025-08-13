# ConvaSimu_Map_OpenDrive

Step 1 — Insert your .xodr file into Unreal

To use our road-generation actor, you must first bring the OpenDRIVE (.xodr) file into Unreal Engine.

We do this via a third-party OpenDRIVE plugin (based on esmini RoadManager) that adds an OpenDRIVE asset type to Unreal and exposes the road network for other tools to read.

OpenDRIVE plugin (Unreal): https://github.com/brifsttar/OpenDRIVE

esmini / RoadManager: https://github.com/esmini/esmini

After the .xodr is imported and visible as an OpenDRIVE asset in your Content Browser, you can use our actor to generate splines/meshes from that data.

Why this plugin?

The plugin handles parsing of the .xodr and provides fast queries (roads, lanes, junctions). Our actor does not replace parsing; it consumes the parsed network to build the Unreal scene.

Using the Actor (SimpleDataExtractionActor)
Prerequisites

Your project already includes the OpenDRIVE plugin (third-party) and you’ve imported the target .xodr file into Unreal (as an OpenDRIVE asset).

You will create a C++ actor named SimpleDataExtractionActor.

Steps

Create the C++ actor

In Unreal Editor: Add New > C++ Class > Actor → name it SimpleDataExtractionActor → Create Class.

Add the provided code

Open the generated files:

SimpleDataExtractionActor.h

SimpleDataExtractionActor.cpp

Replace their contents with the text from your two files:

“header of opendrive actor.txt” → paste into .h

“cpp of opendrive actor.txt” → paste into .cpp

Ensure the required include

In your header, confirm this line exists:

#include "OpenDriveAsset.h"


(Do not modify the third-party plugin files; just include the header.)

<img width="1364" height="807" alt="5" src="https://github.com/user-attachments/assets/5e354839-feb8-4944-971f-02fecf2f29a5" />



Build the project

Compile from Unreal Editor (Tools → Refresh Visual Studio Project if needed, then Build) or build from your IDE.

Place the actor & generate the network

In the Content Browser, drag & drop SimpleDataExtractionActor into your level.

The actor will read the imported .xodr asset (via the plugin) and generate the road network (splines/meshes) in the scene.

Edit lane materials (optional)

Select the actor in the level.

In the Details panel, find the Materials per lane type properties.

Assign materials as you like (e.g., asphalt for driving lanes, concrete for sidewalks).

Click Save / re-run construction if your setup requires it.

(see image below in your docs)

Notes

Make sure the OpenDRIVE asset is properly recognized in the Content Browser before placing the actor.

Keep all references and licenses for the third-party OpenDRIVE plugin and esmini RoadManager intact in your project/documentation. Do not copy their code without preserving license headers.
