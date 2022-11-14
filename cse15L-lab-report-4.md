Ricky Li
Joe Politz
14 November 2022

### CSE 15L Lab Report 2

# Part 1

In DocSearchServer.java, change the name of the start parameter of getFiles, and all of its uses, to instead be called base

DocSearchServer.java:

```

import java.io.File;
import java.io.IOException;
import java.net.URI;
import java.net.URISyntaxException;
import java.nio.file.Files;
import java.nio.file.Path;
import java.nio.file.Paths;
import java.util.ArrayList;
import java.util.List;

class FileHelpers {
    static List<File> getFiles(Path start) throws IOException {
        File f = start.toFile();
        List<File> result = new ArrayList<>();
        if(f.isDirectory()) {
            System.out.println("It's a folder");
            File[] paths = f.listFiles();
            for(File subFile: paths) {
                result.addAll(getFiles(subFile.toPath()));
            }
        }
        else {
            result.add(start.toFile());
        }
        return result;
    }
    static String readFile(File f) throws IOException {
        System.out.println(f.toString());
        return new String(Files.readAllBytes(f.toPath()));
    }
}

class Handler implements URLHandler {
    List<File> files;
    Handler(String directory) throws IOException {
      this.files = FileHelpers.getFiles(Paths.get(directory));
    }
    int num = this.files.size();
    public String handleRequest(URI url) throws IOException {
        if (url.getPath().equals("/")) {
            return String.format("There are " + num + " files to search");
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/search")) {
                String[] parameters = url.getQuery().split("=");
                if (parameters[0].equals("count")) {
                    num += Integer.parseInt(parameters[1]);
                    return String.format("There were " + num + " files found:");
                }
            }
        return "Don't know how to handle that path!";
        }
    }
}

class DocSearchServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler("./technical/"));
    }
}

```

Our sequence of vim commands looked like this:

`/` `s` `t` `a` `r` `t` `<Enter>` `d` `w` `i` `base` `<Esc>` `n` `d` `w` `i` `base` `<Esc>` `:` `w` `<Enter>`
  
![My Image](sc-lab-report4-2.JPG)

This is what it looks like when we first open the DocSearchServer.java file in vim using `vim DocSearchServer.java`
  
![My Image](sc-lab-report4.JPG)

after `/` `s` `t` `a` `r` `t` `<Enter>` it puts our cursor on the first instance of search on the code. Then using `d` `w` `i` we delete the word search and enter insert mode where we can type out base. Then we type out `<Esc>` to leave insert mode.
  
![My Image](sc-lab-report4-3.JPG)

The `n` key then goes to the next instance of search and then using `d` `w` `i` we delete the word search again and enter insert mode to type out base once again. Then we type out `<Esc>` to leave insert mode.
  
![My Image](sc-lab-report4-4.JPG)

After we have finished editing the file, this is what it looks like in vim. We then press the commands `:` `w` `<Enter>` in order to save our work.


# Part 2

Editing file on my vs code then scp : 


2 minutes 28 seconds, I forgot how the format to connect into the remote server was so I had to look it up real quick in order to ssh and scp into the remote account.


Using vim to edit file on remote server : 


40~ seconds, not much trouble here, once I was in vim mode it was really easy to update the file and then exit out to run test.sh




### Which of these two styles would you prefer using if you had to work on a program that you were running remotely, and why? 

I would rather go into the remote server and use vim in order to edit and then save the file just because it is a lot easier and quicker to do in comparison to scp'ing the file.

### What about the project or task might factor into your decision one way or another? (If nothing would affect your decision, say so and why!)

If the task is a lot easier and has minor changes, I would prefer using vim. If the task required a lot more work and has a lot of errors, I would rather work on my own vs code and then scp the file because I am more comfortable editing files this way and I am not quite efficient using vim as of now.


  
