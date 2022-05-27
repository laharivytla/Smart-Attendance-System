
(Overview of above codes)

Step 1: Dataset Creation
  Captures the image of a person using Haar Cascade frontal face algorithm (present in opencv library) and save it in dataset folder in our local directory. The Haar cascade algorithm only saves the image if it detects the face in the frame otherwise it won't capture. We collect the name and pin number of student and stores it in the excel file in csv format (in our case student.csv).

Step 2: Extracting the Embeddings of images
  For each image stored in dataset folder we need to perform following operations:
  * Convert the image into Blob.
  * Using Caffe model (Deep learning pre trained model) detect the face in the image.
  * Finding the coordinates of face, and again convert that part into Blob.
  * Extract embeddings from that blob and append inside a file called "embeddings.pickle" present inside output folder. (For extracting embeddings we need to use pytorch library).

Step 3: Training the model
  We are using Support Vector Machine classifier (SVC) to train our model - Machine learning algorithm.
        
                       embeddings.pickle   -->       Model      --> Recognizer.pickle, le.pickle (store it inside output folder)
                       (input)                                          (output)
     
Step 4: Testing our model 
  For a new input we need to repeat the step 2 (detecting face and finding embeddings) and compare those embeddings with recognizer.pickle, le.pickle files to recognize the person on the frame and displays the name of a person.
  
  
