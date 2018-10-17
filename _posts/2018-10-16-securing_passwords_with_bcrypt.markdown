---
layout: post
title:      "Securing Passwords with bcrypt"
date:       2018-10-16 16:58:35 -0400
permalink:  securing_passwords_with_bcrypt
---


&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bcrypt is a hashing function created by Niels Provos and David Mazières. It protects user passwords through a process of salting and hashing. Hashing scrambles the password in order to make it indecipherable. Not all hashes are created equal though. Data breaches often lead to the release of passwords, a huge problem since users often reuse passwords across multiple sites. When Patreon’s user data was breached though, their use of bcrypt successfully kept user passwords indecipherable. However, Ashely Madison’s use of bcrypt did not successfully protect user passwords as over 15 million of their passwords were first stored with a hashing algorithm called MD5. The passwords that had only ever been hashed with bcrypt remained safe. 

 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;With bcrypt, a user's actual password is never stored in your database. Instead, whenever he reenters his password to sign in, it is rehashed with the same algorithm and that is compared to the hashed password in your database. When hackers attempt to decrypt hashed passwords they use this same system, trying out different passwords in the hashing algorithm and comparing the result to their stolen data. So while it is technically possible to decrypt this stolen data, hashing makes it much more difficult. One method they might use to help is a rainbow table, allowing them to compare the encrypted password to many other passwords in their decrypted and encrypted forms. An extra step bcrypt takes to further protect encrypted passwords is salting. Salting adds a random string to your encrypted passwords, making searching using a rainbow table much more difficult. 
 
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Bcrypt has shown itself to be reliable. Here’s how you can implement it in your application. Once you’ve required bcrypt in your gemfile, add a password_digest column to your user table. You will then have access to the has_secure_password method through bcrypt. The has_secure_password method is where bcrypt hashing and salting is actually implemented. This method will not allow a user to be saved to the database unless he has a password and the password is equal to or less than 72 bytes. You can customize your validations by setting validations: false. The has_secure_password method gives us access to several instance methods: authenticate, password=, and password_confirmation=. If the password being passed in is not empty, password= will encrypt the password into password_digest. You can also require that users confirm their password by using password_confirmation and requiring a password_confirmation form field. 
When creating a new user use an if/else statement to check @user && @user.authenticate(params[:user][:password]). If your password passes the validations, this should return self. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Users depend on your program to protect their data and hashing and salting using bcrypt is one of the best ways to do that. 

