# Parent=hidden?

The challenge links to a website at `https://parent.labyrinthctf.live/`. The flag is stored in a file outside the directory the site serves its pages from.

## Finding the file

The main introduction page mentions a file called `NotGreekText.txt`, saved in the parent directory.

## Working out the URL

Open one of the text files that the site links to and look at its URL. This shows how paths look for the normal directory. For `ThePantheon.txt` it is:

```text
https://parent.labyrinthctf.live/read.php?path=ThePantheon.txt
```

The target file is in the parent directory, so the path has to go one level up. In a path, `../` means "go up one directory". Putting `../` in front of the file name in the `path` parameter gives:

```text
https://parent.labyrinthctf.live/read.php?path=../NotGreekText.txt
```

Opening this URL shows the contents of the file, which includes the flag.

## Flag

```text
labyrinth{norse_gods_know_how_to_talk_to_their_parents}
```