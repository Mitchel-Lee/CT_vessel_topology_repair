# CT_vessel_topology_repair

"generate_broken_segment_data.py" is a script to generate training data for vessel topology repair network.

Input segmentation files must be split into specific component (arteries, veins, airways) before running.

Pipeline:
Extract the largest fully connected component (remove disconnected sections of segmentation).

Construct a skeletonisation and estimate vessel radius at each skeleton point.

Randomly introduce breaks into the segmentation by selecting pairs of skeleton points (maximum distance between selected points, and maximum radius of vessels to break may be selected).

Save cropped volumes (with default dimensions 80 x 80 x 80) of the broken segmentations, along with the corresponding cropped volumes of the CT image and original, fully intact, segmentation.

Example usage is contained within the script.

![synthetic_seg_diagram](https://github.com/user-attachments/assets/fddd62bc-3d1e-495d-a962-95ef3c576552)
