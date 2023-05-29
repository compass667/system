# 接口设计

## 用户注册接口

### 描述
该接口用于用户注册，成功时返回注册成功的信息。

### 接口参数
- user(string, 必需): 用户名
- password(string, 必需): 密码
- code(string, 必需): 只有输入正确的激活码才能注册，该激活码由已存在的管理员生成。

### 请求示例
POST /register  
Content-Type: application/json  
{  
  "user":"admin",  
  "password":"password",  
  "code":"114514"  
}  

### 响应结果
{  
  "status": "success",  
  "message": "User registration successful.",  
  "data": {}
}  

### 错误处理
{  
  "status": "error",  
  "message": "Please provide a valid username, password and code.",  
  "data": {}
}  

  
