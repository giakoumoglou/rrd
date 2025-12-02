## Representation Distillation

This is a PyTorch implementation of the [RRD paper](https://arxiv.org/abs/2407.12073):
```
@misc{giakoumoglou2024relational,
      title={Relational Representation Distillation}, 
      author={Nikolaos Giakoumoglou and Tania Stathaki},
      year={2024},
      eprint={2407.12073},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2407.12073}, 
}
```

## CIFAR-100 Classification

Please refer to [CIFAR-100](https://github.com/giakoumoglou/distillers/tree/master/cifar) for more details.

## ImageNet ILSVRC-2012 Classification

Please refer to [ImageNet](https://github.com/giakoumoglou/distillers/tree/master/imagenet) for more details. Also supports CIFAR-100 classification.

## Abstract

Knowledge distillation transfers knowledge from large, high-capacity teacher models to more compact student networks. The standard approach minimizes the Kullback–Leibler (KL) divergence between the probabilistic outputs of the teacher and student, effectively aligning predictions but neglecting the structural relationships encoded within the teacher’s internal representations. Recent advances have adopted contrastive learning objectives to address this limitation; however, such instance-discrimination–based methods inevitably induce a *“class collision problem”*, in which semantically related samples are inappropriately pushed apart despite belonging to similar classes. To overcome this, we propose **_R_**elational **_R_**epresentation **_D_**istillation (**RRD**) that preserves the *relative relationships* among instances rather than enforcing absolute separation. Our method introduces separate temperature parameters for teacher and student distributions, with a **sharper teacher** (low $\tau_t$) emphasizing primary relationships and a **softer student** (high $\tau_s$) maintaining secondary similarities. This dual-temperature formulation creates an implicit information bottleneck that preserves fine-grained relational structure while avoiding the over-separation characteristic of contrastive losses. We establish theoretical connections showing that InfoNCE emerges as a limiting case of our objective when $\tau_t \rightarrow 0$, and empirically demonstrate that this relaxed formulation yields superior relational alignment and generalization across classification and detection tasks.

<p align="center">
  <img src="https://github.com/user-attachments/assets/d148850a-e253-4c2b-ae5f-1bf4c01f41a1" alt="Information Bottleneck Visualization" width="500"/>
</p>

<p align="left"><strong>Figure 1:</strong> <strong>Visualization of the <em>information bottleneck</em> effect.</strong>  
The teacher produces a sharper similarity distribution $\mathbf{p}^T(\mathbf{x}_i;\tau_t)$ (solid black) highlighting primary relationships, while the student adopts a softer distribution $\mathbf{p}^S(\mathbf{x}_i;\tau_s)$ (dashed black) that retains secondary similarities.  
The gray-shaded overlap region illustrates the <em>filtered information flow</em>, where only essential relational cues are transferred from teacher to student, effectively bounding $I(\mathbf{z}^T;\mathbf{z}^S)$.
</p>

### License

This project is under the CC-BY-NC 4.0 license. See [LICENSE](LICENSE) for details.








