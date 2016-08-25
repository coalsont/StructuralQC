## Description

Generating Workbench Scenes for Structural Quality Control

Authors: Michael Harms and Donna Dierker

---------

1. Download the StructuralQC.zip archive from GitHub:

    https://github.com/Washington-University/StructuralQC

2. Unzip the archive in a directory where you have read permission.

    The archive contains:

    a. a single script -- GenerateStructuralScenes.sh and
    b. a 'templates' directory that contains files that are needed to render the scenes.

    You will probably invoke the script multiple times (i.e., for different batches of subjects).

3. Use a text editor to edit the following variables:

  SubjList="176239 199958 415837 433839 943862 987983"

  OutputFolder="/location/of/my/QC/output/directory"

  StudyFolder="/location/of/subject/data/directories"

  TemplateFolder="/location/of/unpacked/StructuralQC/templates"

  * SubjList is a space delimited list of subject ID's to be processed.

  * OutputFolder is where you want the per-subject scenes (and copies of the
    files in the 'templates' directory) to be located.

  * StudyFolder is the directory containing the subject data (organized in
  	standard Connectome DB file structure).  It is used to replace a dummy
  	string in the template scene so that the generated per-subject scene
  	file can find the necessary file inputs.

  * TemplateFolder is the location of the unzipped StructuralQC.zip
  	folder on your system.  The script will copy reference files (S900* and
  	mean MNI152 T1 atlas target) to your OutputFolder, so that the scenes can
  	find them.

# Enter this command at a terminal window:

	bash GenerateStructuralScenes.sh

# Confirm the scenes were generated:

	cd $StudyFolder
	
	ls

  There should be one scene file for each subject in $SubjList.
  (Each of which contains multiple scenes available for showing in wb_view).

# View the scene file using wb_view:

	wb_view "$Subject".structuralQC.wb.scene
	
