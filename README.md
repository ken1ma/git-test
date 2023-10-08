1. `dir1`

    ```sh
    $ mkdir -p       dir1/dir11
    $ echo file12  > dir1/file12
    $ echo ファイル112 > dir1/dir11/ファイル112
    ```

1. `link`

    ```sh
    $ mkdir link
    $ (cd link; ln -s ../dir1; ln -s ../dir1/dir11/ファイル112)
    ```

1. `dir-empty`

    ```sh
    $ mkdir dir-empty
    $ touch dir-empty/.gitkeep
    ```

1. `日本語.txt`
    
    ```sh
    macos-13$ echo "Hello 世界" > 日本語.txt
    macos-13$ od -t x1 -t c -A x -v 日本語.txt 
    0000000    48  65  6c  6c  6f  20  e4  b8  96  e7  95  8c  0a            
               H   e   l   l   o      世  **  **  界  **  **  \n            
    000000d
    
    ```
