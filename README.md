**Task-1**

# HTTP1 Vs HTTP2

**HTTP** stands for _hypertext transfer protocol_, and it is the basis for almost all web applications. More specifically, HTTP is the method computers and servers use to request and send information.

The first usable version of HTTP was created in 1997. Because it went through several stages of development, this first version of HTTP was called HTTP/1.1. This version is still in use on the web. In 2015, a new version of HTTP called HTTP/2 was created.

HTTP/2 solves several problems that the creators of HTTP/1.1 did not anticipate. In particular, HTTP/2 is much faster and more efficient than HTTP/1.1.

**Multiplexing**:HTTP/1.1 loads resources one after the other, so if one resource cannot be loaded, it blocks all the other resources behind it. In contrast, HTTP/2 is able to use a single TCP connection to send multiple streams of data at once so that no one resource blocks any other resource.

**Server push**: In HTTP/1.1, a server only serves content to a client device if the client asks for it. HTTP/2 solves this problem by allowing a server to "push" content to a client before the client asks for it. The server also sends a message letting the client know what pushed content to expect.

**Header compression**: Small files load more quickly than large ones. HTTP/2 uses a more advanced compression method called HPACK that eliminates redundant information in HTTP header packets. This eliminates a few bytes from every HTTP packet. Given the volume of HTTP packets involved in loading even a single webpage, those bytes add up quickly, resulting in faster loading.

**Prioritization**: Prioritization refers to the order in which pieces of content are loaded. Prioritization affects a webpage's load time. For example, certain resources, like large files, may block the rest of the page from loading if they have to load first. More of the page can load at once if these render-blocking resources load last. In HTTP/2, developers have hands-on, detailed control over prioritization. This allows them to maximize perceived and actual page load speed to a degree that was not possible in HTTP/1.1.

### HTTP/1.1:

+ HTTP (HOL)Head of Line Blocking problem.

+ Non-implementation of requests pipelining for request multiplexing.

+ Opening of multiple TCP connections for requesting multiple resources.

+ Textual nature of data transfer.

+ Long HTTP headers.

+ Numerous Workarounds to overcome above HTTP problems.

+ Slow web page loading speed.

### HTTP/2

+ It’s a binary protocol instead of textual.

+ HTTP/2 is fully multiplexed

+ It used header compression HPACK to reduce the overhead size

+ It allows servers to “push” responses proactively into client caches instead of waiting for a new request for each resource.

+ Low overhead in parsing data.

+ It’s widely supported by browsers. As a basic internet technology, protocol HTTP/2 must be supported by the current version of your browser to work well.

# Objects and its internal representation in javascript

In javascript, Objects, data types such as numbers, strings, and booleans are distinct from primitive datatypes. Unlike Primitive data types which can only contain one value, objects can contain multiple values in the form of key-value pairs. These keys can be either variables or functions and are referred to as properties and methods, respectively, within the object's context.

Each and every object possesses a property that corresponds with a specific value. The values can be retrieved by accessing the respective properties.
```

var myCar = new Object();

myCar.make = 'Suzuki';

myCar.model = 'Altros';

myCar.year = 1978;

myCar.wheels = 2;
```

Once the myCar object is created, its contents can be retrieved using keys.

i.e.

```
myCar.year

Output: 1978
```

It is also possible to access these values using the bracket notation.
```

myCar[year]

Output: 1978
```

The syntax for Adding a property to an object is :

```
ObjectName.ObjectProperty = propertyValue;
```

The format for removing an object's property is as follows:
```

delete ObjectName.ObjectProperty;
```

One can use the following syntax to retrieve a property from an object:
```

objectName.property        
           //or
objectName["property”]     
           //or
objectName[expression]
```


**Object methods**

An object method is a function definition that is stored within an object property.

i.e.,
```

function(){return ignition.on}
```

Definition of Java Script Object methods is that they are actions that can be carried out on objects.

**Create JavaScript Object with Object Literal**

To generate a JavaScript Object , a quick and effortless method is through Object Literal . All that is required is to enclose the attributes and corresponding values within curly brackets, as illustrated below.

```
let bike = {name: 'SuperSport', maker:'Ducati', engine:'937cc'};
```

**Using the JavaScript Keyword new**

This instance generates a fresh javascript object that consists of four attributes.
```

var person = new Object();
person.firstName = “John”;
person.lastName = “Doe”;
person.age = 50;
person.eyeColor = “blue”;
```

**Create JavaScript Object with Constructor**

A constructor, which is essentially a function, can be used with the new keyword to create instances of the same type, as demonstrated below.
```

function Vehicle(name, maker) {
   this.name = name;
   this.maker = maker;
}
let car1 = new Vehicle(’Fiesta’, 'Ford’);
let car2 = new Vehicle(’Santa Fe’, 'Hyundai’)
console.log(car1.name);    //Output: Fiesta
console.log(car2.name);    //Output: Santa Fe
```

Most objects contain all their properties in a single block of memory. All blocks of memory have a pointer to a map, which describes their structure. Named properties that don’t fit in an object are usually stored in an overflow array. Numbered properties are stored separately, usually in a contiguous array.

The JavaScript standard allows developers to define objects in a very flexible way, and it is hard to come up with an efficient representation that works for everything. An object is essentially a collection of properties: basically key-value pairs. You can access properties using two different kinds of expressions:

+ obj.prop

+ obj[“prop”]