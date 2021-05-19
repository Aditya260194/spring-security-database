# spring-security-database

1. To enable spring-security, just need to user spring-security-starter pack. It will by default add filters so our request get intercepted.
2. After adding it will ask for login without implementing any page for it. All urls will need to be authenticated.
3. By Default user is user and password is generated in console.

Setup our on user

4. To updated default user, we can add user in properties file.

Configure security

5. Spring security uses AuthenticationManager to authenticate user. We cant change AUthenticationManager directly, instead we use AuthenticationManagerBuilder 
to configure AuthenticationManager.
6. We configure it using WebSecurityConfigurerAdapter and overide the configure method for AuthenticationManagerBuilder.

In-Memory Auth

7. We updated AUthentication to in-memory authentication with user, password and role. Also we added Password Encoder bean as password cant be sent to app as clear text.
It should be encoded. But here we used NoOpPasswordEncoder which do not encode password and store as clear text :-D.
8. Now Spring will authenticate against the user na dpassword we provided in in-memory authentication and not use default ones.

Authorization of apis - (/ - all without authentication , /user - by authenticated users , /admin - only by admin role)

9. We need to configure HttpSecurity, which we can by using WebSecurityConfigurerAdapter and overide the configure method for HttpSecurity
10. We tested with configuring authotization of all urls to admin role, other roles were not able to access.
There is /logout by default created by spring using which we can logout.
11. We configured the authorization for all roles.
