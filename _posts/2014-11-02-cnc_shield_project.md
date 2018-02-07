---
layout: post
title: CNC Machining of an Aluminum Crest
---

<div class="post">
This project was part of the [Numerical Control of Machine Tools (ME548)](http://mme.uwaterloo.ca/~me548/) course that I'm taking right now.

Given an aluminum blank and a technical drawing of the part (below), I needed to produce a crest with a custom engraving on the surface.

<img src="/assets/images/shield/shield-drawing.png" alt="Shield drawing"/>

From the drawing, I made a model with all the crest geometry in MasterCAM. Here's what the model looks like:

<img src="/assets/images/shield/mastercam_model.png" alt="MasterCAM geometry"/>

In order to actually machine the part I needed specify the toolpaths for the various operations, including contouring of the outer faces, the facing on the part surface, the engraving on the crest and the scallops to finish the part off. Here are some screenshots showing some of the more interesting toolpaths.

Removing material to form the crest island:
<img src="/assets/images/shield/island_operation.png" alt="Island operation"/>

Skimming material off of the crest face to prepare for engraving:
<img src="/assets/images/shield/island_skimming.png" alt="Island facing"/>

The engraving design, based off of the *Bundesadler* (the German federal eagle):
<img src="/assets/images/shield/engraving.png" alt="Engraving"/>


Once this was done, the model and toolpaths were converted to G-Code using a post-processor and off I went to the CNC mill. Here's what the finished product looks like:

<img src="/assets/images/shield/shield_finished.jpg" alt="Finished product!"/>

Overall, I'm pretty pleased with how it turned out, particularly the engraving, but in hindsight I should have put more thought into the toolpath for the facing on the floor (around the crest). The zigzag pattern didn't turn out as well as I had hoped and there were slight cusps from the stepover percentage I used. Live and learn.
</div>