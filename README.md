RacoonScript
============

RacoonScript Example:
---------------------
```js
class SubClass extends SuperClass
    
    //single line comment
    
    /*
     * multiline comment
     */
     
    //declare local variable
    localVar = 5
    
    @OnCreate
    	//function call
    	[self OnUpdate with Delta is 1, Extra is null]
    	
    	//function call as function call parameters
    	[self OnUpdate with Delta is [self GetDeltaTime], Extra is [self OnUpdate with Delta is [self GetDeltaTime], Extra is null]]
    	
    	//create a nested function
    	@nestedMethod
    	
    	end
    	//call it
    	[self nestedMethod]
    	
    	@localVar = 10
    	b = 10 //a function local variable
    	@localVar = 5 + b
    end

    //function with parameters
    @OnUpdate with Delta as delta, Extra as extra
    
    
    end

    @GetDeltaTime
        return 1
    end
    
    static @StaticFunction 
    
    end
```
