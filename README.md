## fastai
The fastai library simplifies training fast and accurate neural nets using modern best practices. See the fastai website to get started. The library is based on research into deep learning best practices undertaken at fast.ai, and includes "out of the box" support for vision, text, tabular, and collab (collaborative filtering) models. For brief examples, see the examples folder; detailed examples are provided in the full documentation. For instance, here's how to train an MNIST model using resnet18 (from the vision example):
```
from fastai.vision import *
path = untar_data(MNIST_PATH)
data = image_data_from_folder(path)
learn = cnn_learner(data, models.resnet18, metrics=accuracy)
learn.fit(1)
```

In this notebook we will see how to easily create an image dataset through Google Images. Note: You will have to repeat these steps for any new category you want to Google.

### Download into file
Now you must run some Javascript code in your browser which will save the URLs of all the images you want for you dataset.

Press CtrlShiftJ in Windows/Linux and CmdOptJ in Mac, and a small window the javascript 'Console' will appear. That is where you will paste the JavaScript commands.

You will need to get the urls of each of the images. Before running the following commands, you may want to disable ad blocking extensions (uBlock, AdBlockPlus etc.) in Chrome. Otherwise the window.open() command doesn't work. Then you can run the following commands:
```
urls = Array.from(document.querySelectorAll('.rg_di .rg_meta')).map(el=>JSON.parse(el.textContent).ou);
window.open('data:text/csv;charset=utf-8,' + escape(urls.join('\n')));
```
