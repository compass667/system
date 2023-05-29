# 接口设计

## 用户注册接口

### 描述
该接口用于用户注册，成功时返回注册成功的信息。

### 接口参数
- user(string, 必需): 用户名
- password(string, 必需): 密码
- code()

### 接口终端点
POST /register
Content-Type: application/json
{
  
