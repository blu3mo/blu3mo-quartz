---
title:
 'PyTorch'
---

注意すること
- BackPropagationがいらないところ（テストデーター / 実用途の場合）は、torch.no_gradの中でやる
    - Pretrained Modelを使うときにも注意、自分がいじらないところはfalseにする

- Dropoutを使ったなら、テストデーター / 実用途の場合はmodel.eval()でオフる
    - またtrainするときは、model.train()で元に戻す
    - もしくはwhen: 使った方が楽?

#Udacity_Intro_to_Deep_Learning_with_PyTorch
- A few things to check if your network isn't training appropriately
    - Make sure you're clearing the gradients in the training loop with optimizer.zero_grad(). If you're doing a validation loop, be sure to set the network to evaluation mode with model.eval(), then back to training mode with model.train().
- まあ上に書いたのと同じ話
