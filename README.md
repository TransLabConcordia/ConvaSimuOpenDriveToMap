# ConvaSimu_Map_OpenDrive

Step 1 — Insert your .xodr file into Unreal

To use our road-generation actor, you must first bring the OpenDRIVE (.xodr) file into Unreal Engine.

We do this via a third-party OpenDRIVE plugin (based on esmini RoadManager) that adds an OpenDRIVE asset type to Unreal and exposes the road network for other tools to read.

OpenDRIVE plugin (Unreal): https://github.com/brifsttar/OpenDRIVE

esmini / RoadManager: https://github.com/esmini/esmini

After the .xodr is imported and visible as an OpenDRIVE asset in your Content Browser, you can use our actor to generate splines/meshes from that data.

Why this plugin?

The plugin handles parsing of the .xodr and provides fast queries (roads, lanes, junctions). Our actor does not replace parsing; it consumes the parsed network to build the Unreal scene.
