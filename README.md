# CT_vessel_topology_repair
Parameters
The script includes several parameters that can be adjusted within the if __name__ == "__main__": block:

Data Paths:

data_path: Base directory containing your data (e.g., "Connectivity_CT/1/").
input_file: Path to the input NIfTI segmentation file (e.g., "arteries.nii.gz").
output_path: Directory to save processed files (e.g., "PROCESSED").

Break Introduction Parameters:

num_breaks (int): Number of artificial breaks to introduce (e.g., 3).

min_distance (float): Minimum Euclidean distance between breakpoint pairs in voxels (e.g., 5).

max_distance (float): Maximum Euclidean distance between breakpoint pairs in voxels (e.g., 15).

radius_factor (float): Scaling factor for the cylinder radius used in erosion (e.g., 1.1).

min_radius (float): Minimum radius for the cylinder in voxels to ensure minimal erosion (e.g., 1).

max_skeleton_radius (float): Maximum radius of skeleton points to consider for breaks, targeting smaller vessels (e.g., 5).

Subvolume Extraction Parameters:

subvolume_size (tuple): Size of the subvolumes to extract around breaks (default (80, 80, 80)).

num_samples (int, optional): Number of subvolumes to extract (defaults to the number of breaks).

output_dir (str): Directory to save extracted subvolumes and metadata (e.g., "SYNTHETIC_BREAKS").

Outputs:
After running the script, the following outputs will be generated in the PROCESSED folder:

Largest Connected Component:

arteries_largest_component.nii.gz: The largest connected component extracted from the input segmentation.

Broken Segmentation:

arteries_broken.nii.gz: The segmentation with artificial breaks introduced.

Synthetic Breaks Subvolumes:

Located in PROCESSED/SYNTHETIC_BREAKS/:

broken_subvolume_1.nii.gz, intact_subvolume_1.nii.gz, ct_subvolume_1.nii.gz, etc.

breakpoints.json: JSON file containing coordinates of introduced breaks and paths to the extracted subvolumes.
