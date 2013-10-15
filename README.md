# JS-SPY

## Purpose

Very first draft of method that helps spy what properties of an object are being used on a given website. Can be useful when trying to make Modernizr as light as possible.

## Sample Code

1) First, get an object to be spied. Can be Modernizr for example. Let's define a simple one:
```
var user = { name: 'Maciej', surname: 'Smolinski', fullName: 'Maciej Smolinski' };
```

2) Spy properties of the previously defined object. Add 'user' label to debug info to be output in the console:
```
spyProperties('user', user);
```

3) Access object's properties as usual:
```
console.log('Full Name is: ' + user.name + ' ' + user.surname);
```

4) Watch debug info in the console:
```
[Property Usage] user.name
[Property Usage] user.surname
```

That's about it!

## Bonus: Simply check how jQuery works

1) Spy jQuery methods:
```
spyProperties('$', $);
spyProperties('$.fn', $.fn);
```

2) Call method you want to get an understanding of:
```
$('body').attr('class');
```

3) Watch the console output (debug):
```
// [Property Usage (0.0130)] $.fn
// [Property Usage (0.0130)] $.fn.init 
// [Property Usage (0.0130)] $.fn.find
// [Property Usage (0.0020)] $.find
// [Property Usage (0.0120)] $.fn.pushStack
// [Property Usage (0.0150)] $.fn.constructor
// [Property Usage (0.0130)] $.fn
// [Property Usage (0.0130)] $.fn.init
// [Property Usage (0.0020)] $.merge
// [Property Usage (0.0080)] $.fn.length
// [Property Usage (0.0090)] $.fn.selector
// [Property Usage (0.0120)] $.fn.attr
// [Property Usage (0.0010)] $.attr
// [Property Usage (0.0020)] $.access
// [Property Usage (0.0080)] $.fn.length
// [Property Usage (0.0020)] $.type
```