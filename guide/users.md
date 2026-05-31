# 用户管理

New API 支持多用户系统，管理员可以管理所有用户。

## 用户角色

| 角色 | 权限 |
|------|------|
| 管理员 | 完全控制权限 |
| 普通用户 | 使用 API，管理自己的令牌 |
| 受限用户 | 有限的 API 使用权限 |

## 管理员操作

### 访问管理后台

默认管理员账号：
- 用户名：`root`
- 密码：`123456`

> 首次登录后请立即修改密码！

### 用户列表

进入 **控制台** -> **用户管理** 查看所有用户。

### 添加用户

1. 点击 **添加用户**
2. 填写用户名和密码
3. 设置角色和额度
4. 点击提交

### 编辑用户

可修改：
- 用户角色
- 额度限制
- 用户状态（启用/禁用）

### 删除用户

> 警告：删除用户会同时删除其所有令牌和数据。

## 用户注册

### 开启注册

在环境变量中设置：
```bash
ENABLE_REGISTRATION=true
```

### 关闭注册

```bash
ENABLE_REGISTRATION=false
```

### 邀请码注册

可配置邀请码模式，需要邀请码才能注册。

## 额度管理

### 分配额度

```bash
# 通过 API 分配用户额度
curl -X PUT http://localhost:3000/api/user/1 \
  -H "Authorization: Bearer admin-token" \
  -H "Content-Type: application/json" \
  -d '{"quota": 10000}'
```

### 额度类型

| 类型 | 说明 |
|------|------|
| 总额度 | 用户可用的总金额 |
| 已用额度 | 已消耗的金额 |
| 剩余额度 | 剩余可用金额 |

## 用户自助操作

普通用户可以：
- 修改密码
- 生成 API 令牌
- 查看使用统计
- 查看额度余额

## 安全设置

### 登录限流

防止暴力破解：
```bash
ENABLE_LOGIN_RATE_LIMIT=true
```

### 密码策略

建议要求：
- 最小长度 8 位
- 包含大小写字母
- 包含数字

### Session 管理

Session 超时设置：
```bash
SESSION_TTL=86400  # 24小时
```

## 批量操作

### 批量导入用户

通过 API 批量创建用户：

```bash
curl -X POST http://localhost:3000/api/user/batch \
  -H "Authorization: Bearer admin-token" \
  -H "Content-Type: application/json" \
  -d '{
    "users": [
      {"username": "user1", "password": "pass1", "quota": 1000},
      {"username": "user2", "password": "pass2", "quota": 1000}
    ]
  }'
```

### 批量设置额度

```bash
curl -X POST http://localhost:3000/api/user/batch-quota \
  -H "Authorization: Bearer admin-token" \
  -H "Content-Type: application/json" \
  -d '{"user_ids": [1, 2, 3], "quota": 5000}'
```

## 最佳实践

1. **最小权限原则**: 只授予必要的权限
2. **定期审计**: 检查用户活动
3. **额度控制**: 设置合理的使用上限
4. **强密码策略**: 要求强密码
5. **禁用无用账号**: 及时禁用不活跃用户
