# RS-FewshotSSL
Self-Supervised Learning for Remote Sensing Scenes Classification under few shot scenario

Scene classification is a crucial research problem in remote sensing (RS) that has attracted many researchers recently. It has many challenges due to multiple issues, such as: the complexity of remote sensing scenes, the classes overlapping (as a scene may contain objects that belong to foreign classes), and the difficulty of gaining sufficient labeled scenes. Deep learning (DL) solutions and in particular convolutional neural networks (CNN) are now state-of-the-art solution in RS scene classification; however, CNN models need huge amounts of annotated data, which can be costly and time-consuming. On the other hand, it is relatively easy to acquire large amounts of unlabeled images. Recently, Self-Supervised Learning (SSL) is proposed as a method that can learn from unlabeled images, potentially reducing the need for labeling. 
In this work, we propose a deep SSL method, called RS-FewshotSSL, for RS scene classification under the few shot scenario when we only have a few (less than 20) labeled samples per class. Under this scenario, typical DL solutions that fine-tune pre-trained CNN models fail dramatically. RS-FewshotSSL is composed of an online network and a target network both using the EfficientNet-B3 CNN model as a feature encoder backbone. During the pretext task, RS-FewshotSSL learns discriminative features from the unlabeled images using cross-view contrastive learning. Different views are generated from each image using geometric transformations and passed to the online and target networks. Then, the whole model is optimized by minimizing the cross-view distance. After pre-training using the pretest task, the target network is discarded, and the online model is fine-tuned on the downstream task using the few labeled shots or scenes. 
Previous SSL methods based on cross-view contrastive learning require a large batch size to learn good feature representations, which is a major challenge when the computational resources are limited. Therefore, in order to keep the batch size high, we propose to down sample the images during the pretext task training. Furthermore, in the downstream task of RS-FewshotSSL, we propose a two-branch fusion architecture with each branch consisting of a copy of the EfficientNet-B3 CNN initialized with weights from the pretext task. Then, one branch uses large batches of down-sampled images while the other branch used smaller-size batches of images with their original size. This architecture allows us to benefit from both large batch sizes and full image sizes. We show that RS-FewshotSSL is able to learn from the large amounts of unlabeled data and enhance its classification accuracy. We tested RS-FewshotSSL on three RS public datasets, and it demonstrated a significant improvement compared to other state-of-the-art methods such as: SimCLR, MoCo, BYOL and IDSSL.




N. Alosaimi, H. Alhichri, Y. Bazi, B. B. Youssef,  and N. Alajlan, "Cnn ensemble approach to detect covid-19 from computed tomography chest images,"Computers, Materials & Continua 2023, 67(3), 3581-3599. https://doi.org/10.32604/cmc.2021.015399
