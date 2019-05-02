# Flask - Lecture 2 - cs50's web programming with python and javascript

## published on Feb 6 2018



- python is an interpreted programming language.
  
- Interpreted programming language means writing code in the python programming language, then we run the program using python interpreter (a program that reads python code line by line and interprets its) and executes it and we get the result.

  ## hello.py 

```python
print("Hello, World!")
```

[.py extension tells its a python file (i.e) files that contains python code]

## How to run it:

- open terminal in which the actual python files is located, then type

```
python3 python_source_file_name.py
```


Breaking down the single line:
------------------------------
```python
print("Hello, World")
```

print

- function name [a name that actually doing something, in this case, it prints something to screen]

"Hello, World" 

- we have given string as arguments

("Hello, World") 

- function argument [Information we have give to the function, in this case, what it needs to print to the screen]


name.py
--------

```python
name = input()              # result of input() function stored in name variable              
print(f"hello, {name}!")
```

name 

- variable name used to store data or information inside our python program

input()

-  It is a function in python that asks user to provide input at command line.


- when you hit enter in command line, whatever you typed in, gets returned from function.

Format string: (available in python 3.6)
----------------------------------------

- using format strings, we take a string and substitute information to the placeholder area (i.e) {}

- f indicates format strings used on strings.

variables.py
-------------

- we can also store different kinds of data (other than strings) in a variable.

```python
i = 28			# Integer
print(f"i is {i}")

f = 2.8			# Floating point (decimal)
print(f"f is {f}")

b = True
print(f"b is {b}")	# Boolean (True or False) [Note: T caps for True and F caps for False]

n = None
print(f"n is {n}")	# None (that represents that variable isn't storing any information)

```

conditions.py
---------------

- using conditions, we can decide which code we want to execute based on True or False.

- indentation is must.

- If first condition is true, it executes the statement and exits, and never checks other conditions even if the next conditions is true.

```python
x = 28

if x > 0:
	print("x is positive")
elif x < 0:
	print("x is negative")
else:
	print("x is zero")
```


sequences.py
-------------

```python
name = "Alice"
coordinates = (10.00, 14.33)
names = ["Alices", "Bob", "charlie"]
```

- A string is a sequence of characters. we take first character, second character and so on from string.

- python tuple is a way of grouping a couple of values together. If you wanted to store xy coordinates in python program, rather than storing in two separate variables such as x and y, we can store it together under a single name.

- python list is powerful datatype that allows us to store different kinds of data together under single name.

- list in python is denoted by square brackets [] and each of the elements inside the list is separated by comma.


How to access individual element from a sequence:
-------------------------------------------------


```python
>>name = "Alice"
>>name[0]
'A'
```

- To access the element from a sequence, we use index value

- index value starts at 0 (zero)

- index 0 represents first element in the sequence and so on.


```python
>>coordinates = (10.0, 20.0)
>>coordinates[1]
20.0
```


```python
>>names = ["Alice", "Bob", "charlie"]
>>names[0]
'Alice'
>>names[1]
'Bob'
```

- when you access an element outside the index range, you will get an python exception.


```python
>>names[3]
Traceback (most recent call last)
file "<stdin>", line 1 in module
IndexError: list index out of range
```


Loops
-----

```python
for i in range(5):
	print(i)
```

- range() function returns a number of elements. Think like,

range(3) ------> 0 1 2
generate a sequence of number

- loops are used to repeatedly execute set of code number of times.

- we can also loop through each element in the sequence type like list, strings, tuples.


```python
names = ["Alice", "Bob", "charlie"]

for name in names:
	print(name)
```

Note: It is not strict that all elements in a list has to be on same type but it is good design to use same type.

```python
l = [28, "Alice", True]
```

sets (more advanced datatypes)
------------------------------

- sets is a collection of items

- it contains unique values (no duplicated values)

```python
s = set()
s.add(1)
s.add(3)
s.add(5)
s.add(3)
print(s)
```

dictionaries
--------------

- key-value pairs.

- map certain values to other values.

```python
ages = {'Alice":22, "bob":27}
ages["charlie"] = 30	# adding another element into the directory
ages["Alice"] += 1		# modifying or editing value of an element (here it updates its 						value by 1)
```

functions.py
------------

```python
def square(x):
	return x * x

for i in range(10):
	print("{}.squared is {}".format(i, square(i)))
```

def ----> function definition keyword
square ----> function name
(x) ----> argument

*---> multiplication symbol

- similar to print(), range(), input() pre-defined function, in this case, we are creating a user defined functions (i.e) our own function.

Notes:

- you need to define the function definition before calling it. function call must be below the function definition.
- once you written the functions in one file, you can use them in other files.
-  you can also use function written by other people by referring to it.

modules.py
----------

```python
from functions import square

print(square(10))
```

- If we try to execute this code, we get 10 lines of squared is and finally 100. the reason for this, it executes everything inside the functions.py when i use "from functions import square". this isn't what we wanted.

- solution for this is: put all the code I want to run only when I actually run this function file.

- we need to define a main() function that runs when you try and run functions.py

- finally 

  ```python
  if __name__ == "__main__":
  ```

   means if i am currently running this file, then run the main() function.

```python
def square(x):
	return x * x

def main():
	for i in range(10):
		print("{}.squared is {}".format(i, square(i)))

if __name__ == "__main__":
	main()
```

classes.py
----------

```python
class point:
	def __init__(self, x, y):
		self.x= x
		self.y = y

p = point(3, 5)
print(p.x)
print(p.y)
```

class ----> keyword
point ----> class name
__init__ ----> special method
def ----> function definition
x, y ----> local variables
self --> [p] = point(3, 5)	

- A class is used to define new types in python. it already have built-in types for representing list, strings, Boolean values.

- __init__ function saying when I create a new point what information do i need.

- self is a variable that refers to the point itself (i.e) object i'm creating.

- self.x = x, self is name refering to the point object that we have created.
  .x ---> I want to access a particular attribute of the self. (point that we created)


HTTP (hyper text transfer protocol)
-------------------------------------

- HTTP is a way to interact and communicate between computers and servers.

- when you type a website address and hit return, that doing is sending an http request to servers.

- the server receives the request and process it and understands what i'm asking for, what i'm searching for news or images and responds back to the browser

- the server understands the request and give back the corresponding information i.e HTTP Response to the web browser and displays it to the user.

- writing code that takes care of server side processing, receive request, figure out what they are asking for and give back them response.

Flask
-----

- flask is a micro framework written in python.
- flask code is generally stored inside a file called application.py, it is going to be main file of the flask application.

```python
from flask import Flask

app = Flask(__name__)	# I want to create a new web application that will be a flask app

@app.route("/")
def index():
	return "Hello, World!"

# flask ----> filename
# Flask ----> either class or function
# __name__ ----> just representing the current file
```
@app.route("/") 

- flask is designed in terms of route. route is just part of the url you type in order to determine which page you want to request.
- slash represents the default or index page
- whenever the user goes to the slash(default) page, the function immediately below it, is the function that will run.
-  it is special line called decorator.just assume we just tie-ing the function to index page.

To run:
-------
```python
flask run
```

## Does Flask know to look for an application named application.py?

No, you need to set an environmental variable to tell flask to execute the application.py

```python
export FLASK_APP = application.py
```

## Templates

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
	return render_template("index.html")
```
- we are importing a function from flask called render_template	

- Rather than returning a string, we return render_template("index.html"). this line says, take index.html and render it and display it in browser.

- render_template() function immediately look for webpage inside templates directory. Note: strictly place all webpages inside templates directory.

  ## jinja2 templating language

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
	headline = "hello, world!"
	return render_template("index.html", headline=headline, subheading="this is my sub heading")
```


```html
<!DOCTYPE html>
<html>
    <head>
        <title>My Website!</title>
    </head>
    <body>
        <h1>
            {{ headline }}
        </h1>
    	<h2>
            {{ subheading }}
        </h2>
    </body>
</html>
```

- jinja2 variable 
- we can send data from flask to html 
- we created a variable, headline = "hello, world!" and we returning return_template function with index.html and we have also add additional arguments as headline=headline and subheading="this is my sub heading".
- It's a convention to give argument name and value as same name, but it not necessary to be.
- In html, we added {{ }} inside <h1> tag. Think of this as a placeholder. It means, whatever value the headline variable holds in the python (flask) program will be substituted inside the {{ }} 

## what is the advantage of substituting value into html templates instead of just write directly into the html?

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
	headline = "hello, world!"
	return render_template("index.html", headline=headline, subheading="this is my sub heading")

@app.route("/bye")
def bye():
    headline = "byebye!"
    return render_template("index.html", headline=headline, subheading="this is my sub heading") 

```

Here we used the same index.html template, but html page will be different based on page ths user sees.

## isitnewyear project

- conditions

  

```python
import datetime

from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
    now = datetime.datetime.now()
    newyear = now.month == 1 and now.day == 1
    return render_template("index.html",newyear=newyear)
```

```html
 <!DOCTYPE HTML>
 <html>
     <head>
         <title>is it new year</title>
         <style>
             body {
                 text-align: center;
             }
         </style>
     </head>
     <body>
         {% if newyear %}
         	<h1>Yes! Happy New Year!</h1>
         {% else %}
         	<h1>NO</h1>
         {% endif %}
     </body>
</html>
```

- why should we use conditional statement (jinja2) inside html, rather we can directly write in python. 

  ```python
  import datetime
  
  from flask import Flask, render_template
  
  app = Flask(__name__)
  
  @app.route("/")
  def index():
      now = datetime.datetime.now()
      newyear = now.month == 1 and now.day == 1
      newyear = "yes! Happy New Year!" if newyear else "NO"	# conditional statement inside python rather than on html.
      return render_template("index.html",newyear=newyear)
  ```

  ```html
   <!DOCTYPE HTML>
   <html>
       <head>
           <title>is it new year</title>
           <style>
               body {
                   text-align: center;
               }
           </style>
       </head>
       <body>
           <h1>
               {{ newyear }}
           </h1>
       </body>
  </html>
  ```

  - this code also works the same but when we start working more complex websites, where you need display entire chunk of html based on conditions rather than a single string value (here newyear.)



## Loops:

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
	names = ["Alice", "Bob", "charlie"]
	return render_template("index.html", names=names)
```

```html
 <!DOCTYPE HTML>
 <html>
     <head>
         <title>My Website!</title>
     </head>
     <body>
         <h1>Names</h1>
          
         <ul>
             {% for name in names %}
             	<li>{{ name }}</li>
             {% endfor %}
         </ul>
     </body>
</html>
```

## urls

How to link different parts of your web application? which means one route, that links to other route, then it routes to the original route. (html-link links to different pages using href tag but not processed by server side code, but here, when we click a link, it is processed at server side code and then the corresponding page is displayed.)

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
	return render_template("index.html")

@app.route("/more")
def more():
	return render_template("more.html")

```

**index.html**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My Website!</title>
    </head>
    <body>
        <h1>
            First Page
        </h1>
        <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos eius repellat alias consequuntur deserunt, ratione dignissimos natus nulla sed itaque modi provident totam mollitia quia quae sapiente id voluptatem eveniet?
        </p>
        <a href="{{ url_for('more') }}">See more...</a>
    </body>
</html>

<!-- 'more' - name of the python function. -->
```

**more.html**

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My Website!</title>
    </head>
    <body>
        <h1>
            Second Page
        </h1>
        <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos eius repellat alias consequuntur deserunt, ratione dignissimos natus nulla sed itaque modi provident totam mollitia quia quae sapiente id voluptatem eveniet?
        </p>
        <a href="{{ url_for('index') }}">Go Back</a>
    </body>
</html>

```

we can see more similarity between index.html and more.html, so that we can take what are common to both the pages and put it inside a separate file as a template (or layout). from the layout or template, we can inherit the common things and use it on new pages.

It is called Template Inheritance.

## Template Inheritance

```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def index():
	return render_template("index.html")

@app.route("/more")
def more():
	return render_template("more.html")
```

layout.html

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My Website!</title>
    </head>
    <body>
        <h1>{% block heading %}{% endblock %}</h1>
         {% block body %}
         {% endblock %}
    </body>
</html>
```

index.html

```html
{% extends "layout.html" %}

{% block heading %}
	First Page
{% endblock %}

{% block body %}
	<p>
	Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos eius repellat alias consequuntur deserunt, ratione dignissimos natus nulla sed itaque modi provident totam mollitia quia quae sapiente id voluptatem eveniet?
	</p>

	<a href="{{ url_for('more') }}">See more...</a>
{% endblock %}
```

more.html

```html
{% extends "layout.html" %}

{% block heading %}
	Second Page
{% endblock %}

{% block body %}
	<p>
	Lorem ipsum dolor sit amet consectetur adipisicing elit. Eos eius repellat alias consequuntur deserunt, ratione dignissimos natus nulla sed itaque modi provident totam mollitia quia quae sapiente id voluptatem eveniet?
	</p>

	<a href="{{ url_for('index') }}">Go Back</a>
{% endblock %}
```

## Forms

```python
from flask import Flask, render_template, request

app = Flask(__name__)

@app.route("/")
def index():
	return render_template("index.html")

@app.route("/hello", methods=["POST"])
def hello():
	name = request.form.get("name")
	return render_template("hello.html", name=name)
```

layout.html

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My Website!</title>
    </head>
    <body>
        <h1>{% block heading %}{% endblock %}</h1>
         {% block body %}
         {% endblock %}
    </body>
</html>
```

hello.html

```html
{% extends "layout.html" %}

{% block heading %}
	Hello!
{% endblock %}

{% block body %}
	Hello, {{ name }}!
{% endblock %}
```

index.html

```html
{% extends "layout.html" %}

{% block heading %}
	First Page
{% endblock %}

{% block body %}
	<form action="{{ url_for('hello') }}" method="post">
		<input type="text" name="name" placeholder="Enter Your Name">
		<button>Submit</button>
	</form>
{% endblock %}
```

## sessions

sessions are used to store user information on the server.



Notetaking App without using session:

```python
from flask import Flask, render_template, request, session
from flask_session import Session

app = Flask(__name__)

app.config["SESSION_PERMANENT"] = False
app.config["SESSION_TYPE"] = "filesystem"
Session(app)

notes = []

@app.route("/", methods=["GET", "POST"])
def index():
    if request.method == "POST":
        note = request.form.get("note")
        notes.append(note)
    
    return render_template("index.html", notes=notes)
```

```html
{% extends "layout.html" %}

{% block heading %}
    Note Taking App
{% endblock %}

{% block body %}
	<ul>
        {% for note in notes %}
        	<li>{{ note }}</li>
        {% endfor %}
	</ul>

	<form action="{{ url_for('index') }}" method="POST">
        <input type="text" name="note" placeholder="Enter note here">
        <button>
            Add Note
        </button>
	</form>
{% endblock %}
```

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My Website!</title>
    </head>
    <body>
        <h1>{% block heading %}{% endblock %}</h1>
        {% block body %}
        {% endblock %}
    </body>
</html>
```

Notetaking app using session:

```python
from flask import Flask, render_template, request, session
from flask_session import Session

app = Flask(__name__)

app.config["SESSION_PERMANENT"] = False
app.config["SESSION_TYPE"] = "filesystem"
Session(app)

notes = []

@app.route("/", methods=["GET", "POST"])
def index():
    if session.get("notes") is None:
        session["notes"] = []
    if request.method == "POST":
        note = request.form.get("note")
        session["notes"].append(note)
    
    return render_template("index.html", notes=session["notes"])
```

```html
{% extends "layout.html" %}

{% block heading %}
    Note Taking App
{% endblock %}

{% block body %}
	<ul>
        {% for note in notes %}
        	<li>{{ note }}</li>
        {% endfor %}
	</ul>

	<form action="{{ url_for('index') }}" method="POST">
        <input type="text" name="note" placeholder="Enter note here">
        <button>
            Add Note
        </button>
	</form>
{% endblock %}
```

```html
<!DOCTYPE html>
<html>
    <head>
        <title>My Website!</title>
    </head>
    <body>
        <h1>{% block heading %}{% endblock %}</h1>
        {% block body %}
        {% endblock %}
    </body>
</html>
```



end of lecture 3