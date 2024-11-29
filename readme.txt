1. fetch data from zoning account
2. create annotations in coco format to train with DETR
3. use the server for traiing with resnet as pre trained model
4. train at least for 300 epochs
5. command for training in distributed mode machine
python -m torch.distributed.launch --nproc_per_node=4  --use_env main.py --coco_path doco19_8/ --output_dir="doco19_8/results" 
--epochs 400 --batch 20 --resume notebook/detr-r50_no-class-head.pth 



improvements required:
1. save best checkpoint
2. wandb to show chart for m@p

Issues:
1. pycocotools numpy issue change numpy.float to numpy.float64 as python 3.10 does not support np.float

