# Quickdraw Challenge

Quick, Draw! is an online game developed by Google that challenges players to draw a picture of an object or idea and then uses a neural network artificial intelligence to guess what the drawings represent. (Wikipedia)

#### Task
Build a neural network to identify the categories of the drawings.

#### Dataset
20 Categories from the Quick, Draw! challenge. I use 12,000 drawings per category to build a neural network using Keras framework.

## Results

After trying models with different number of layers and hyperparamets, such as the Dropout rate and the number of nodes for a fully connected layer, the best model was one with four fully connected layers, with dropout layers in between.

```
rate = 0.2
model = tf.keras.Sequential([
    tf.keras.layers.Flatten(input_shape=(x_train[1].shape)),
    tf.keras.layers.Dense(128, activation='relu'),
    tf.keras.layers.Dropout(rate),
    tf.keras.layers.Dense(128, activation='relu'),
    tf.keras.layers.Dropout(rate),
    tf.keras.layers.Dense(128, activation='relu'),
    tf.keras.layers.Dropout(rate),
    tf.keras.layers.Dense(128, activation='relu'),
    tf.keras.layers.Dropout(rate),
    tf.keras.layers.Dense(n_classes)
])
```

On the test set, this model scored a sparse_categorical_accuracy score of 0.6048.
