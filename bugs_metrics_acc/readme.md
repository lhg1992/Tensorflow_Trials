This code shows a bug with `metrics="acc"` or `metrics="accuracy"` in model.fit.
  1. Run through the code using `metrics="acc`" with `train_dataset` from `aug.flow`. you will find the acc is just 0.1.
  2. If you run through the code using `metrics="acc"` with `x=train_images, y=train_lables, batch_size=128`, you will see the correct acc. 
      Then without re-compiling the model, feed the `model.fit` with `train_dataset`, you will still have the correct acc as well. 

Even though the tensorflow [tutorial](https://www.tensorflow.org/tutorials/images/classification) uses the name 'accuracy' to feed `metrics`, never do it!
It's highly recommended to use a specific instance such as `tf.keras.metrics.SparseCategoricalAccuracy()`
