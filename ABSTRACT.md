Authors introduce **DUTS**, a significant contribution to the field of saliency detection, which originally relied on unsupervised computational models with heuristic priors but has recently seen remarkable progress with deep neural networks (DNNs). DUTS is a large-scale dataset comprising 10,553 *train* images and 5,019 *test* images. The training images are sourced from the ImageNet DET training/val sets, while the test images are drawn from the ImageNet DET test set and the SUN dataset, encompassing challenging scenarios for *salient_object* detection. What sets DUTS apart is its meticulously annotated pixel-level ground truths by 50 subjects and the explicit training/test evaluation protocol, making it the largest saliency detection benchmark to date, enabling fair and consistent comparisons in future research endeavors, with the training set serving as an ideal resource for DNN learning and the test set for evaluation purposes.

<img src="https://i.ibb.co/d2FN38z/Screenshot-2023-10-19-201047.png" alt="image" width="800">

<span style="font-size: smaller; font-style: italic;">Image-level tags (left panel) provide informative cues of dominant objects, which tend to be the salient foreground. Authors propose to use image-level tags as weak supervision to learn to predict pixel-level saliency maps (right panel).</span>

Authors provide a new paradigm for learning saliency detectors with weak supervision, which requires less annotation efforts and allows the usage of existing large scale data set with only imagelevel tags (e.g., [ImageNet](https://ieeexplore.ieee.org/document/5206848)). Secondly, authors propose two novel network designs, i.e., global smooth pooling layer and foreground inference network, which enable the deep model to infer saliency maps by leveraging image-level tags and better generalize to previously unseen categories at test time. Thirdly, authors propose a new CRF algorithm, which provides accurate refinement of the estimated ground truth, giving rise to more effective network training. The trained DNN does not require any post-processing step, and yields comparable or even higher accuracy than fully supervised counterparts at a substantially accelerated speed.

<img src="https://i.ibb.co/Sncmpdj/Screenshot-2023-10-19-154330.png" alt="image" width="800">

<span style="font-size: smaller; font-style: italic;">Overview of the network architecture. In the first stage, authors jointly train FCN and FIN (b-e) for image categorization (f). In the second stage, the FIN (b,d) is trained for saliency prediction (g).</span>


