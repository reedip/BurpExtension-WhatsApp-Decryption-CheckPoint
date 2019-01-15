# THIS REPO HAS BEEN CLONED JUST FOR RESEARCH PURPOSE
# WhatsApp Protocol Decryption Burp Tool

This tool was created during our research at Checkpoint Software Technologies on Whatsapp Protocol.

Here is the link to our blog post: https://research.checkpoint.com/fakesapp-a-vulnerability-in-whatsapp/

The Extension:

![alt tag](https://raw.githubusercontent.com/romanzaikin/BurpExtension-WhatsApp-Decryption-CheckPoint/master/tool.png)


Made By:
---------------

__Dikla Barda__

Linkedin - https://www.linkedin.com/in/diklabarda/ 


__Roman Zaikin__

Linkedin - https://www.linkedin.com/in/romanzaikin/

Twitter -  https://twitter.com/R0m4nZ41k1n


Dependences:
---------------

1) Download Python 2.7 at https://www.python.org/downloads/release/python-2715/

2) Download pip at https://pip.pypa.io/en/stable/installing/

3) Execute the command `pip install -r requirements.txt`
    * On Linux/Mac use `python2 -m pip install  -r requirements.txt`

4) Download Microsoft Visual C++ Compiler for Python 2.7 at https://www.microsoft.com/en-us/download/confirmation.aspx?id=44266

5) Copy `stdint.h` to `C:\Users\Administrator\AppData\Local\Programs\Common\Microsoft\Visual C++ for Python\9.0\VC\include`


About the extension
---------------

This extension allow you to view and manipulate the actual data that sent via whatsapp.

1) First you have to run the `parser.py` file (which is in helper dir).
2) Second you have to add the file `burpWhatsapp.py` to your burpsuit extensions.


Functionality
---------------

1) Decrypt incoming data, you have to paste the data as base64 to the extension `ctrl+b`
2) Encrypt incoming data, after you decrypt the data you can encrypt and put it back to burp by copy pase the base64 and `ctrl+shift+b`
3) Decrypt outgoing data, to decrypt outgoing data you have to take it from `AesCbcEncrypt` function in list format.
4) Encrypt outgoing data, after the extension encrypt the data back you have to put it back via the console.

you can use the following helper function to do that:

```js
function str2unit8(str) {
  var buf = new ArrayBuffer(str.length);
  var bufView = new Uint8Array(buf);
  
  for (var i=0, strLen=str.length; i < strLen; i++) {
    bufView[i] = str[i];
  }
  return buf;
}
```

TO-DO
---------------

The extension currently can decrypt and encrypt only the message related functionality, in order to add more function you have to map the protobuf
and add it to our protobuf file.



