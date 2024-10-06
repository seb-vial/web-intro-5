---
theme: light-icons
image: ./images/intro.jpg
title: Web development - Introduction | Part 5
transition: slide-left
mdc: true
layout: intro
download: true
favicon: "https://scratchmy.dev/favicon.ico"
---

<div class="mb-4 absolute top-20 left-12">
  <span class="text-6xl text-teal-400 font-500" >
    Web development<light-icon icon="code"/>
  </span>
  <div class="text-4xl text-white text-opacity-60 font-300 uppercase" >
    Introduction – Part 5
  </div>
</div>

<div class="mb-4 absolute bottom-4 right-12">
  <div class="flex gap-x-4 items-center">
    <div class="rounded-full p-0.5 shadow-lg shadow-zinc-800/5 ring-1 backdrop-blur bg-white ring-white/10">
      <img src="/images/profile.webp" sizes="4rem" class="rounded-full object-cover h-16 w-16" alt="Profile picture" width="400" height="400" loading="lazy" decoding="async">
    </div>
    <div class="flex flex-col">
      <p class="!my-1 text-xl">Sébastien VIALLEMONTEIL</p>
      <p class="!my-1">Full stack web developer</p>
      <a href="mailto:sebastien.viallemonteil@institut-agro.fr"><light-icon icon="mail" class="inline-block mb-0.5"/> sebastien.viallemonteil@institut-agro.fr</a>
    </div>
  </div>
</div>

---
layout: dynamic-image
image: ./images/forms.jpg
equal: false
left: false
---

# Forms
Sign here please.

Web forms are inevitable when it comes to websites. Login, registration, newsletter, contact, you name it.  
Forms are written in HTML but its data is sent to a server that will process it and do whatever needs to be done.

<v-click>
When using forms, you have to decide which method you want to use to send the data:
</v-click>
<v-clicks>

- **GET**: data is sent as a list of keys and values in the URL. Example: *https://example.com/index.php?<span v-mark.underline.red="1">param1</span>=<span v-mark.underline.blue="1">value1</span>&<span v-mark.underline.red="1">param2</span>=<span v-mark.underline.blue="1">value2</span>*
- **POST**: data is sent within the body of the request made to the server

</v-clicks>

---
layout: dynamic-image
image: ./images/forms.jpg
equal: false
left: false
---

# Forms
Fill in the blanks

### Creating a form
```html {*}{lines:true}
<form action="process.php" method="POST">
  <!-- Add some form fields here -->
</form>
```

<v-clicks>

- **action**: path or URL to the PHP script that will process the form data.
- **method**: you have to send you form using **GET** or **POST** method. If `method` is omitted, data is sent using the **GET** method.

</v-clicks>

---
layout: dynamic-image
image: ./images/forms.jpg
equal: false
left: false
---

# Forms
Start composing

What can you find in a form?

<v-clicks>

- Text inputs: whether the user needs to enter a name, a number, a date, an email, etc. Text inputs are the answer.
- Lists: let the user choose from a list of values.
- Checkboxes: multiple choices for the user.
- Radio buttons: the user needs to pick one option out of many.
- Buttons: either to submit the form, reset the form, or do some other action in the form.

</v-clicks>

---
layout: dynamic-image
image: ./images/forms.jpg
equal: false
left: false
---

# Forms
The attributing factor

<Transform scale="0.9">
Some attributes are important when creating form fields, some other are usefull:

<v-clicks>

- **name**: the most important attribute that needs to be set to every form field so the server can retrieve the data sent by the user.
- **value**: if set, the form field will have a default value. For buttons, it defines their label.
- **placeholder**: as the name suggests, the value set for this attribute, will appear in place of the actual value. It means that as long as the field is empty, the placeholder text will show.
- **required**: an attribute without any value that indicates to the browser the field has to be filled by the user.

</v-clicks>

<ComplementaryMessage bordered>There are many more existing attributes you can use on form fields depending on their type.<br>As any other HTML elements, form fields can possess classes and/or an id.</ComplementaryMessage>
</Transform>

---
layout: dynamic-image
image: ./images/forms.jpg
equal: false
left: false
---

# Forms
I’d love your input, user

```html {*}{lines:true}
<form action="index.php" method="POST">
  <div>
    <input name="fullname" placeholder="John Smith"/>
  </div>
  <div>
    <input name="email" type="email" placeholder="john@example.com"/>
  </div>
  <div>
    <input name="date-of-birth" type="date" placeholder="1999-01-01"/>
  </div>
  <div>
    <input type="submit" value="Send!"/>
  </div>
</form>
```

<div v-motion v-click :initial="{x: 999, y: -999}" :enter="{x: 570, y: -230}" class="[color-scheme:auto] absolute min-w-1/3 p-2 bg-gray-700 text-white dark:text-gray-800 dark:bg-white rounded-md border-2 border-teal-600 space-y-2">
  <div>
    <input class="border-gray-3 border rounded-sm p-1" name="fullname" placeholder="John Smith"/>
  </div>
  <div>
    <input class="border-gray-3 border rounded-sm p-1" name="email" type="email" placeholder="john@example.com"/>
  </div>
  <div>
    <input class="border-gray-3 border rounded-sm p-1" name="date-of-birth" type="date" placeholder="1999-01-01"/>
  </div>
  <div>
    <input type="submit" value="Send!" class="bg-gray-200 py-1 px-2 border border-gray-50 rounded-md cursor-pointer hover:bg-gray-400 hover:text-white"/>
  </div>
</div>

---
layout: dynamic-image
image: ./images/forms.jpg
equal: false
left: false
---

# Forms
If you want to make the list, select an option

```html {*}{lines:true}
<form action="index.php" method="POST">
  <select name="country">
    <!-- This option emulates a placeholder -->
    <option value="" hidden selected disabled>Pick a country</option>
    <option value="fr">France</option>
    <option value="ge">Germany</option>
    <option value="sp">Spain</option>
    <option value="it">Italy</option>
  </select>
</form>
```

<div v-motion v-click :initial="{x: 999, y: -999}" :enter="{x: 570, y: -120}" class="[color-scheme:auto] absolute min-w-1/3 p-2 bg-gray-700 text-white dark:text-gray-800 dark:bg-white rounded-md border-2 border-teal-600 text-center">
  <select name="country" class="border-gray-3 border rounded-sm p-1">
    <option value="" hidden selected disabled>Pick a country</option>
    <option value="fr">France</option>
    <option value="ge">Germany</option>
    <option value="sp">Spain</option>
    <option value="it">Italy</option>
  </select>
</div>

<ComplementaryMessage type="alert" bordered>When the form is submitted, the <strong>value</strong> of the selected option will be sent, not its displayed text. For example, if the user picks « Germany », "<strong>ge</strong>" will be sent as value for the field.</ComplementaryMessage>

---
layout: dynamic-image
image: ./images/forms.jpg
equal: false
left: false
---

# Forms
Do you check all the boxes?

```html {*}{lines:true}
<form action="index.php" method="POST">
  <span>Choice 1</span>
  <input type="checkbox" name="choice1">
  <span>Choice 2</span>
  <input type="checkbox" name="choice2">
  <span>Choice 3</span>
  <input type="checkbox" name="choice3">
</form>
```

<div v-motion v-click :initial="{x: 999, y: -999}" :enter="{x: 570, y: -120}" class="[color-scheme:auto] absolute min-w-1/3 p-2 bg-gray-700 text-white dark:text-gray-800 dark:bg-white rounded-md border-2 border-teal-600 text-center">
  <span>Choice 1</span>
  <input class="mr-2" type="checkbox" name="choice1">
  <span>Choice 2</span>
  <input class="mr-2" type="checkbox" name="choice2">
  <span>Choice 3</span>
  <input class="mr-2" type="checkbox" name="choice3">
</div>

---
layout: dynamic-image
image: ./images/forms.jpg
equal: false
left: false
---

# Forms
What radio are you on?

```html {*}{lines:true}
<form action="index.php" method="POST">
  <span>Choice 1</span>
  <input type="radio" name="radio_btn" value="choice_1" checked>
  <span>Choice 2</span>
  <input type="radio" name="radio_btn" value="choice_2">
  <span>Choice 3</span>
  <input type="radio" name="radio_btn" value="choice_3">
</form>
```

<div v-motion v-click :initial="{x: 999, y: -999}" :enter="{x: 570, y: -120}" class="[color-scheme:auto] absolute min-w-1/3 p-2 bg-gray-700 text-white dark:text-gray-800 dark:bg-white rounded-md border-2 border-teal-600 text-center">
  <span>Choice 1</span>
  <input class="mr-2" type="radio" name="radio_btn" value="choice_1" checked>
  <span>Choice 2</span>
  <input class="mr-2" type="radio" name="radio_btn" value="choice_2">
  <span>Choice 3</span>
  <input class="mr-2" type="radio" name="radio_btn" value="choice_3">
</div>

<ComplementaryMessage type="alert" bordered>Notice all inputs of type radio have the <strong>same name</strong> in order to be part of the same radio group</ComplementaryMessage>

---
layout: dynamic-image
image: ./images/forms.jpg
equal: false
left: false
---

# Forms
Expand the area

Simple text inputs don’t leave much space for user to express themselves. If you need to gather detailed information from your users, try `textarea`

<div v-click>

```html {*}{lines:true}
<form action="index.php" method="POST">
  <textarea name="description" rows="5" cols="30" 
    placeholder="Share your thoughts"></textarea>
  <textarea name="description" rows="3" cols="10" 
    placeholder="What else?"></textarea>
</form>
```

</div>
<div v-motion v-click :initial="{x: 999, y: -999}" :enter="{x: 570, y: -220}" class="[color-scheme:auto] absolute min-w-1/3 p-2 bg-gray-700 text-white dark:text-gray-800 dark:bg-white rounded-md border-2 border-teal-600 text-center">
  <textarea class="border-gray-3 border rounded-sm p-1" name="description" rows="5" cols="30"placeholder="Share your thoughts"></textarea>
  <div>
    <textarea class="border-gray-3 border rounded-sm p-1" name="description" rows="3" cols="10"placeholder="What else?"></textarea>
  </div>
</div>

<ComplementaryMessage bordered><strong>rows</strong> and <strong>cols</strong> attributes are optional and define the default number of lines and columns for the textarea.</ComplementaryMessage>

---
layout: dynamic-image
image: ./images/forms.jpg
equal: false
left: false
---

# Forms
Make it, label it

Labels are great to caption your form fields and give better accessibility to users as they are associated to one specific field. If a user clicks a label, the corresponding field will obtain the focus. In addition, screen readers can read the label to the user.

<div v-click>

```html {*}{lines:true}
<form action="index.php" method="POST">
  <label for="first_name">First name</label>
  <input type="text" name="first_name" id="first_name"
    placeholder="John" />
  <label for="last_name">Last name</label>
  <input type="text" name="last_name" id="last_name"
    placeholder="Smith" />
  <label for="newsletter">Do you want to subscribe?</label>
  <input type="checkbox" name="subscribe" id="newsletter" />
</form>
```

</div>

<div v-motion v-click :initial="{x: 999, y: -999}" :enter="{x: 570, y: -250}" class="[color-scheme:auto] absolute min-w-1/3 p-2 bg-gray-700 text-white dark:text-gray-800 dark:bg-white rounded-md border-2 border-teal-600 flex flex-col gap-1 items-start">
  <label for="first_name">First name</label>
  <input class="border-gray-3 border rounded-sm p-1" type="text" name="first_name" id="first_name" placeholder="John"/>
  <label for="last_name">Last name</label>
  <input class="border-gray-3 border rounded-sm p-1" type="text" name="last_name" id="last_name" placeholder="Smith"/>
  <label for="newsletter">Do you want to subscribe?</label>
  <input type="checkbox" name="subscribe" id="newsletter" />
</div>

<ComplementaryMessage type="alert" bordered>To associate a label to a field, label’s <strong>for</strong> attribute and field’s <strong>id</strong> attribute should match.</ComplementaryMessage>

---
layout: dynamic-image
image: ./images/forms.jpg
equal: false
left: false
---

# Forms
Putting everything together

<Transform scale="0.9">
```html {*}{lines:true}
<form action="index.php" method="POST">
  <div>
    <label for="last_name">Last name</label>
    <input type="text" name="last_name" id="last_name" required>
  </div>
  <div>
    <label for="first_name">First name</label>
    <input type="text" name="first_name" id="first_name" required>
  </div>
  <div>
    <label for="email">Email</label>
    <input type="email" name="email" id="email" required>
  </div>
  <div>
    <label for="password">Password</label>
    <input type="password" name="password" id="password" required>
  </div>
  <div>
    <label for="newsletter">Newsletter</label>
    <input type="checkbox" name="newsletter" id="newsletter">
  </div>
  <div>
    <input type="submit" value="Send!">
  </div>
</form>
```
</Transform>

<div v-motion v-click :initial="{x: 999, y: -999}" :enter="{x: 570, y: -400}" class="[color-scheme:auto] absolute min-w-1/3 p-2 bg-gray-700 text-white dark:text-gray-800 dark:bg-white rounded-md border-2 border-teal-600 flex flex-col gap-2 items-start">
  <div>
    <label for="last_name2">Last name</label>
    <input class="border-gray-3 border rounded-sm p-1 ml-2" type="text" name="last_name" id="last_name2" required>
  </div>
  <div>
    <label for="first_name2">First name</label>
    <input class="border-gray-3 border rounded-sm p-1 ml-2" type="text" name="first_name" id="first_name2" required>
  </div>
  <div>
    <label for="email">Email</label>
    <input class="border-gray-3 border rounded-sm p-1 ml-2" type="email" name="email" id="email" required>
  </div>
  <div>
    <label for="password">Password</label>
    <input class="border-gray-3 border rounded-sm p-1 ml-2" type="password" name="password" id="password" required>
  </div>
  <div>
    <label for="newsletter2">Newsletter</label>
    <input class="ml-2" type="checkbox" name="newsletter" id="newsletter2">
  </div>
  <div>
    <input type="submit" value="Send!" class="bg-gray-200 py-1 px-2 border border-gray-50 rounded-md cursor-pointer hover:bg-gray-400 hover:text-white">
  </div>
</div>

---
layout: intro
image: ./images/foggy.jpg
---

<h1 class="absolute left-12 bottom-12 !text-5xl !line-height-relaxed">You have a long road ahead of you</h1>
<p class="!opacity-80 absolute left-12 bottom-6">One step at a time.</p>

<img src="/images/gifs/bob.webp" class="absolute right-12 top-[20%] border-2 border-white rounded-md" alt="Bob Gif" />

---
layout: intro
image: ./images/quiz.jpg
---

<h1 class="absolute left-12 bottom-12">Quiz time!</h1>
<p class="!opacity-80 absolute left-12 bottom-6">Why the hell not 🤷‍♂️</p>

<img src="/images/gifs/mouahahah.webp" class="absolute right-12 top-[20%] border-2 border-white rounded-m max-h-[50%]" alt="Mouahahah Gif" />

---
layout: dynamic-image
image: ./images/question.jpg
equal: false
---

# Form, form and… form again
Pay attention to the form

<v-clicks>

- Create a POST form leading to a **process.php** page
- Add a required input text for the last name
- Add a required input text for the first name
- Add an input of type *number** for the age
- Add a select list for the gender
- Add a submit button
- Each field has its associated **label**

</v-clicks>

---
layout: dynamic-image
image: ./images/time.jpg
equal: false
left: false
---

# Time’s up!
Who wants to write some code?

<Transform scale="0.9">
```html {*|1,25|2-5|6-9|10-13|14-21|22-24|all}{lines:true}
<form action="process.php" method="POST">
  <div>
    <label for="last_name">Last name</label>
    <input type="text" id="last_name" name="last_name" required/>
  </div>
  <div>
    <label for="first_name">First name</label>
    <input type="text" id="first_name" name="first_name" required/>
  </div>
  <div>
    <label for="age">Age</label>
    <input type="number" id="age" name="age"/>
  </div>
  <div>
    <label for="gender">Gender</label>
    <select id="gender" name="gender">
      <option value="m">Male</option>
      <option value="f">Female</option>
      <option value="n">None of the above</option>
    </select>
  </div>
  <div>
    <input type="submit" />
  </div>
</form>
```
</Transform>

<div v-motion v-click :initial="{x: 999, y: -999}" :enter="{x: 570, y: -400}" class="[color-scheme:auto] absolute min-w-1/3 p-2 bg-gray-700 text-white dark:text-gray-800 dark:bg-white rounded-md border-2 border-teal-600 flex flex-col gap-2 items-start">
  <div>
    <label for="last_name3">Last name</label>
    <input class="border-gray-3 border rounded-sm p-1 ml-2" type="text" name="last_name" id="last_name3" required>
  </div>
  <div>
    <label for="first_name3">First name</label>
    <input class="border-gray-3 border rounded-sm p-1 ml-2" type="text" name="first_name" id="first_name3" required>
  </div>
  <div>
    <label for="age">Age</label>
    <input class="border-gray-3 border rounded-sm p-1 ml-2" type="number" name="age" id="age">
  </div>
  <div>
    <label for="gender">Gender</label>
    <select id="gender" name="gender" class="border-gray-3 border rounded-sm p-1 ml-2">
      <option value="m">Male</option>
      <option value="f">Female</option>
      <option value="n">None of the above</option>
    </select>
  </div>
  <div>
    <input type="submit" class="bg-gray-200 py-1 px-2 border border-gray-50 rounded-md cursor-pointer hover:bg-gray-400 hover:text-white">
  </div>
</div>

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# Web servers
Serve your website to users, and more

Local development will only get you so far, at some point you need to put your website online so visitors can admire it.

Hosting you website on a server will allow you to:

<v-clicks>

- Give worldwide users access to your website
- Interact with databases so you can read and save data
- Use online services to get or post information

</v-clicks>

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# Web servers
Serve your website to users, and more

You can also use a web server while programming locally, here is why:

<v-clicks>

- Browsers (**clients**) can only read and comprehend HMTL, CSS and Javascript languages.
- When you need to interact with a database or an online service, you need to use a **backend** or server language.
- When using forms, browsers can only display them, not retrieve values the user has sent.

</v-clicks>

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# Web servers
How does that work exactly?

When using a web sever, you have to use a URL to reach your website, whether it's a local or distant server.  
In the end, the server will return HTML and CSS the browser (client) will be able to render.

<div v-click class="[color-scheme:auto] p-4 bg-gray-700 text-white dark:text-gray-800 dark:bg-white rounded-md border-2 border-teal-600">
  <div class="flex gap-12 items-center">
    <div class="text-center">
      <hugeicons-user class="text-3xl text-gray-700"/>
      <h4 class="text-lg font-semibold text-gray-700">Client</h4>
    </div>
    <div class="min-h-[200px] flex-1 shrink-0 flex flex-col justify-between">
      <div class="relative flex flex-col border-b-2 border-red text-center italic pb-2 after:content-['>'] after:absolute after:text-red after:right-[-15px] -after:bottom-[15px] after:text-2xl"><span>https://mywebsite.fr</span><span class="text-sm text-gray-600 font-light uppercase">(HTTP Request)</span></div>
      <div v-click="3" class="relative flex flex-col border-t-2 border-red text-center italic pb-2 after:content-['<'] after:absolute after:text-red after:left-[-15px] -after:top-[20px] after:text-2xl"><span>Sending result</span><span class="text-sm text-gray-600 font-light uppercase">(HTML / CSS)</span></div>
    </div>
    <div class="text-center flex flex-col gap-4">
      <div v-if="$clicks < 2">
        <hugeicons-cloud-server class="text-3xl text-gray-700"/>
        <h4 class="text-lg font-semibold text-gray-700">Server</h4>
      </div>
      <div v-if="$clicks === 2">
        <hugeicons-loading-02 class="animate-spin text-3xl text-amber-700"/>
        <h4 class="text-xs font-semibold text-gray-700">Processing<br>request...</h4>
      </div>
      <div v-if="$clicks === 3">
        <hugeicons-cloud-saving-done-01 class="animate-pulse text-3xl text-green-700"/>
        <h4 class="text-lg font-semibold text-gray-700">Done!</h4>
      </div>
    </div>
  </div>
</div>

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# PHP
A server language

To interact with databases, other web services, or to retrieve data sent by the client you need a language interpreted by the server. Web servers can comprehend many languages (Python, PHP, Javascript, Ruby, Go, etc.). In this course, our focus will be **PHP**.

<div v-click>

```php {*}{lines:true}
<?php /* PHP opening tag */
// A small sneak peek
$name = $_POST['name'];
echo '<h2>Hi ' . $name . '!</h2>'
?> /* PHP closing tag */
```

</div>

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# PHP
Create variables

```php {*}{lines:true}
<?php
$str = 'Hi there !';
$number = 15;
$decimal = 1.5;
$boolean = true;
$tab = ['zero', 'foo', 'bar'];
```

<ComplementaryMessage bordered>PHP was first created with implicit typing, meaning that variables can contain any type of data: integer, booleans, strings, arrays, etc.</ComplementaryMessage>
<ComplementaryMessage bordered>When using fuctions and classes, PHP now supports explicit typing.</ComplementaryMessage>

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# PHP
Combining PHP and HTML

As it was demonstrated before, the web server needs to return HTML and CSS to the client (browser) which will then display it.  
PHP offers a special keyword which instructs the server to render a string: **echo**

```php {*}{lines:true}
<?php /* PHP opening tag */
$user = 'Seb';
echo '<em>Hi ' . $user . ' !</em>';
// Same result, just another way of combining strings and variables
echo "<em>Hi {$user} !</em>";
```

<div v-click class="[color-scheme:auto] mt-4 p-4 bg-gray-700 text-white dark:text-gray-800 dark:bg-white rounded-md border-2 border-teal-600 text-center">
  <em>Hi Seb!</em>
</div>

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# PHP
Combining PHP and HTML (larger scale)

```php {*}{lines:true}
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <title>My page</title>
    <link type="text/css" rel="stylesheet" href="styles.css" />
  </head>
  <body>
    <?php /* PHP opening tag */
    $user = 'Seb';
    echo '<em>Hi ' . $user . ' !</em>';
    // Same result, just another way of combining strings and variables
    echo "<em>Hi {$user} !</em>";
    ?> // PHP closing tag
  </body>
</html>
```

<ComplementaryMessage bordered>PHP files can contain HTML outside PHP opening and closing tags. The web server will send them as is to the client.</ComplementaryMessage>

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# PHP
Conditional programming

```php {*}{lines:true}
<?php /* PHP opening tag */
/*
  The 'date' function gets the current date.
  'G' means we only want the hour, based on the '24h' system
  ('g' would be based on the '12h' system)
*/
$now = date('G');
if($now > 6 && $now < 12) {
  echo 'Good Morning';
}
else if($now >= 12 && $now < 18) {
  echo 'Good Afternoon';
}
else {
  echo 'Good Night';
}
```

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# PHP
You’re in the loop

### for loop
```php {*}{lines:true}
<ul>
  <?php /* PHP opening tag */
  $myArr = ['Dog', 'Cat', 'Squirrel', 'Fox'];
  for ($i = 0; $i < count($myArr); $i++) {
    echo '<li>' . $myArr[$i] . '</li>';
  }
  ?>
</ul>
```

<div v-click>

### foreach loop
```php {*}{lines:true}
<ul>
  <?php /* PHP opening tag */
  $myArr = ['Dog', 'Cat', 'Squirrel', 'Fox'];
  foreach ($myArr as $animal) {
    echo '<li>' . $animal . '</li>';
  }
  ?>
</ul>
```

</div>

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# PHP
Useful functions

PHP comes with many utility functions out of the box. You can browse the [documentation](https://php.net) whenever you are feeling lost.

<v-clicks>

- [**strlen**](https://www.php.net/manual/en/function.strlen.php): returns the number of characters in a string
- [**strtlower**](https://www.php.net/manual/en/function.strtolower.php): transforms the given string to a lowercase string (good for comparing strings)
- [**strtupper**](https://www.php.net/manual/en/function.strtoupper.php): transforms the given string to an uppercase string (good for comparing strings)
- [**substr**](https://www.php.net/manual/en/function.substr.php): extracts part of string
- [**isset**](https://www.php.net/manual/en/function.isset.php): checks if a variable exists and is not null
- [**empty**](https://www.php.net/manual/en/function.empty.php): checks if a variable exists and if its value does not equal **false** (see [this](https://www.php.net/manual/en/language.types.boolean.php#language.types.boolean.casting))
- [**var_dump**](https://www.php.net/manual/en/function.var-dump.php): dumps information about the given variable, good for debugging

</v-clicks>

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# PHP
Get form data

The browser can display a form and the user will fill it out but its data is then sent to the server. PHP allows you to retrieve what the user filled out (or missed).

<div v-click>

### Retrieve data sent with « GET » method
```php {*}{lines:true}
<?php
if (empty($_GET['name'])) {
  echo '<p class="error">You did not fill out your name!</p>';
} else {
  echo 'Hi ' . $_GET['name'] . '!';
}
```

</div>
<div v-click>

### Retrieve data sent with « POST » method
```php {*}{lines:true}
<?php
if (empty($_POST['name'])) {
  echo '<p class="error">You did not fill out your name!</p>';
} else {
  echo 'Hi ' . $_POST['name'] . '!';
}
```

</div>

---
layout: dynamic-image
image: ./images/server.jpg
equal: false
---

# PHP
Including common code

Until now you had to copy and paste your common HTML code to every page (html, head, meta, title, body, header, nav, footer, etc.).  
You can extract that code to PHP files that will be **included** to everyone of your pages.

<div v-click>

```php {*}{lines:true}
<?php
include('header.php'); // Doctype, html, head, etc.
?>
<div id="content">
...
</div>
<?php
include('footer.php'); // Footer, closing body and html
?>
```

</div>
<ComplementaryMessage type="alert" bordered>Using this method implicates transforming all your HTML files to PHP files.</ComplementaryMessage>


---
layout: intro
image: ./images/thinker.jpg
---

<div class="absolute inset-0 flex justify-center items-center">
  <h1 class="text-6xl !text-white font-500">Questions?</h1>
</div>

<div class="absolute bottom-4 right-4 opacity-50 text-sm italic">
  © Unsplash<br>© Giphy
</div>
