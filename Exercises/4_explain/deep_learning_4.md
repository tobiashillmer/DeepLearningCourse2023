### Exercise Sheet Deep Learning, Part4: Explainable AI, Summer 23

This sheet includes a theoretical part and a practical assignment of the third part of the
lecture Deep Learning (XAI).
name1: Tobias Hillmer
name2: Lukas Schubert
name3: Yasar Plückebaum

#### PARTI – THEORY
1. The following XAI methods are . . .
- SHAP is a global feature-based method => NO, SHAP is local
- LRP is invariant to the specific implementation of the functional form, i.e. if
there are two deep networks implementing the same function but possibly dif-
ferent neurons and weights, the feature relevance scores are the same =>  NO, result depends on Neurons
- LIME is a post-hoc and local model-agnostic method => YES
- Computing saliency maps is quadratic w.r.t the number of weights => NO
2. The overarching idea behind the following XAI method is . . .
-  SHAP aims for determining the weights which correspond to the impact of features in a linear model and fair distribution of their impact w.r.t coalitions => NO
-  Counterfactual explanations aim for an example with different output => YES
-  Model distillation for a classificer f relies on the idea to train a smaller model
which is supervised by the learned one => YES
-  SpRAy clusters data based on their associated closest counterfactual => NO
3. The following training/optimization algorithms are used to extract the respective
explanations:
-  DeepPINK deletes features (knock-off) to estimate their relevance => Yes
-  LRP enforces a conservation of the relevances over all data when backpropaga-
ting signals. => 
-  LIME relies on sparse global linear surrogate models, derived from sampling.
-  DeepProblog uses evolutionary optimization to account for discrete logic opera-
tions while training
4. Explanations serve different purposes: improvement, justification, raising trust, dis-
covery, whereby some methods can be used for more than one purpose. The following
explanation methods can be used (among other purproses) for . . .
-  Saliency maps for discovery of locally relevant and causal features => YES?
-  VQA for model justification => YES?
-  counterfactual explanations for improving actions => NO?
-  SpRAy for improvement of the model => YES! Chinacarcompany.com
5. The following statements are true:
-  For a linear classifier x 7 → sgn(wtx − b) and input x′, the closest counterfactual
is given by x′ − wtx′+b
wtw2 · w.
-  A linear model constitutes one example of an additive feature attribution model.
-  There are not quantitative evaluations of explainable AI
-  LIME models, if applied for logistic regression, just gives the model itself
