Codes for ACL paper "Jointly Learning to Align for Neural Cross-Lingual Summarization".

Quick start:

```
path=***
save-dir=***
CUDA_VISIBLE_DEVICES=0,1,2,3 python train_xsumm.py $path \
  --generator generator --optimizer adam \
  --dropout 0.4 --max-tokens 4096 \
  --label-smoothing 0.2 --criterion label_smoothed_cross_entropy \
  --adam-betas '(0.9, 0.999)' --save-dir $save-dir \
  --min-lr '1e-09' --lr-scheduler inverse_sqrt --weight-decay 0.0001 \
  --warmup-updates 3000 --warmup-init-lr '1e-07' \
  --task crosslingual_summarization --lr 0.0003 \
  --no-epoch-checkpoints
```
