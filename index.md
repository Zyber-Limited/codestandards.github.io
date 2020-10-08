
# Zyber Coding Standards

The below documentation provides some best practices and standards to follow in development.




## JavaScript
Use [Can I Use](https://caniuse.com/) to check browser support for any required functionality.

### Code Reusability
Always structure your code in such a way that promotes code reuse. This will reduce time, effort and reduce coupling/dependency.

### Naming Conventions

`let` should be **camelCase**.

`const` if at the top of a file use upper case **snake case** -> `MY_CONST` . 

If not at the top of the file use **camelCase**.

`class` should be **PascalCasing ** ->  `MyClass`.

`functions` should be **camelCase**  -> `myFunction`.

Function names should always relfect what the function is intended to do.

File names should be **camelCase**  -> `myFile.js`.


### Comparisons
Use === instead of ==

> Fail : if (val == 2)

> Pass : if (val === 2)


### Scope & Variable declaration

Use `let` instead of `var` to avoid scoping issues in JavaScript.

> Fail : var myVar = 10;

> Pass : let myVar = 10;

Use `const` to define any variables that are not expected to be changed.

> Fail : let GST_PERCENT = 15;

> Pass : cost GST_PERCENT = 15;


### Use of semicolons (;)
 
Although this is optional in JavaScript as semicolons are not needed as statement terminators like other languages.  Using a `;`really helps to keep the code consistent and a great for statement separators and improved readability.

>**Fail**

> const VAT_PERCENT = 20;
> let amount = 10  
> return addVat(amount, vatPercent)

>**Pass**

> const VAT_PERCENT = 20;  
> let amount = 10;  
> return addVat(amount, vatPercent);

### Reduce nesting
An `if` within `if` can get messy and very hard to read, very quickly. Sometimes you may not be able to get around but always have a look at the structure of your JavaScript to see if you can change it around.
> **Fail**

    if (myNumber > 0) {  
	    if (myNumber > 100) {  
		    if (!hasDiscountAlready) {  
				 return addDiscountPercent(0);  
		    } else {  
			    return addDiscountPercent(10);  
		    }  
	    } else if (myNumber > 50) {  
		    if (!hasDiscountAlready) {  
			    return addDiscountPercent(5);  
		    }  
	    } else {  
		    if (!hasDiscountAlready) {  
			    return addDiscountPercent(0);  
		    } else {  
			    return addDiscountPercent(1);  
		    }  
	    }  
    } else {  
	    error();  
    }

> **Pass**

    if (myNumber <= 0) {  
       return error;  
    }
    if (!hasDiscountAlready) {  
        return addDiscountPercent(0);  
    }
    if (myNumber > 100) {   
        return addDiscountPercent(10);  
    }
    if (myNumber > 50) {   
        return addDiscountPercent(5);  
    }
    return addDiscountPercent(1);

> **Fail**

    if (valid) {   
       return buy();  
    } else {   
       return error();  
    }

> Pass

    return valid ? buy() : error();

### Use of default parameters
In JavaScript, if you don’t pass in a value into a parameter when calling a function it will be `undefined`

> **Fail**

    myFunction(a, b) {  
	    return a + b;  
    }

> **Pass**

    myFunction(a = 0, b = 0) {  
    	return a + b;  
    }

### Switch Statements
Consider using switch statements if you come across a situation where you need to compare lot of values. It also makes reading easier.
Switch statements should use `break` and have `default`
> **Fail**

    switch (myNumber)  
    {  
	    case 10:  
		    addDiscountPercent(0);  
	    case 20:  
		    addDiscountPercent(2);  
	    case 30:  
		    addDiscountPercent(3);  
    }
**Pass**

    switch (myNumber)  
    {  
	    case 10:  
		    addDiscountPercent(0);  
		    break;  
	    case 20:  
		    addDiscountPercent(2);  
		    break;  
	    case 30:  
		    addDiscountPercent(3);  
		    break;  
	    default:  
		    addDiscountPercent(0);  
		    break;  
    }
    
### A function's task
Please ensure that functions only ever fulfil one task.

If another developer joins you on your project, tries to build on it, or attempts to debug it or change it, they won't have to read through the _entire_ code document to figure out what code performs which functions.

### Commenting
Use comments to
Don't comment on the obvious.
> **Fail**

    let  i  =  1;  // Setting i to 1;

# PHP

All Php development  should be developed according to the [PSR 12](https://www.php-fig.org/psr/psr-12/) standard. 
