1. `日本語.txt`
    
    ```sh
    macos-13$ echo "Hello 世界" > 日本語.txt
    macos-13$ od -t x1 -t c -A x -v 日本語.txt 
    0000000    48  65  6c  6c  6f  20  e4  b8  96  e7  95  8c  0a            
               H   e   l   l   o      世  **  **  界  **  **  \n            
    000000d
    
    ```
