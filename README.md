# SENKAYA_WALDNER_IA_Projet_Mask

Vous pouvez retrouver sur ce repository les programmes permettant de lancer le réseau de neurones que nous avons entraînés. Ce repos est un fork du repos :  https://github.com/theAIGuysCode/tensorflow-yolov4-tflite
Le réseau de neurones que nous avons utilisé est Yolov4 Darknet.
Ce repos va permettre de faire de l'inférence sur une image, une vidéo ou directement depuis la webcam. Il permettra de tester votre réseaux Yolov4 avec un test mAP sur un dataset Kaggle centrer sur la reconnaissance du port du masque. 

## Prérequis 

Pour pouvoir faire fonctionner ce réseau il faut avoir la version de Python 3.6.8
La version de Cuda utilisé lors des test est la 11.4

## Comment commencer?

Avant de commencer quoi que ce soit il faut d'abord cloner ce repository. Après cela il faut télécharger le fichier custom.weights qui contient les poids de nos entraînements : https://drive.google.com/file/d/1Q4LvHFfFfVvh48IGeyrE168_F6Dtm-j4/view?usp=sharing

Ensuite il faut le placer dans le dossier data. 

Il faut également télécharger le fichier ZIP custom-416.zip et placer le dossier checkpoints à la racine du projet : https://drive.google.com/file/d/1SWuCTGwnUf2h_vQc_oL7_z0qmLRonSVR/view?usp=sharing

Il faut ensuite créer un environnement Python virtual via la commande suivante dans un Invite de commande : 
```
    python -m venv MyVenv
```

Ensuite il faut activer votre environnement virtuel en executant la commande suivante : 
```
    MyVenv\Scripts\activate
```

Après avoir activer votre environnement virtuel il faut vous rendre dans le dossier contenant tout nos programme.

Il faut ensuite installer les packages nécessaire via la commande (si utilisation de cuda):
```
    pip install -r requirements-gpu.txt
```

OU il faut installer la commande (si non utilisation de cuda):
```
    pip install -r requirements.txt
```
Puis éxecuter la commande suivante :
```
    python detect_video.py --weights ./checkpoints/custom-416 --size 416 --model yolov4 --video 0 --output ./detections/results.avi
```

Si vous voulez lancer le test mAP il faut effectuer les commandes suivantes : 
```
    python evaluate.py
    cd mAP\extra
    python remove_space.py
    cd ..
    python mAP\main.py --output results_yolov4_tf
```

