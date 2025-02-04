### Problem how to iterate over strings on each line and do not brake string at space character
 ```sh
 cat file_paths.txt
/path/tofile/vm name 1.vmx
/path/tofile/vm name 2.vmx
/path/tofile/vm_name_3.vmx
/path/tofile/vm name 4.vmx
/path/tofile/vm name_5.vmx
/path/tofile/vm_name_6.vmx
```

Solution
```sh
cat file_paths.txt | while IFS= read fp; do echo "FP: $fp" ;done
FP: /path/tofile/vm name 1.vmx
FP: /path/tofile/vm name 2.vmx
FP: /path/tofile/vm_name_3.vmx
FP: /path/tofile/vm name 4.vmx
FP: /path/tofile/vm name_5.vmx
FP: /path/tofile/vm_name_6.vmx
```

