# Visual Taxonomy Project

This project aims to solve a problem using a visual taxonomy dataset. The solution involves preprocessing a large dataset, handling missing values, and training a ResNet50 model to classify images into different categories. Below, I describe the steps followed to complete the project.

## Steps in the Project

### 1. Adding Image Paths to `train.csv` and `test.csv`

The first step was to create a script to add the full image paths from the dataset to the `train.csv` and `test.csv` files. This eliminated the need to access images using only their IDs, making the data easier to handle and access.

### 2. Preprocessing Missing Values

The dataset had two types of missing values:
- Some attributes had only partial missing values.
- Some categories had no attribute values defined (i.e., all attribute values were missing for that category).

For preprocessing, I:
- Used a pretrained ResNet50 model to impute only those attributes with partial missing values.
- Did not impute attributes for categories where all values were missing.

### 3. Splitting Data into Categories

Given the large number of images, I split the dataset into categories for efficient preprocessing. Each category was processed separately. The preprocessing code for each category can be found in the `Preprocess` folder of this repository.

### 4. Training the Model

After filling the missing values, I trained the model using the ResNet50 architecture. To further optimize the training process:
- I divided the data into categories and trained models separately for each category.
- The training scripts for each category are available in the `Train` folder.

### 5. Kaggle Dataset

The images and additional dataset information can be downloaded from the Kaggle competition [Visual Taxonomy](https://www.kaggle.com/competitions/visual-taxonomy).

## Repository Structure

```
.
├── Data                     # Folder containing the dataset
├── Preprocess                # Contains preprocessing scripts for each category
│   ├── Kurtis
│   ├── Men_Tshirts
│   ├── Sarees
│   ├── Women_Tops_Tunics
│   └── Women_Tshirts
├── Train                    # Contains training scripts for each category
│   ├── Kurtis
│   ├── Men_Tshirts
│   ├── Sarees
│   ├── Women_Tops_Tunics
│   └── Women_Tshirts
├── .gitignore               # Git ignore file
├── category.csv             # CSV file with category details
├── main.ipynb               # Main script
├── predict.ipynb            # Prediction script
├── read.me                  # README file
├── resnet50_weights.h5      # Pretrained ResNet50 weights
├── test.csv                 # Test dataset with image paths
├── train.csv                # Training dataset with image paths
├── train_without_na.csv     # Training dataset with missing values handled
```

## How to Run

1. Download the dataset from the Kaggle [Visual Taxonomy competition](https://www.kaggle.com/competitions/visual-taxonomy).
2. Clone this repository and navigate to the directory:
    ```bash
    git clone https://github.com/Anubhav-Vashishtha/Meesho_Hackathon
    cd Meesho_Hackathon
    ```
3. Add the dataset to the appropriate folder.
4. Follow the steps in `main.ipynb` to preprocess the data and train the model.

## Libraries Used
- Python
- TensorFlow/Keras (for ResNet50)
- Pandas
- Pillow for image processing
- NumPy

## Contact
For any queries, feel free to contact me.
[LinkedIn](https://www.linkedin.com/in/anubhav-vashishtha-319523256/)