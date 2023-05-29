[toc]

# 接口设计

## 用户注册接口

### 描述
该接口用于用户注册。

### 接口参数
- user(string, 必需): 用户名
- password(string, 必需): 密码
- code(string, 必需): 只有输入正确的激活码才能注册，该激活码由已存在的管理员生成。

### 请求示例
POST /admin/add  
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

## 用户登录接口

### 描述
该接口用于用户身份验证。

### 接口参数
- user(string, 必需): 用户名
- password(string, 必需): 密码

### 请求示例
POST /admin/query  
Content-Type: application/json  
{  
  "user":"admin",  
  "password":"password",  
}  

### 响应结果
{  
  "status": "success",  
  "message": "User login successful.",  
  "data": [  
    {"user":"admin"}  
  ]    
}  

### 错误处理
{  
  "status": "error",  
  "message": "Please provide a valid username with correct password.",  
  "data": {}  
}  

## 用户删除接口

### 描述
该接口用于用户删除自己。

### 接口参数
- user(string, 必需): 用户名
- password(string, 必需): 密码


### 请求示例
POST /admin/delete   
Content-Type: application/json  
{  
  "user":"admin",  
  "password":"password"  
}  

### 响应结果
{  
  "status": "success",  
  "message": "User delete successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "Please provide a valid username and correct password\.",  
  "data": {}  
}  
## 用户修改接口

### 描述
该接口用于用户修改密码。

### 接口参数
- user(string, 必需): 用户名  
- old_password(string, 必需): 旧密码  
- new_password(string, 必需): 新密码  

### 请求示例
POST admin/update  
Content-Type: application/json  
{  
  "user":"admin",  
  "old_password":"password",  
  "new_password":"mew_password"  
}  

### 响应结果
{  
  "status": "success",  
  "message": "Password update successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "Please provide a valid username and correct password.",    
  "data": {}  
}  

## 部门添加接口

### 描述
该接口用于部门添加。

### 接口参数
- dept_name(string, 必需): 部门名称

### 请求示例
POST /dept/add  
Content-Type: application/json  
{  
  "dept_name":"海工",   
}  

### 响应结果
{  
  "status": "success",  
  "message": "Department addition successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 部门查询接口

### 描述
该接口用于部门查询，如果参数为"all"就返回所有的部门，否则就返回查询的部门。

### 接口参数
- dept_name(string, 必需): 部门名

### 请求示例
POST /dept/query  
Content-Type: application/json  
{  
  "dept_name":"all"    
}  

### 响应结果
{  
  "status": "success",  
  "message": "",  
  "data": [  
    {"dept_name":"海工"},  
    {"dept_name":"计科"}  
  ]   
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 部门删除接口

### 描述
该接口用于删除部门。

### 接口参数
- dept_name(string, 必需): 部门名称

### 请求示例
POST /dept/delete   
Content-Type: application/json  
{  
  "dept_name":"海工"  
}  

### 响应结果
{  
  "status": "success",  
  "message": "Department delete successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 部门修改接口

### 描述
该接口用于修改部门名称。

### 接口参数
- old_dept_name(string, 必需): 旧部门    
- new_dept_name(string, 必需): 新部门    

### 请求示例
POST admin/update  
Content-Type: application/json  
{  
  "old_dept_name":"海工",  
  "new_dept_name":"计科"  
}  

### 响应结果
{  
  "status": "success",  
  "message": "Department update successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",    
  "data": {}  
}  

  
