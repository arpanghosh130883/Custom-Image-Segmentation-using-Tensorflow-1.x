# Custom Image Segmentation using Tensorflow 1.x

1. # Creation of Test Images
    - Download Images
    - Annotate imamges in .jason format using Labelme tool
    - Use the script to convert .jason anotated files to .tfrecords file
    - Store Images in seperate folder and anotated files in seperate folder
2. # Download the model from Tensordflow model zoo
     - https://github.com/tensorflow/models/tree/v1.13.0
     - use the models whose outputs are Mask
3. # Model Config file changes
     - Make necessary changes basis the requirement of experiment (sepcially in line 10 and line 127)
     - Line 127 referes for the checkpoint modification
4. # Traing and Inferencing
     - Use belo commands for the same
     
     - Train
         
         - python train.py --logtostderr --train_dir=mask_training/ --pipeline_config_path=mask_training/mask_rcnn_inception_v2_coco.config


    - Inference
       
       - python export_inference_graph.py --input_type image_tensor --pipeline_config_path mask_training/mask_rcnn_inception_v2_coco.config --trained_checkpoint_prefix            mask_training/model.ckpt-10 --output_directory inference_graph
