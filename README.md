## Face Alignment problem solving

This code solves the face alignment problem using the FAN model to train the facial landmarks dataset.

Thanks for Ladrianb's excellent work on face-alignment-training [https://github.com/1adrianb/face alignment-training]. And in this project, I reused and updated code for 2D-FAN and 3D-FAN described in the "How far are we from solving the 2D \& 3D Face Alignment problem? (and a dataset of 230,000 3D facial landmarks)" paper. Please visit the author's webpage [https://www.adrianbulat.com] or arxiv [https://arxiv.org/abs/1703.07332] for technical details.

## Requirments

   - Install the latest Pytorch [http://pytorch.org], version 1.0.0.

## Packages

   - [https://www.scipy.org/][scipy]<br>
   - [https://pytorch.org][torchvision]<br>
   - [https://pypi.python.org/pypi/progress] progress (optional) for better visualization.

## Train

   1. Clone the GitHub repository and install all the dependencies mentioned above.
   
            git clone https://github.com/KeevaLyu/Face-Alignment


   2. Download the LS3D-W dataset from the authors' webpage (https://www.adrianbulat.com/face-alignment). 

   3. Download the 300W-LP annotations converted to t7 format by paper author from (https://www.adrianbulat.com/downloads/FaceAlignment/landmarks.zip).
   
   4. We merge the LS3D-W dataset and 300W-LP dataset together to train our model.
   
      cd data/LS3D-W                    <br>
      tree -d -L 1                      <br>
      
            |-- 300VW-3D                
            |-- 300W-Testset-3D         
            |-- 300W_LP                 
            |-- AFLW2000-3D-Reannotated 
            `-- Menpo-3D
       
      The validation set is test set of 300W-LP

   5. Start to train:

            ./exp/train.sh
   
   
## Test

   1. Run the demo.

            python demo_video.py gpu


## What's different?

   - Train FAN only includes 2 Hourglass
   - Total Params: 11.55M   

## Performance

![GIF](landmarks.gif)

## Citation

      {
       @inproceedings{bulat2017far,
         title={How far are we from solving the 2D \& 3D Face Alignment problem? (and a dataset of 230,000 3D facial landmarks)},
         author={Bulat, Adrian and Tzimiropoulos, Georgios},
         booktitle={International Conference on Computer Vision},
         year={2017}
       }
       
