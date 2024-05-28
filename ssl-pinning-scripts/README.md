**Rename the .der certificate into .crt**
```
mv cacert.der cert-der.crt
```

**Copy the certificate into your android device.**
```
adb push cert-der.crt /data/local/tmp/
```

**Start the frida server & run the following command**
```
frida -U -f <packagename> -l <script>.js 
```
