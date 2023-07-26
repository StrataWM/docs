# Compiling from Source

To compile from source, follow these steps

 ## 1. Clone the repository
 ```sh
 git clone https://github.com/stratawm/kagi
 ```

## 2. Compile and install
Now `cd` into the cloned repository using:
```sh
cd kagi
```
then run:
```sh
 cargo install --path .
 ```
 This'll install it for your user. If you want to install it globally, run:
 ```sh
 sudo cargo install --path .
 ```