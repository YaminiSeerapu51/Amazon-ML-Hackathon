# ML Challenge Problem Statement

## Feature Extraction from Images

In this hackathon, the goal is to create a machine learning model that extracts entity values from images. This capability is crucial in fields like healthcare, e-commerce, and content moderation, where precise product information is vital. As digital marketplaces expand, many products lack detailed textual descriptions, making it essential to obtain key details directly from images. These images provide important information such as weight, volume, voltage, wattage, dimensions, and many more, which are critical for digital stores.

### Dataset : 
The dataset is divided into two main files:

- train.csv: Contains over 310,000 image links along with metadata.
- test.csv: Contains over 130,000 image links along with metadata.

Each dataset consists of the following columns: 

1. **index:** An unique identifier (ID) for the data sample
2. **image_link**: Public URL where the product image is available for download. Example link - https://m.media-amazon.com/images/I/71XfHPR36-L.jpg
    To download images use `download_images` function from `src/utils.py`. See sample code in `src/test.ipynb`.
3. **group_id**: Category code of the product
4. **entity_name:** Product entity name. For eg: “item_weight” 
5. **entity_value:** Product entity value. For eg: “34 gram” 
    Note: For test.csv, you will not see the column `entity_value` as it is the target variable.


### File Descriptions:

*source files*

1. **src/sanity.py**: Sanity checker to ensure that the final output file passes all formatting checks. Note: the script will not check if less/more number of predictions are present compared to the test file. See sample code in `src/test.ipynb` 
2. **src/utils.py**: Contains helper functions for downloading images from the image_link.
3. **src/constants.py:** Contains the allowed units for each entity type.
4. **sample_code.py:** We also provided a sample dummy code that can generate an output file in the given format. Usage of this file is optional. 

*Dataset files*

1. **dataset/train.csv**: Training file with labels (`entity_value`).
2. **dataset/test.csv**: Test file without output labels (`entity_value`). Generate predictions using your model/solution on this file's data and format the output file to match sample_test_out.csv (Refer the above section "Output Format")
3. **dataset/sample_test.csv**: Sample test input file.
4. **dataset/sample_test_out.csv**: Sample outputs for sample_test.csv. The output for test.csv must be formatted in the exact same way. Note: The predictions in the file might not be correct.

![WhatsApp Image 2025-05-12 at 20 40 11_72617995](https://github.com/user-attachments/assets/f8fd9c34-e52d-4567-a15f-de781ed2672e)

# Conclusion
In this hackathon, spanning four days, we faced challenges, particularly with the computational resources needed to process such a large volume of data. Processing the test.csv file, which involved downloading over 52 GB of images and running them through an OCR model, took us collectively more than 20 hours. Despite these obstacles, it was an invaluable experience to work on a real-world problem faced by Amazon.

# Future Scope 
This project can also further improved using HuggingFace and Llama transformers.

# Results
Our model achieved the following results:
    - F1 Score: 0.03 (highest)
    - Rank: 503 out of 2500+ teams
