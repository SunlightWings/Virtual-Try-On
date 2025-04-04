[Complete Code base not maintained yet, this is just for a rough record of the files.]

Implementation on CP-VITON-PLUS dataset, extended for 3D reconstruction from single 2D image
[Dataset](https://1drv.ms/u/s!Ai8t8GAHdzVUiQRFmTPrtrAy0ZP5?e=rS1aK8) 

Steps:
1. First prepare the dataset
2. Train GMM 
 2.a Requirements: cloth, cloth mask, image, image mask, image parse(segmentation), pose(keypoint detection)
 2.b Output: Warped cloth, warped grid, warped mask, overlayed TPS
3. Test GMM with testing set
4. Train TOM 
 4.a Requirement: Warped cloth,warped mask, Image, pose, image mask.
 4.b Output: Composite mask, Rendered image, Final improved image
5. Test TOM

Pitfalls:
1. Run test.py for GMM network with the training dataset (not the testing dataset)
2. Copy the result of GMM module: "warp-cloth and "warp-mask" folders into "data/train" directory. This will be used to train the TOM as mentioned in Step 4.a above
3. For testing your custom images, resize them to 192x256 pixels, and obtain image-parse, cloth mask and pose(keypoints)

Credit for 2d goes to:
1. https://minar09.github.io/cpvtonplus/cvprw20_cpvtonplus.pdf
2. https://minar09.github.io/cpvtonplus/
