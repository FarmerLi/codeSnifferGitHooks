codeSnifferGitHooks
===================

Ŀ��
---
�淶�����ʽ����ߴ�������

˵�� 
---
* php ����淶������pear������ʶ��޸ġ�
* js ����淶����google���
* git ���ӽ��Զ��Դ�commit�ļ�����У�飬У�����ݰ�����
** php�﷨����
** php����淶
** js����淶
* У�鲻ͨ�����������ύ���룬��ͨ��ʱ�������н��ᱨ�汾��У���������嵽�����С�
* gjslint�ṩ�����ĸ�ʽ�޸�����fixjsstyle��ʹ�÷���

$ fixjsstyle path/file.js

�޸�ʱ����Ӻ���ǰ�޸��������кŲ��ᷢ���䶯�������Ҳ��������С�
* php ����淶ʾ����[http://redmine.huoyunren.com/documents/54]
* js ����淶��[http://chajn.org/jsguide/javascriptguide.html]

����
---
ʹ�ñ�������Ҫ��װ php codeSniffer, gjslint, easy_install��Դ����\<br>
*PHP_CodeSniffer
** �����ĵ�: [http://pear.php.net/package/PHP_CodeSniffer/]
** ��װ��ʹ��pear��װ���������������������
* easy_install
** ��װ��[http://peak.telecommunity.com/DevCenter/EasyInstall#installing-easy-install]
* gjslint
** �����ĵ�: [https://developers.google.com/closure/utilities/docs/linter_howto?hl=zh-CN]
** ��װ����Ҫ�Ȱ�װpython��ʹ��easy_install��װ

����
---
Git���� CatGitHook ��Ŀ��
��Cat Ŀ¼���Ƶ���pear/codesnifferĿ¼�£��磺
// ��ע���Сд
$ cp /projects/CatGitHook/Cat /usr/local/Cellar/php55/5.5.5/lib/php/PHP/CodeSniffer/Standards/Cat
��Hook/pre-commit �� Hook/config.ini���Ƶ���Ŀ.git/hooks/Ŀ¼�£�
$ cp /projects/CatGitHook/Hook/pre-commit /projects/cat/app/cat_ucenter/.git/hooks/
$ cp /projects/CatGitHook/Hook/config.ini /projects/cat/app/cat_ucenter/.git/hooks/
����config.ini
[global]
; ��Ҫ�ų����ļ�, ʹ������
exclude[] = 
; Example :
; exclude[] = /.*?tests\/.*?/
; exclude[] = /.*?xx.php/

[php]
; php ִ���ļ�λ��
path = php

[phplint]
; �Ƿ���php�﷨У��
enable = 1

[phpcs]
; �Ƿ��� phpcs У��
enable = 1
; php codesniffer ִ���ļ�����·��
path = phpcs
; phpcs ����淶
standard = Cat

[gjslint]
; �Ƿ��� gjslint
enable = 1
; gjslint ִ���ļ�����·��
path = gjslint
