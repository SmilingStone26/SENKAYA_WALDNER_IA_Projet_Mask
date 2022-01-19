# SENKAYA_WALDNER_IA_Projet_Mask

Vous pouvez retrouver sur ce repos les programmes permettant de lancer le réseau de neurones que nous avons entraînés. Ce repos est un fork du repos :  https://github.com/theAIGuysCode/tensorflow-yolov4-tflite
Le réseau de neurones que nous avons utilisé est Yolov4 Darknet.
Ce repos va permettre de faire de l'inférence sur une image, une vidéo ou directement depuis la webcam. Il permettra de tester votre réseaux Yolov4 avec un test mAP sur un dataset Kaggle centrer sur la reconnaissance du port du masque. 

## Prérequis 

Pour pouvoir faire fonctionner ce réseau il faut avoir la version de Python suivante 3.6.8
La version de Cuda utilisé lors des test est la 11.4

## Comment commencer?

Avant de commencer quoique ce soit il faut d'abord cloner ce repository. Après cela il faut télécharger le fichier suivant qui contient les poids de nos entraînements : 

Ensuite il faut place ce dossier data. 

Il faut ensuite créer un environnement Python virtual via la commande suivante dans un Invite de commande : 
```
    python -m venv MyVenv
```

Ensuite il faut activer votre environnement virtuel en executant la commande suivante : 
```
    MyVenv\Scripts\activate
```

Après avoir activer votre environnement virtuel il faut vous rendre dans le dossier contenant tout nos programme puis éxecuter la commande suivante :
```
    python detect_video.py --weights ./checkpoints/custom-416 --size 416 --model yolov4 --video 0 --output ./detections/results.avi
```

Si vous voulez lancer le test mAP il faut effectuer les commandes suivantes : 
```
    python evaluate.py
    python mAP\extra\remove_space.py
    python mAP\main.py --output results_yolov4_tf
```

