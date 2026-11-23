# 004: Explore the cube and run a first analysis

- **Status:** done
- **Created:** 2026-11-22
- **Updated:** 2026-11-22
- **Due:** 2026-11-22

## Goal

`topic.ipynb` has a Data section (citation, files, units, limitations), a Parameters section, an exploration of the sample cube and the dark and white references, and a first quantitative comparison of two painted regions in calibrated reflectance. The notebook runs top to bottom from a fresh kernel.

## Progress log

- 2026-11-22: Checked the MD5 checksums of all six files in `data/` against the Zenodo record (10.5281/zenodo.8143550); all match. The record says dammar varnish was applied to half of the painted surface, but not which half, and includes no varnish map.
- 2026-11-22: Exploration. The sample cube is 410 lines × 384 samples × 288 bands (896–2502 nm, BIL, uint16). 46 values are saturated (65535 counts), all at lines 38–40, outside every region. White − dark is below 1000 counts for some sample in 12 bands (896–959 nm), so the analysis keeps 1000–2500 nm (268 bands). Reference line means vary by 0.05 % (dark) and 0.15 % (white), but white − dark varies by 4.5 % across samples at 1300 nm, so references are averaged over lines for each sample separately.
- 2026-11-22: The band ratio R(1730)/R(1300) has its steepest drop at sample 267, a vertical edge inside the painted area. Regions were placed either side of it: left (samples 215–250) and right (samples 285–320), lines 80–330.
- 2026-11-22: First analysis in reflectance, n = 8750 pixels per region. R(1730)/R(1300): left 0.773 ± 0.037, right 0.663 ± 0.049 (mean ± SD), difference 0.109 (2.5 pooled SD). Control R(1100)/R(1300): left 0.953 ± 0.057, right 0.927 ± 0.058, difference 0.025 (0.4 pooled SD). Notebook sections drafted with Claude Code and run from a fresh kernel without errors.
- 2026-11-22: Checked the notebook against the Project 5 brief in the course `project-list.md`, which asks the draft for per-band noise from the dark frames and a PCA score image (sessions 8 and 15). Added both. Dark SD is 15.8 counts (median over bands, range 13.8–16.2) with variance/mean about 0.025, so read noise, not counting noise; as a reflectance 0.0004–0.003, and the spread between pixels in each region is a median 86–90 times larger. Block means of the dark lines follow 1/√n (ratio 0.87–1.00) up to 25 lines. PCA of the painted area (55 100 pixels, 268 bands, centered only): PC1 82.3 %, PC2 14.5 %, PC3 2.2 %. PC1 changes most steeply at sample 260 (Savitzky-Golay smoothing; 266 with a 5-sample moving average), and PC1 and PC2 both show a straight vertical edge across hair, forehead and face. PC1 scores: left 0.666 ± 0.745, right −0.842 ± 0.759.

## Outcome

The painted area has a vertical edge near sample 267. To its right, relative C–H absorption near 1730 nm is stronger (ratio difference 0.109, against 0.025 for the control ratio). That is consistent with extra organic material such as varnish on the right side, but it is not validated, because the dataset has no varnish map and the regions were chosen using the same ratio. PCA, given no regions, finds the edge at sample 260, which lowers that circularity. The test of whether the edge comes from a coating or from the paint is task 005.
