**Rename the .der certificate into .crt**
```
mv cacert.der cert-der.crt
```

**Copy the certificate into your android device.**
```
adb push cert-der.crt /data/local/tmp/
```

**Grant the certificate appropriate permission.**
```
adb shell
chmod 644 /data/local/tmp/cert-der.crt
```

**Start the frida server & run the following command**
```
frida -U -f <packagename> -l <script>.js 
```
