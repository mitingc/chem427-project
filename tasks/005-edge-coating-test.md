# 005: Test whether the edge at sample 267 comes from a coating or from the paint

- **Status:** active
- **Created:** 2026-11-22
- **Updated:** 2026-11-22
- **Due:** 2026-12-01

## Goal

Decide whether the difference in R(1730)/R(1300) across the edge near sample 267 (task 004) behaves like a surface coating, staying the same wherever the edge crosses different paint, or follows the painted features, as a pigment difference would.

## Next step

In a new section of `topic.ipynb`, after the First analysis:

1. Add a parameter `STRIP_HEIGHT_LINES` (unit: lines, with its reason) and split `REGION_LINES` (80–330) into strips of that height, for example five strips of 50 lines crossing the hair, forehead, cheek and chin.
2. In each strip, compute left − right for R(1730)/R(1300) and for the control R(1100)/R(1300), using the same left and right sample ranges as task 004.
3. Plot the difference for each strip, with a different marker for each of the two ratios, and add a sentence on what the plot shows.
4. Do the same for the PC1 scores, which in task 004 already show the edge as a straight line across hair, forehead and face.
5. After this, start on the brief's measure: the C–H band area near 1700 nm above a baseline fitted through anchor regions on either side (session 11), with the anchor residual checked.

## Done when

The notebook has a table and a plot of the left − right difference for every strip and both ratios, and a markdown cell that states whether the difference keeps the same sign and a similar size in all strips. That cell also says what this means for the coating explanation, and the notebook runs top to bottom from a fresh kernel.

## Progress log

- 2026-11-22: Created from the "assumption to test next" in the First analysis of `topic.ipynb`.
- 2026-11-22: The PCA added to the notebook shows the edge in PC1 at sample 260, a straight vertical line crossing different paint. That is a visual impression, which steps 1–4 turn into numbers.

## Outcome
