# @domain.js/sequelize
Sequelize ORM 实例化通用模块，多库支持

[![Build status](https://travis-ci.com/domain-js/sequelize.svg?branch=master)](https://travis-ci.org/domain-js/sequelize)
[![codecov](https://codecov.io/gh/domain-js/sequelize/branch/master/graph/badge.svg)](https://codecov.io/gh/domain-js/sequelize)

# Installation
<pre>npm i @domain.js/sequelize --save</pre>

# cnf
专属配置名称 `sequelize`
| 名称 | 类型 | 必填 | 默认值 | 描述 | 样例 |
| ---- | ---- | ---- | ------ | ---- | ---- |
| db0  | object | `是` | `无` | 对应数据库连接配置信息 | { user: 'root', host: '127.0.0.1', name: 'db0' } |
| db1  | object | `否` | `无` | 对应数据库连接配置信息 | { user: 'root', host: '127.0.0.1', name: 'db1' } |
| 以此类推 | - | - | - | - | - |

* 名称也可以自定义，习惯上用 db0, db1, 这样一次类推，也可以起一个更有含义的名称, 定义多个库，是为了在业务上分库，增强并发处理能力

## cnf 完整样例
<pre>
{
  sequelize: {
    db0: {
      host: "127.0.0.1",
      port: 3306,
      name: "db_0",
    },
    db1: {
      host: "127.0.0.1",
      port: 3306,
      name: "db_1",
    },
    db2: {
      host: "127.0.0.1",
      port: 3306,
      name: "db_2",
    }
  }
}
</pre>

# deps
| 模块名 | 别名 | 用到的方法 | 描述 |
| ------ | ---- | ---------- | ---- |
| Sequelize | `无` | 构造函数 | Sequelize orm 库包，之所以通过注入的方式，是为了项目自身可以灵活控制 Sequelize 的版本 |


# Usage
| 功能 | 描述 | 样例 |
| ---- | ---- | ---- |
| db0 | 对应配置信息里 db0 的 Sequelize 实例 | sequelize.db0.query |
| db1 | 对应配置信息里 db1 的 Sequelize 实例 | sequelize.db0.query |
| 依此类推 | - | - |
