ghost-on-heroku
===============

��ʾҳ��studiofnt.herokuapp.com


��һ������heroku��Ϊnodejs����

$ vi Procfile 

���룺web: node index.js --production

esc���أ�:wq�˳�



��һ�֣���config.js�����production��ε�host����addon�����postsql������ʺź����뼴��

Ȼ��git clone�������git��ǵ�

$ git init                        //�����ͬ��
$ git add .                      //�������ӵ����git������
$ git commit -m "���������д"  //�������ͬ����ע��
$ git push                     //�ύ��heroku�汾������

ע�⣺ͬ������Զ�npm Install����package.json����Ķ�����



�ڶ��֣���heroku�����Env����������˼��
��config�����database�ĳ����£�

database: {
        client: 'postgres',
        connection: {
              host: process.env.POSTGRES_HOST,
              user: process.env.POSTGRES_USER,
              password: process.env.POSTGRES_PASSWORD,
              database: process.env.POSTGRES_DATABASE,
              port: '5432'
        }

Ȼ��������Env����Ȼ���ȵð�heroku login ��¼����ʺź����룬��ʾ������publickey������y��֮��heroku keys:add ~/.ssh/id_rsa.pub  ��һ��win�µ�·����C:\Documents and Settings\Administrator\.ssh���ɵ���Կ������

$ heroku config:set POSTGRES_HOST=host
$ heroku config:set POSTGRES_USER=user
$ heroku config:set POSTGRES_PASSWORD=password
$ heroku config:set POSTGRES_DATABASE=database

���ú��˼���~



