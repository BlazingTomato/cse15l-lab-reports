# Getting into your Remote Access account of r CSE15L
## Step 1: Installing VSCode

If you're using the lab computers, VScode should already be installed. Simply press Windows key, then search for VSCode as shown below.


![image](https://user-images.githubusercontent.com/98483167/211942449-47d23e42-a56f-4093-b9b1-491b378b21a4.png)


If not, Vscode has a good tutorial on how to install and set up VSCode [Here](https://code.visualstudio.com/docs/setup/setup-overview). P.S. If you're looking for a cool dark color theme, I recommend [Palenight Theme](https://marketplace.visualstudio.com/items?itemName=whizkydee.material-palenight-theme).

## Step 2: Initiallizing you're Remote Account
Once you're in VScode and you've had fun customizing it to you're liking, you need to download Git for Windows. Git and Bash should already be initiallized for your lab computers, but if you're on your personal device, or it doesn't work, Git has a nice [resource](https://gitforwindows.org/) to help you get up to speed.

Once Git and Bash is set up, make sure to set up your Remote Account [here]("https://sdacs.ucsd.edu/~icc/index.php), and make sure to ask a TA or someone if something seems off. 

Now that you set a password for your CSE15L Remote account, open terminal in either VSCode, or your windows computer by searching cmd (or for mac: press space Cmd + Space and search terminal). 

Since you have Git and Bash already initallized, you can use the command ssh, which stands for secure shell. Type the command below, and replace [Account Name] with your CSE15L account name (should look like this: cs15lwi23zz).

> ssh [Account Name]@ieng6.ucsd.edu

Now it will ask you 

>ssh cs15lwi23zz@ieng6.ucsd.edu
>The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
>RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
>Are you sure you want to continue connecting (yes/no/[fingerprint])? 

Type yes and press enter, then type your password.

If nothing happens when you correctly type your password, use ctrl + c to get out of the command, and retry it. 

Once it says
>Hello [Your account name], you are currently logged into ieng6-203.ucsd.edu

you're good to go.

Overall, my experience went like this

![image](https://user-images.githubusercontent.com/98483167/211944707-463eb42a-7190-418b-abbd-3ddf36ad4d20.png)


