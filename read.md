ghost-on-heroku
===============

演示页：studiofnt.herokuapp.com


第一步：把heroku作为nodejs环境

$ vi Procfile 

插入：web: node index.js --production

esc返回，:wq退出



第一种：把config.js里面的production这段的host对照addon上面的postsql上面的帐号和密码即可

然后git clone了这个本git后记得

$ git init                        //这个是同步
$ git add .                      //这个是添加到你的git库里面
$ git commit -m "这里随便你写"  //这个是你同步的注释
$ git push                     //提交到heroku版本库里面

注意：同步后会自动npm Install所有package.json上面的东西。



第二种：在heroku上添加Env（环境的意思）
在config上面的database改成如下：

database: {
        client: 'postgres',
        connection: {
              host: process.env.POSTGRES_HOST,
              user: process.env.POSTGRES_USER,
              password: process.env.POSTGRES_PASSWORD,
              database: process.env.POSTGRES_DATABASE,
              port: '5432'
        }

然后在设置Env（当然你先得把heroku login 登录你的帐号和密码，提示你输入publickey点输入y，之后heroku keys:add ~/.ssh/id_rsa.pub  【一般win下的路径是C:\Documents and Settings\Administrator\.ssh生成的密钥。】）

$ heroku config:set POSTGRES_HOST=host
$ heroku config:set POSTGRES_USER=user
$ heroku config:set POSTGRES_PASSWORD=password
$ heroku config:set POSTGRES_DATABASE=database

设置好了即可~



