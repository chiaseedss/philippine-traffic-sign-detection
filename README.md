# Philippine Traffic Sign Detection and Recognition Using YOLOv8n

This project explores the detection and recognition of selected Philippine traffic signs using **YOLOv8n**. It focuses on identifying road signs in images, evaluating detection performance, and generating rule-based driving suggestions based on detected signs.

## Objectives

- Detect and classify five traffic signs: **STOP, Give Way, No Entry, Turn Left, and Turn Right**.
- Apply transfer learning to a pretrained YOLOv8n object detection model.
- Evaluate performance on validation images and a separate external test dataset.
- Associate detected signs with corresponding rule-based suggestions.

## Technologies Used

Python, Ultralytics YOLOv8n, PyTorch, OpenCV, NumPy, pandas, Matplotlib, and Jupyter Notebook.

## Methodology

The project uses YOLO-format bounding-box annotations and maps the selected source classes into five target categories. To reduce class-count imbalance, the training set was balanced to **605 images** (121 per class) from an initial pool of 1,537 images.

A pretrained YOLOv8n model was fine-tuned for **80 epochs** using **640-pixel** image inputs. Evaluation covered **386 validation images** and **265 images from an external dataset**. The recorded fixed-threshold evaluation used a confidence threshold of **0.70** and non-maximum suppression IoU of **0.70**; detection mAP was also measured.

The project also defines sign-based suggestions, such as stopping, yielding, or preparing to turn. These are **displayed recommendations**, not commands to physical robot hardware.

## Results

| Dataset | Precision | Recall | F1-score | mAP@50 | mAP@50–95 |
|---|---:|---:|---:|---:|---:|
| Validation (386 images) | 0.9974 | 0.9974 | 0.9974 | 0.9950 | 0.8546 |
| External test (265 images) | 0.8656 | 0.6075 | 0.7140 | 0.7319 | 0.5229 |

The recorded validation performance was high, but recall declined to **60.75%** on the external test images, indicating difficulty detecting some signs beyond the validation dataset. The study is limited to the five selected sign classes.

*The figures above are from the project's saved evaluation records; they are not new measurements.*

## Dataset

The training and validation images originated from a **Roboflow** traffic-sign dataset. A **Road Signs dataset** was used for external testing. Original dataset files are not redistributed here; exact dataset versions and source links should be added once verified.

## Video Demonstration

The following demonstration presents the Philippine
Traffic Sign Detection system using YOLOv8n.

[Watch the Video Demonstration](https://drive.google.com/file/d/193ewY228nIQ413k8zm9QLgmNbJ_VDMAY/view?usp=drivesdk)

## Project Files

- [`Philippine_Traffic_Sign_Project.ipynb`](Philippine_Traffic_Sign_Project.ipynb) — experiment methodology, evaluation workflow, and implementation notes.
- [`requirements.txt`](requirements.txt) — project dependencies.

The notebook refers to additional local modules, evaluation files, and a trained model checkpoint that are not included in this repository package. The standalone webcam application is therefore not available from these files alone.

## Credits

Academic Computer Vision project by Robopuff Girls: 
- Agnote, Rovilyn Doroin, Ivy 
- Moico, Mary Joyce 
- Olivares, Tischia Ann (Repository Owner)
- Quite, Rona Mae 
- Tercero, Michelle
