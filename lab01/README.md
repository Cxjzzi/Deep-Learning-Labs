# Lab 1 — Building Your Deep Learning Workbench

## Laboratory

Lab 1 — Building Your Deep Learning Workbench

## Objective

The objective of this laboratory was to become familiar with the software tools and workflow used in deep learning. I used Google Colab to run Python code, examined the Python environment and GPU, created and manipulated PyTorch tensors, and used a pretrained image-classification model from Hugging Face to classify several images.

## Tools Used

- Python
- Google Colab
- PyTorch
- NumPy
- Pandas
- Matplotlib
- PIL
- PrettyTable
- Git
- GitHub
- Hugging Face Transformers

## Model Used

The model tested was `google/vit-base-patch16-224`. This model is a Vision Transformer designed for image classification. It was pretrained on ImageNet-21k and fine-tuned on ImageNet-1K.

## Main Result

The pretrained model successfully performed image classification without requiring us to train a neural network. The cat image was classified primarily as an Egyptian cat with a score of approximately 0.4614. The model also returned predictions and scores for images of a robot dog and a toy robot. The notebook used a Tesla T4 GPU through Google Colab, and the PyTorch tensor was successfully moved to the GPU.

## Interesting Failure

The model had difficulty interpreting the robot images. For the robot dog, its top predictions were “crutch” (0.1668), “folding chair” (0.0697), and “joystick” (0.0529), even though the image showed a robot dog. For the toy robot, the model predicted labels such as “toyshop,” “breastplate,” and “comic book,” rather than identifying it as a toy or robot. These errors may have occurred because the images were different from the data used to train the model, or because the model focused on individual visual features instead of the complete object.

Another example showed that confidence is not the same as correctness. An image of an astronaut was classified as “gasmask, respirator, gas helmet” with a score of approximately 0.7100. The model recognized the helmet-like appearance but failed to identify the complete context of the astronaut.

## Reflection

This laboratory demonstrated the workflow of using an existing deep-learning model: input data is provided to a pretrained model, the model produces predictions, and the predictions must be evaluated rather than accepted automatically. The experiments also showed the importance of recording software versions, selecting suitable computing hardware, and considering the limitations of a model when interpreting its results.

**Lab ipynb file was too large to upload please refer to the link below:**
https://colab.research.google.com/drive/1b3gxNPeWqVYpLqJeuqUuNuQNXXkkyl7O#scrollTo=bYGXUDfQMaCP 
