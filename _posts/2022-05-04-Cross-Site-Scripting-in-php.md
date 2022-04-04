# Cross-Site Scripting (XSS)

Test environment available on [this github repo ](https://github.com/The-F00L/php-xss)

## Description and resources

### Mission brief
In this walkthrough, you'll learn about Cross-Site Scripting the most common and easiest to exploit web vulnerability.

### Description
Cross-Site Scripting vulnerability is part of injection type attack family. Injcetion type attack occurs when malicious code injected to the trusted website. This happens when we don't filter the user's inputs. We'll cover the two main type of the cross-site scripting attack. 

### Recommend reading
[Cross-Site Scripting(OWASP)](https://owasp.org/www-community/attacks/xss/)


## Mission
Let's begin!! First let's take a look at the non-persistent type. This type also called reflected Cross-Cite scripting.

There is an input form that allow to search users through the database.

![Search form](assets/XSS_search_01.png)
Let's try search for something.


![Search form](assets/XSS_search_02.png)
You can see it's display what you searched for. Now test, if we can render HTML. 


![Search form](assets/XSS_search_03.png)

Yes! Now it's time do to some nasty stuff. Let's try run JavaScript code with script HTML attribute. We can easily test this with a simple JavaScript code:
```html
<script>alert(1)</script>
```


![Search form](assets/XSS_search_04.png)
Well done! You just find your first Reflected Cross-Site Scripting vulnerability.

Let's move on, our next Cross-Site Scripting type.

The second main type is persistent type, also called stored Cross-Site Scripting.

It's occurs, when the injected script permanently stored on the target server. The injected script will execute everytime when users visit the site.

We can see input form to add user and comments to the database. It will list them.
![Search form](assets/XSS_search_05.png)
Previously, we learned that, maybe we can render HTML from user input. The submited input will be stored in database. Let's try it.


![Search form](assets/XSS_search_06.png)
Yes, we can! Now, instead a comment, try the previously learned script to test, if it's vulnerable. 


![Search form](assets/XSS_search_07.png)

Yes, it is! Now try refresh the page. Did you notice?

Everytime we refresh the page, our script will be executed as a result of our injected script is stored on the server. 
![Search form](assets/XSS_search_04.png)

## Mitigations:
Let's view the vulnerable code section. The username parameter directly put between the h1 HTML attribute, without any sanitizing.
```php
echo "<div><h2>Search result for: ".$_GET["user_name"]."</h2></div>";
```

Try using htmlspecialchars to fix this vulnerability. Unfortunately, with some advanced techniques, is still bypassable. We need to use the correct parameters. Which is the following:

```php
echo "<div><h2>Search result for: ".htmlspecialchars($_GET["user_name"],ENT_QUOTES,'UTF-8')."</h2></div>";
```

Some situations, we need to combine htmlspecailchars() with urlencode(), for example:
```html
<a href="<?php echo urlencode(htmlspecialchars($_GET[‘userURL’]));?>">Click here</a>
```

### Here are a couple of suggestions: 
- Properly sanitize user input, that you work with.
- Use, build in function like escapeString() that create properly escaped string.
- One of the most important function is htmlspecialchars() that will convert special character to HTML entities.
- Some cases htmlspacialchars() is not enough, you can use urlencode() function to be more secure.
- Every php framework has their own function that will help prevention the injection, use them.