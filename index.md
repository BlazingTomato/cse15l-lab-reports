# Getting into your Remote Access account for CSE15L
## Step 1: Installing VSCode

If you're using the lab computers, VScode should already be installed. Simply press Windows key, then search for VSCode as shown below.


![image](https://user-images.githubusercontent.com/98483167/211942449-47d23e42-a56f-4093-b9b1-491b378b21a4.png)


If not, Vscode has a good tutorial on how to install and set up VSCode [Here](https://code.visualstudio.com/docs/setup/setup-overview). P.S. If you're looking for a cool dark color theme, I recommend [Palenight Theme](https://marketplace.visualstudio.com/items?itemName=whizkydee.material-palenight-theme).

## Step 2: Initiallizing you're Remote Account
Once you're in VScode and you've had fun customizing it to you're liking, you need to download Git for Windows. Git and Bash should already be downloaded for your lab computers, but if you're on your personal device, or it doesn't work, Git has a nice [resource](https://gitforwindows.org/) to help you get up to speed.

Once Git and Bash is set up, make sure to set up your Remote Account [here]("https://sdacs.ucsd.edu/~icc/index.php). If you haven't set a password for your remote account, you'll have to set a new password. Look up your account by inputing your last name and PID, and click on your CSE15L account. The website should lead you to the global password reset tool, and you can change it here. It took me a couple minutes for the password to change, so don't worry if it doesn't work the first time, and always make sure to ask a TA or someone if something seems off. 

Now that you set a password for your CSE15L Remote account, open terminal in either VSCode, or your windows computer by searching cmd (or for mac: press space Cmd + Space and search terminal). 

Since you have Git and Bash already initallized, you can use the command ssh, which stands for secure shell. Type the command below, and replace [Account Name] with your CSE15L account name (should look like this: cs15lwi23zz).

```ssh [Account Name]@ieng6.ucsd.edu```

Now it will ask you 

```
ssh cs15lwi23zz@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])? 
```

Type yes and press enter, then type your password.

If nothing happens when you correctly type your password, use ctrl + c to get out of the command, and retry it. 

Once it says
```
Hello [Your account name], you are currently logged into ieng6-203.ucsd.edu
```

you're good to go.

Overall, my experience went like this

![image](https://user-images.githubusercontent.com/98483167/211944707-463eb42a-7190-418b-abbd-3ddf36ad4d20.png)

## Step 3: Trying some Commands
Now that you're in your Remote Accounts, you can use some commands to snoop around your directory.

What I did was use the command
```
cd ~
ls
```
to first change my directory (cd) to the home folder (~), than list (ls) the files in that directory.

This is what mine looked like

![image](https://user-images.githubusercontent.com/98483167/211945294-c7590ef8-51b7-4376-9067-1a0225d7762a.png)

If you're not sure what commands to use, [Here](https://www.lifewire.com/change-directories-in-command-prompt-5185508) is a basic guide on moving around directories for Window's Command Prompt.

That should be all you need to get started on your remote account. And always ask someone for help if something goes wrong, rather than wasting time doing it by yourself ;).

# Lab Report 2 - Servers and Bugs (Week 3)
## Part 1

This lab was to create a web server called StringServer that keeps track of strings added to the server.

Here's the code for the server

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> strings = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            
            return displayStrings();
        }else{
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    strings.add(parameters[1]);
                    return displayStrings();
                }
            }
            return "404 Not Found!";
        }
    }

    String displayStrings(){
        String s = "";

        for (String string : strings) {
            s += string + "\n";
        }

        return s;
    }
}




class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```


Here are some examples of adding a string to the server.



![image](https://user-images.githubusercontent.com/98483167/215677843-510df28b-83b8-486f-8a08-1e8c1b2eb623.png)

This screenshot shows a user entering "Hello" into the server, and the webpage displaying it as so. It first calls the handleRequest(URI url) method with the given url. IT fids that the url contains /add, so it takes the parameters of the url and adds the string to the ArrayList strings.After it adds the string, the server calls displayString(), which outputs all the strings in the ArrayList.

None of the values in the URL gets changed, only the ArrayList is appended.

If nothing is added to the URL, only displayStrings() is called.

![image](https://user-images.githubusercontent.com/98483167/215681015-e51d587b-7624-47f9-ace3-465cd77047dc.png)

This is an instance of a user adding "How are you" to the server, after "Hello" has been added. As you can see, Hello remains on the webpage, and How are you is printed after. This is because the ArrayList is only appended, and not reinitialized.


## Part 2

Here's an example of a input that does not induce a failure and a failure-inducing input for the same method.

```
@Test
  public void testReversed() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));

    int[] input2 = {1,2,3};
    assertArrayEquals(new int[]{3,2,1}, ArrayExamples.reversed(input2));
  }
 ```
 
 This is the following symptom
 
![image](https://user-images.githubusercontent.com/98483167/215683647-0b13c5d1-8c26-4d34-9e8b-8365d44eb9c0.png)

The Bug inducing code is shown here

```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

The bug is that the array is reversed to the halfway point, but then is simply recopied into the second half. Thus the input of an empty array will work, but an input of a populated array fails.

The code-change is shown here.

```
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = arr[i];
      arr[i] = temp;
    }
  }
 ```
 
 ## Part 3
 
 The big thing I learned from week 2 and 3 is how to use JUnit tests to debug my code, and to look for failure-inducing inputs. Gone are the days of using System.out.println everywhere in my code, looking for a potential bug hidding behind the spagetti code. Now that I can use JUnit tests, not only can I easily use a lot of different inputs to test my code, fine-tuning and locating what and where the bug is has become so much easier for all my CS classes.

