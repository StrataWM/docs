# Compiling from Source

To compile from source, follow these steps

 ## 1. Clone the repository
 ```sh
 git clone https://github.com/stratawm/stratawm
 ```

 ## 2. Installing using the script
 There is a a script that installs both StrataWM and StrataCTL. To run it, `cd` into the cloned repo:
 ```sh
cd stratawm
 ```
 then add executable permissions to the script:
 ```sh
 chmod +x install.sh
 ```
 finally, run the script:
 ```sh
 ./install.sh
 ```

 You can sit back and relax while it installs Strata. It might take a bit of time since it has to compile the source code and all the dependencies but if your system is a bit better than a potato, this won't take much time.

 ## 3. Installing manually
 To install manually, cd into the cloned repo and then run:
 ```sh
 cargo install --path .
 ```
 This'll install it for your user. If you want to install it globally (which is not recommended right now), then run:
 ```sh
 sudo cargo install --path .
 ```

 Now you have to install StrataCTL. Without it StrataWM is almost unusable. First clone the repo:
 ```sh
 git clone https://github.com/stratawm/stratactl
 ```
 Then `cd` into it:
 ```sh
 cd stratactl
 ```
 And finally install it:
 ```sh
 cargo install --path .
 ```
If you want to install it globally, then run:
 ```sh
 sudo cargo install --path .
 ```

 ## 4. Next steps
 Congratulations, if all went well, you should have StrataWM and StrataCTL installed on your system. Next you'd want to install Kagi or a hotkey daemon of your choice. If you want to install Kagi, go to the chapter on the left hand side for compiling from source. Then next chapter will teach you how to configure Strata.