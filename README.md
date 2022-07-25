# Developing an integrated approach to validate 3D ownership spaces in complex multi-storey buildings
## Introduction 
3D geospatial data is progressively adopted in urban land administration to represent 3D ownership rights in multi-storey buildings. However, the urban land administration’s integrity highly depends on the validity and quality of cadastral data. Existing research suggests conceptual principles for internal and external spatial consistencies of 3D cadastral data. The internal spatial consistency principles ensure each 3D parcel is accurately and correctly defined and has valid geometry. In a 3D digital representation of cadastre, the 3D space is subdivided into 3D volumetric ownership spaces partitioning the 3D space without overlaps or gaps (Stoter and Salzmann, 2003). Checking double defined ownership spaces (overlaps) and undefined ownership spaces (gaps) are essential as two critical external spatial consistency principles for checking the 3D subdivision correctness. We integrated the principles in practice and developed methods to check the validity of 3D parcels and their relationships in complex ownership settings. 

![image](https://user-images.githubusercontent.com/40024785/174431870-3e0930eb-874c-49cd-bb88-92d3de2e289f.png)

## Dataset
In this project, a real cadastral dataset is used as our case study. This dataset includes 248 lots and three types of common property in an 18-floor mixed-use apartment complex.Each lot’s ownership space was represented as an aggregation of dwelling, balcony, car park, and storage spaces. Like lots, an aggregation of the spaces described common property areas. An outer geometry for each level, which represents the parcel/title boundary delineating the maximum legal right limit, was also developed in the BIM model. Developing each level’s outer geometry in which all the legal spaces are located is a critical step in the developed method for identifying gaps. A polyhedral surface model with OBJ data structure was used to represent the ownership spaces. 

![image](https://user-images.githubusercontent.com/40024785/174432091-573ab5f1-8230-4c3e-8ecc-510ba8171fbf.png)

## Implementation
The case study building shows four types of floor layouts, which are repeated throughout the building. Therefore, different parts of the whole building were utilised for different implementation phases to showcase the reliability and viability of the algorithms and methods. First, a dataset representing whole floors with 1957 unique ownership spaces including dwellings, balconies, storage, car parks, and various common property areas was used for evaluating the methods for checking the internal spatial consistency principles. 

![image](https://user-images.githubusercontent.com/40024785/174432685-db6ad49b-d6cf-43e8-be06-362d33f3beda.png)

Then, the ground floor with 62 unique ownership spaces was selected for validating the methods developed for checking overlaps.

![image](https://user-images.githubusercontent.com/40024785/174432725-0f3aec3f-9ec7-4d53-a842-4cb200b247fa.png)

And finally, the ground floor was selected to check the gap among stratified ownership spaces. 

![image](https://user-images.githubusercontent.com/40024785/174432782-f17d9e08-3923-4929-a754-2d3f56903ada.png)

## Requirements
This code was implemented with C++ programming language using Computational Geometrical Algorithms Library (CGAL). Other requirements are as follows: 
- Visual Studio 2019
- Vcpkg Library Manager
- QT (Required for drawing and visualisation)
- CMake

## How to run the codes
-	As the developed codes use the CGAL libraries, please follow the CGAL installation at https://doc.cgal.org/latest/Manual/windows.html to install the CGAL on your local system. The windows operating system and the Visual Studio IDE were used respectively to install the CGAL libraries and set up the environment to develop the codes.
-	The datasets were provided alongside the codes. The datasets are in OBJ formats representing the legal spaces of our case study. These OBJ files need to be stored in a folder on your hard drive. The path to this folder is then needed to be addressed within the codes. The default path in our code is C:/dev/MyProg/Test/Dataset.
-	A path to a folder also needs to be provided to receive the dataset_filenames.txt, dataset_filepaths.txt, Invalid objects.txt and also validation Reports.txt. All these documents are created once the codes are executed. For example, you can find the default path as C:/dev/MyProg/Test/Result/Invalid objects.txt for the invalid objects at the end of the codes. The program has also adjusted to provide the information about the invalid objects in a validation report. The default path to have access to this report is C:/dev/MyProg/Test/Result/Validation Report.txt within the code.
-	The codes also return the invalid objects with OBJ and OFF formats for more investigations and finding out the potential issues. 
-	By running the codes for checking the internal spatial consistency of the obj files, each object is checked against the validation rules developed and a result of invalid objects is created in the result folder as the Validation Report. 
-	In short, what needs to change within the code is just the path to your dataset and the different outputs that you might need. 

## Citation
```
Asghari A, Kalantari M, Rajabifard A, Shin J. Developing an integrated approach to validate 3D ownership spaces in complex multi-storey buildings.  International Journal of Geographical Information Science. 2022;
```
## Author
Ali Asghari
- Email: <asgharia@unimelb.edu.au>
- ResearchGate: [Here](https://www.researchgate.net/profile/Ali-Asghari-10)
- Linkedin: [Here](https://www.linkedin.com/in/aliiasgharii/)

## Acknowledgments
This project incorporates code from the following repos:
- https://github.com/CGAL/cgal
