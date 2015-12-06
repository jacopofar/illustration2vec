# illustration2vec
Dockerfile to run illustration2vec using the CPU, used to build the corresponding Docker Hub image.

[Illustration2vec](https://github.com/rezoo/illustration2vec) is a software able to tag and extract semantic feature vectors from illustrations using deep learning.

To run it quickly using Docker, you can use the command:

    docker run -it jacopofar/illustration2vec bash

and you'll be in the container with the dependencies, illustration2vec and the models.

You can try it using this small code:

```
import i2v
from PIL import Image
print("started, loading model...")
illust2vec = i2v.make_i2v_with_chainer(
    "illust2vec_tag_ver200.caffemodel", "tag_list.json")
print("model loaded, loading image...")
img = Image.open("images/miku.jpg")
print("image loaded, estimating the tags...")
print(illust2vec.estimate_plausible_tags([img], threshold=0.5))
```
