# Template Matching Problem
 
The task is to identify associations between the provided crops and images, specify which crops appear in which locations in which image. 

The output is a dictionary where the keys are image names, and the values are a list of tuples of crop names and their locations (specified by their left-top and right-bottom coordinates). 

For certain images or crops, if there are no associations, those images are appended into 'not applicable' key in the dictionary.


# Logic used in the functions:

## getUniqueCrops:

	Crop images are encoded in hexadecimal format using md5 algorithm to check data integrity.
	
## getCropsAssociation:

	Pass images and crops to matching function
	
## md5:

	Returns md5 checksum of the image file(s) referred [here](https://www.geeksforgeeks.org/md5-hash-python/)
	
## matchCrop:

	Template matching is performed using [cv2.matchTemplate()](https://opencv-python-tutroals.readthedocs.io/en/latest/py_tutorials/py_imgproc/py_template_matching/py_template_matching.html) for searching and finding the location of cropped image in the original image. It returns a grayscale image, where each pixel denotes how much does the neighbourhood of that pixel match with template.
	
	
	
Gaussian Blur is used for original images and crops to remove noise and to make the matcher more generalised.	

The function cv2.minMaxLoc finds the minimum and maximum element values and their positions.

Rectangular box plots are drawn over the original image calculating the top-left and bottom-right corner. The x and y points of the top-left and bottom-right corners are found from the shape of the image object.

	

	