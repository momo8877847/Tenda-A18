# Tenda-A18
Tenda A18 V15.13.07.09 Vulnerability Disclosure
Vulnerability Trigger Operation
Tenda A18 V15.13.07.09 has a stack overflow vulnerability in the function fromSetCmdlineRun. This function receives the parameter
wpapsk_cryptoa from a POST
request through the variable wpapsk_crypto5g and passes it to the set_repeat5 function.
![](https://github.com/momo8877847/Tenda-A18/blob/main/images/1.png)
![](https://github.com/momo8877847/Tenda-A18/blob/main/images/2.png)
In set_repeat5, the array wpapsk_cryptovalue is fixed at 16 bytes. However, since the user can control the input wpapsk_crypto5g, the statement strcpy(wpapsk_cryptovalue, wpapsk_crypto); can cause a buffer overflow. The user-provided wpapsk_crypto5g may exceed the capacity of the wpapsk_cryptovalue array, thereby triggering this security vulnerability.
![](https://github.com/momo8877847/Tenda-A18/blob/main/images/3.png)
We set both variables configured2_4g to be not equal to the string 'true' and configured5g to equal the string 'true', in order to trigger the execution of the vulnerable part of the code in the strcmpif condition.
![](https://github.com/momo8877847/Tenda-A18/blob/main/images/4.png)

reproduce:
![](https://github.com/momo8877847/Tenda-A18/blob/main/images/5.png)
