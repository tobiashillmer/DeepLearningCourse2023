### Exercise Sheet Deep Learning, Part3: Attacks, Summer 23

This sheet includes a theoretical part and a practical assignment of the third part of the
lecture Deep Learning (Attacks).
name1: Tobias Hillmer
name2: Lukas Schubert
name3: Yasar Plückebaum

#### PARTI – THEORY

1. For the following attacks, it holds:
- Backdoor attacks try to change the function such that the network can no longer be used. -> NO
- Data poisoning attacks need access to the training data. -> YES, malicious data needs to be added.
- Model inversion attacks can be countered using robust training. -> NO, but it depends on whether measures such as Differential Privacy count as robust training.
- Universal attacks provide universal backdoors for arbitrary models. -> NO

2. For the following adversarial attacks, it holds:
- Fast gradient sign and basic iterative method are based on gradient schemes. -> YES
- Deepfool uses an adaptive step size. -> YES
- Universal adversarial perturbations incorporate a regularization against translations of visual objects in scenes. -> 
- Adversarial attacks need to have access to the model gradient or estimate it implicitly -> NO

3. Defenses against attacks ...
- Data poisoning can be detected by clustering the training set. -> NO, outliers are detected using the class mean on certified data
- Homomorphic privacy enables the public release of models trained on personal data. -> NO, the model would be unusable without decryption
- Adversarial training solves the adversarial training loss exactly via computing worst case adversarials in the inner loop. -> NO, only approximately
- Certified defenses can rely on Lipschitz bounds. -> YES

4. Attacks in reality:
- Some training data might deteriorate model accuracy rather than helping it -> YES
- Attacks need to address the whole input space -> NO
- Attacks can be designed such that they hold for different object view points or different scenes in a stream -> YES
- Data compression can provably avoid attacks. -> NO, but can help against some types of attacks

5. The following holds:
- Robustified networks have the same accuracy as original ones -> NO
- Adversarial risk and minimum perturbation risk are identical for the mean squared error. -> NO
- Adversarial training complexity strongly depends on the design of adversarial attacks in the inner loop -> YES, if design is more efficient
- Adversarial examples do not exist for linear models. -> NO

#### PARTII – PRACTICE

1. Use a deep network for the MNIST data set. Perform at least three different types of targeted attacks on 5 different numbers, including one attack which puts particular effort on the fact that the attacked pattern is indistinguishable from the original one. Evaluate the performance of the attacks visually (which attack does not change the visual impression) and quantitatively (distance of attack to original sample, success rate of the approach).

Code is here: https://github.com/tobiashillmer/DeepLearningCourse2023/blob/main/Exercises/3_attacks/deep_learning_3_1_practical.ipynb

2. Use the FashionMNIST data set and a deep model. Create a universal attack, which attacks more than one input at once. Describe how you approach this, and evaluate the performance (success rate). Evaluate whether the universal attack also transfers to other deep learning architectures.

Code is here: https://github.com/tobiashillmer/DeepLearningCourse2023/blob/main/Exercises/3_attacks/deep_learning_3_2_practical.ipynb

The universal pertubation works by computing a pertubation, which leads to an missclassification for each datapoints, and by combining these pertubations into a universal one usable for all images.
The universal pertubation attack almost halfes the accuracy (from 92.13% to 47.11), while not affecting recognition through a human. However the effects of the attack are clearly visible.
Applied on a fundamentally different (not convolutional) architecture the universal pertubation significantly reduces the accuracy from 88.26% to 74.14%.
