Usage
=====

.. _installation:

Installation
------------

To use YOLOv7, first install it via git:

.. code-block:: console

   (base) $ git clone https://github.com/jinfagang/yolov7

Creating Your coco dataset or Just coco
----------------

To train on coco, the commond is very simple.
you can use the ``python train_det.py --config-file xxx.yaml --num-gpus 1`` function:

The ``train_det.py`` will automatically apply some augmentation **only** for detection. If you want train on instance segmentation:

``python train_inseg.py``.

You can try register your down dataset by:

.. code-block:: python
   # VOC dataset in coco format
   DATASET_ROOT = "./datasets/voc"
   ANN_ROOT = DATASET_ROOT
   TRAIN_PATH = os.path.join(DATASET_ROOT, "JPEGImages")
   VAL_PATH = os.path.join(DATASET_ROOT, "JPEGImages")
   TRAIN_JSON = os.path.join(ANN_ROOT, "annotations_coco_train_2012.json")
   VAL_JSON = os.path.join(ANN_ROOT, "annotations_coco_val_2012.json")

   register_coco_instances("voc_train", {}, TRAIN_JSON, TRAIN_PATH)
   register_coco_instances("voc_val", {}, VAL_JSON, VAL_PATH)




