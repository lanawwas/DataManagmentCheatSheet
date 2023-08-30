### Setting a WSL2 Memory Limit
1. Create .wslconfig file in your home directory such as C:\Users\<?user?name>\.wslconfig
2. Open the file in a text editor and put the following parameters, change the value of in GB based on your system:
```txt
[wsl2]
memory=6GB
swap=0
````

reference: https://ryanharrison.co.uk/2021/05/13/wsl2-better-managing-system-resources.html
