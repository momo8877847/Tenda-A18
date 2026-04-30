# Tenda-A18
Tenda A18 V15.13.07.09 Vulnerability Disclosure
Vulnerability Trigger Operation
Tenda A18 V15.13.07.09 has a stack overflow vulnerability in the function fromSetCmdlineRun. This function receives the parameter
wpapsk_cryptoa from a POST
request through the variable wpapsk_crypto5g and passes it to the set_repeat5 function.
![](https://github.com/momo8877847/Tenda-A18/blob/main/images/1.png)
