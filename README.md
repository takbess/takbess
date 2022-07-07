- 👋 Hi, I’m @takbess
- 👀 I’m interested in Machine Learning.
- 🌱 I’m currently learning Computer Vision.
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
takbess/takbess is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->


Following the instruction, I did the command:

```
python -m tools.train_net \
    --config-file configs/COCO-detection/faster_rcnn_R_50_FPN_base.yaml \
    --num-gpus 8 \
    --resume \
    --eval-only \
    DATASETS.TEST "('coco_test_all', 'coco_trainval_all',)" \
    MODEL.META_ARCHITECTURE "ProposalNetwork"
```

Then, I got the following error:

usage: train_net.py [-h] [--config-file FILE] [--config-file-lin FILE] [--resume] [--eval-only]
                    [--eval-all] [--eval-during-train] [--eval-iter EVAL_ITER] [--start-iter START_ITER]
                    [--end-iter END_ITER] [--num-gpus NUM_GPUS] [--num-machines NUM_MACHINES]
                    [--machine-rank MACHINE_RANK] [--dist-url DIST_URL]
                    [--opts_lin OPTS_LIN [OPTS_LIN ...]] [--opts ...]
train_net.py: error: unrecognized arguments: DATASETS.TEST ('coco_test_all', 'coco_trainval_all',) MODEL.META_ARCHITECTURE ProposalNetwork

So, I'm doing the command:

python -m tools.train_net \
    --config-file configs/COCO-detection/faster_rcnn_R_50_FPN_base.yaml \
    --num-gpus 8 \
    --resume \
    --eval-only \
   --opts \
    DATASETS.TEST "('coco_test_all', 'coco_trainval_all',)" \
    MODEL.META_ARCHITECTURE "ProposalNetwork"

The difference is "--opts \".
Is this change correct?
