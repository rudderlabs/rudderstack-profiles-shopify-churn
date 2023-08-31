# Churn classifier repo

This is a profiles application project that builds a churn prediction score on top of shopify features. The shopify features is a library project, and churn prediction comes on an independent python package that is compatible with profiles. 

## Python environment setup:
This project has the same requirements as the usual profiles projects. But the python_model has one extra requirement, to create a virtual environment with the required packages installed, and point to that path in the site_config. The exact steps are present in the python_model README.md

## Customising the repo:
1. Clone the shopify features repo and make any required changes to the entity vars. This workflow should be identical to how any regular profiles project is set up
2. The github url of profiles project with feature table is added in pb_project.yaml as a package, replacing the current shopify project url. It can be a local file path as well.
3. In profiles.yaml, modify the config in train/data to point to the correct feature table and target column. 
    * The label_column should be the entity var that needs to be predicted in advance (defined by prediction_horizon_days). 
    * The label_value tells the actual value in the feature table that corresponds to the users who performed the action historically.
    * model_name is the name of feature table defined in the profiles project (step 1)
