###启用git凭证存储，通过http方式去push和pull时，只有第一次需要提供用户名和密码，后续不需要再输入
```
git config --global credential.helper store 
```