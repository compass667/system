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
POST dept/update  
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

## 党委添加接口

### 描述
该接口用于党委添加。

### 接口参数
- committee_name(string, 必需): 党委名称

### 请求示例
POST /committee/add  
Content-Type: application/json  
{  
  "committee_name":"海工",   
}  

### 响应结果
{  
  "status": "success",  
  "message": "Committee addition successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 党委查询接口

### 描述
该接口用于党委查询，如果参数为"all"就返回所有的党委，否则就返回查询的党委。

### 接口参数
- committee_name(string, 必需): 党委名

### 请求示例
POST /committee/query  
Content-Type: application/json  
{  
  "committee_name":"all"    
}  

### 响应结果
{  
  "status": "success",  
  "message": "",  
  "data": [  
    {"committee_name":"哈工大"},  
    {"committee_name":"双创园"}  
  ]   
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 党委删除接口

### 描述
该接口用于删除党委。

### 接口参数
- committee_name(string, 必需): 党委名称

### 请求示例
POST /committee/delete   
Content-Type: application/json  
{  
  "committee_name":"海工"  
}  

### 响应结果
{  
  "status": "success",  
  "message": "Committee delete successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 党委修改接口

### 描述
该接口用于修改党委名称。

### 接口参数
- old_committee_name(string, 必需): 旧党委    
- new_committee_name(string, 必需): 新党委    

### 请求示例
POST committee/update  
Content-Type: application/json  
{  
  "old_committee_name":"哈工大",  
  "new_committee_name":"双创园"  
}  

### 响应结果
{  
  "status": "success",  
  "message": "Committee update successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",    
  "data": {}  
} 

## 支部添加接口

### 描述
该接口用于支部添加。

### 接口参数
- branch_name(string, 必需): 支部名称

### 请求示例
POST /branch/add  
Content-Type: application/json  
{  
  "branch_name":"海工",   
}  

### 响应结果
{  
  "status": "success",  
  "message": "Committee addition successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 支部查询接口

### 描述
该接口用于支部查询，如果参数为"all"就返回所有的支部，否则就返回查询的支部。

### 接口参数
- branch_name(string, 必需): 支部名

### 请求示例
POST /branch/query  
Content-Type: application/json  
{  
  "branch_name":"all"    
}  

### 响应结果
{  
  "status": "success",  
  "message": "",  
  "data": [  
    {"branch_name":"哈工大"},  
    {"branch_name":"双创园"}  
  ]   
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 支部删除接口

### 描述
该接口用于删除支部。

### 接口参数
- branch_name(string, 必需): 支部名称

### 请求示例
POST /branch/delete   
Content-Type: application/json  
{  
  "branch_name":"海工"  
}  

### 响应结果
{  
  "status": "success",  
  "message": "Branch delete successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 支部修改接口

### 描述
该接口用于修改支部名称。

### 接口参数
- old_branch_name(string, 必需): 旧支部    
- new_branch_name(string, 必需): 新支部    

### 请求示例
POST branch/update  
Content-Type: application/json  
{  
  "old_branch_name":"哈工大",  
  "new_branch_name":"双创园"  
}  

### 响应结果
{  
  "status": "success",  
  "message": "Branch update successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",    
  "data": {}  
} 

## 回复情况添加接口

### 描述
该接口用于回复情况添加。

### 接口参数
- member_name(string, 必需): 成员名
- status(int, 必需): 状态（0，1，2表示回复、未及时回复）

### 请求示例
POST /branch/add  
Content-Type: application/json  
{  
  "branch_name":"海工",   
}  

### 响应结果
{  
  "status": "success",  
  "message": "Committee addition successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 支部查询接口

### 描述
该接口用于支部查询，如果参数为"all"就返回所有的支部，否则就返回查询的支部。

### 接口参数
- branch_name(string, 必需): 支部名

### 请求示例
POST /branch/query  
Content-Type: application/json  
{  
  "branch_name":"all"    
}  

### 响应结果
{  
  "status": "success",  
  "message": "",  
  "data": [  
    {"branch_name":"哈工大"},  
    {"branch_name":"双创园"}  
  ]   
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 支部删除接口

### 描述
该接口用于删除支部。

### 接口参数
- branch_name(string, 必需): 支部名称

### 请求示例
POST /branch/delete   
Content-Type: application/json  
{  
  "branch_name":"海工"  
}  

### 响应结果
{  
  "status": "success",  
  "message": "Branch delete successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",  
  "data": {}  
}  

## 支部修改接口

### 描述
该接口用于修改支部名称。

### 接口参数
- old_branch_name(string, 必需): 旧支部    
- new_branch_name(string, 必需): 新支部    

### 请求示例
POST branch/update  
Content-Type: application/json  
{  
  "old_branch_name":"哈工大",  
  "new_branch_name":"双创园"  
}  

### 响应结果
{  
  "status": "success",  
  "message": "Branch update successful.",  
  "data": {}  
}  

### 错误处理
{  
  "status": "error",  
  "message": "",    
  "data": {}  
} 

