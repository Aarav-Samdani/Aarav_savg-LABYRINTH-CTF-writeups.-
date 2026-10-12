\# Parent=hidden?



The challenge links to a website at `https://parent.labyrinthctf.live/`. The flag is stored in a file outside the directory the site serves its pages from.



\## Finding the file



The main introduction page mentions a file called `NotGreekText.txt`, saved in the parent directory.



\## Working out the URL



Open one of the text files that the site links to and look at its URL. This shows how paths look for the normal directory, like for pantheon.txt it looks like: 



```text

https://parent.labyrinthctf.live/read.php?path=ThePantheon.txt

```



The target file is in the parent directory, so the path has to go one level up. In a path, `../` means "go up one directory". Replacing the file name in the URL and adding `../` in front gives:



```text

https://parent.labyrinthctf.live/read.php?path=../NotGreekMyth.txt

```



Opening this URL shows the contents of the file, which includes the flag.



\## Flag



```text

labyrinth{norse\_gods\_know\_how\_to\_talk\_to\_their\_parents}

```

