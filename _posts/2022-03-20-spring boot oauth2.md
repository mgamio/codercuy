---
layout: post
title:  "Spring Boot and OAuth2"
author: moises
categories: [ Jekyll, tutorial ]
image: assets/images/oauthRoles.jpg
---
This tutorial will show how to integrate OAuth2 with Spring Security in a Spring Boot application.

The Spring Boot application I am going to use is based on my previous article: <a href="https://codersite.dev/documenting-rest-api-openapi3/">Documenting a SpringBoot REST API with OpenAPI 3</a>

## OAuth

<a href="https://datatracker.ietf.org/doc/html/rfc6749">OAuth</a> is an authorization framework many companies use to secure access to its protected resources. It performs this by using access tokens.

The token represents a delegated right of access on behalf of the resource owner.

## Roles

OAuth defines four roles

- Resource Owner – the user who grants access to a protected resource.

- Resource Server – store user’s data and http services and respond to protected resource requests using access tokens.

- Client – the application which require access to protected resources on behalf of the resource owner and with its authorization.

- Authorization Server – responsible for authenticating user’s identity and gives an authorization token.

## Authorization grant

An authorization grant is a credential representing the resource owner's authorization used by the client to obtain an access token.

OAuth defines four grant types.

- Authorization Code, for web apps that are server-side apps

- Implicit, optimized for clients implemented in a browser using a scripting language such as JavaScript

- Resource Owner Password Credentials, used when there is a high degree of trust between the resource owner and the client

- Client Credentials, used when the client is requesting access to protected resources based on an authorization previously arranged with the authorization server.

The  Client Credentials grant type is the most appropriate for server-to-server applications, such as typical B2B interactions.

### Gettin Started

We add the Spring oauth dependency to our pom.xml file.

{% highlight ruby %}
<dependency>
  <groupId>org.springframework.security.oauth.boot</groupId>
  <artifactId>spring-security-oauth2-autoconfigure</artifactId>
  <version>2.5.1</version>
</dependency>
{% endhighlight %}
