RacoonScript
============
```js
class SubClass extends SuperClass

//single line comment

/*
 * multiline comment
 */
 
//function with no parameter
@OnCreate is

	//function call
	[OnUpdate with Delta is 1, Extra is null]
	
	//function call as function call parameters
	[OnUpdate with Delta is [GetDeltaTime], Extra is [OnUpdate with Delta is [GetDeltaTime], Extra is null]]
	
	//create a nested function
	@nestedMethod is
	
	@end
	//call it
	[nestedMethod]
	
	
@end

//function with parameters
@OnUpdate with Delta as delta, Extra as extra is
	
@end

@GetDeltaTime is
    return 1
@end
```