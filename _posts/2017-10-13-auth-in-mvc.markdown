---
layout: post
title:  "Auth - php frameork comparison"
date:   2017-10-13 13:30:00 +1000
categories: Geek
---
> Authentication and authorization are required for a Web page that should be limited to certain users. Authentication is about verifying whether someone is who they claim to be. It usually involves a username and a password. Authorization is finding out if the person, once identified (i.e. authenticated), is permitted to manipulate specific resources. This is usually determined by finding out if that person is of a particular role that has access to the resources.

Yii 
=======

To cater the authentication variation, Yii introduce the class `CUserIdentity` to do the actual authentication with its method `authenticate`. Usually, this method will handle maximum password trial, session creation, password fail.

Then the identity object will carry the credentials input by user to `front-controller`, these info will be persistent (e.g. session), could be used later.
{% highlight php%}
// Login a user with the provided username and password.
$identity=new UserIdentity($username,$password);
if($identity->authenticate())
    Yii::app()->user->login($identity);
else
    echo $identity->errorMessage;
// Logout the current user
Yii::app()->user->logout();
{% endhighlight %}

For the authorization, we can use access rules to control, here's an example:
{% highlight php%}
public function accessRules() {
    return array(
        array('deny',
            'actions'=>array('create', 'edit'),
            'users'=>array('?'),
        ),
        array('allow',
            'actions'=>array('delete'),
            'roles'=>array('admin'),
        ),
        array('deny',
            'actions'=>array('delete'),
            'users'=>array('*'),
        ),
    );
}
{% endhighlight %}

An access rule can match any context parameters as `actions`, `controllers`, `users`, `roles`, `ips`, `verbs`, `expression`. For detail check [this link](http://www.yiiframework.com/doc/guide/1.1/en/topics.auth).

Using `role` is a very common solution for authorization. Even without installing any extra plugin, the Yii provides the basic role base solution. 

When we use `roles` in access rule, `CWebUser::checkAccess` will be called to return true or false. 

Business rule is the association of roles, operations and tasks. These relationship are stored in table: AuthAssignment, AuthItem, and AuthChild.
 


Laravel
=======


