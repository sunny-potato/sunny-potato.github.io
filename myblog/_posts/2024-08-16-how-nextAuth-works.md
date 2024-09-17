---
title: How NextAuth works
author: Sunhee Cho
date: 2024-08-16 11:33:00 +0800
categories: [Blogging, Demo]
tags: [typography]
pin: true
math: true
mermaid: true
image:
  path: /commons/devices-mockup.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: Responsive rendering of Chirpy theme on multiple devices.
---

2 session strategies
(https://next-auth.js.org/getting-started/upgrade-v4#session-strategy)

1. JWT : an encrypted JWT(JWE) stored in the session cookie.

2. The database adapter :

- handles token in the database
  database is used for persisting users, OAuth accountsm email sign in tokens and sessions.
- the session cookie will only contain a `sessionToken` value,
  which is used to look up the session in the database.

authentication vs authorization
authentication : check who the person that have access to a application is with login
authorization : give a right to access data by returning user information via API requrest

3. how OAuth 2.0 and OpenId connect work
   forms authentication (=simple login)

- username & password
- verify them in DB via back-end
- session ID? in brower (ex Cookies ) to keep track of user
- downside : security and maintainance ?

- OAuth
  grant access to API
  OAuth flow
  front + back end channel
  designed to be used for authorization to exchange permisssion using access token(=JSON WEB TOKEN =JWT) & scope & content
  no way to check who the person is

- OpenId connect
  added OpenId connect to the top of OAuth 2.0
  (=extra stuff in OAuth flow ) = OpenID flow
  designed for authentication
  OpenID in scope and get back id token as respnese type
  use ID-token(=JSON WEB TOKEN =JWT)
  ID-token consist of ???? user info. signature(=verify that ID Token has not beed modified)
  userinfo endpoint : if want more info about user

- Reference
  OAuth 2.0 and OpenID Connect : https://www.youtube.com/watch?v=996OiexHze0&list=PPSV
  What is OAuth 2.0? : https://auth0.com/intro-to-iam/what-is-oauth-2

6. how to manage access token
   when authorization is grant, application gets tokens.

- (possible) type of tokens

1. Access token
2. Refresh token (optional)
3. Id token (when Open ID connect is used)

- where to store tokens

1.

- Reference
  Storing OAuth Tokens: https://fusionauth.io/articles/oauth/oauth-token-storage#server-side-token-storage

5. Vipps

- when authorization is grant
  1. when authorization is grant, Vipps gives some information including access token.
     when the back-end sends API with the acces token from Vipps to get access to the user's resource.
  2.
