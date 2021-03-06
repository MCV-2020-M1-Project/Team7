# Week 1

## Pre-requisites
- OpenCV
- Numpy
- Scipy

You can install these packages with pip using: 
`pip install requirements.txt`

## Instructions
`python match\_paintings.py <path_to_db> (e.g., /home/sergio/MCV/M1/DB) <db_folder_name> (e.g., BBDD) <query_set_folder_name> (e.g., qsd1_w1) --masking <0 apply mask / 1 don't remove background> -rm <name of the retrieval method> -mm <name of the masking method> --output_pkl <path to save pkl file with query assignments>        --output_mask <folder to save mask images>`

## List of methods
<ul>
    <li> rm: [onedcelled, CBHC, twodcelled2, 1dhist, 2dhist]</li>
    <li> mm: [CBHS, PBM]</li>
</ul>

CBHC and onedcelled will only work if there is no masking method or CBHS is selected. It does not work with PBM because it does not preserve the 2D shape of the image.

## Notes
 - The folder should contain the database folder aswell as the query set. \
    e.g., \
    -db_folder (<- <path_to_db> parameter (absolute path)) \
    -- BBDD (<- <db_folder_name> parameter (relative path with respect to db_folder -> it is only necessary to indicate the folder name)) \
    -- qsd1_w1 (<- <query_set_folder_name> parameter (relative path with respect to db_folder -> it is only necessary to indicate the folder name)) \

Method reference list:
- CBHC: Cell-based histogram comparison
- CBHS: Cell-based histogram segmentation
- PBM: Probability-based masking
- 2dhist: Color histogram (2D luminance + 1D luminance histograms -> Descriptor)
