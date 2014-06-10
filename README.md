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
 
//function with no parameter
@localVariable is 5

@OnCreate is
begin
	//function call
	[self OnUpdate with Delta is 1, Extra is null]
	
	//function call as function call parameters
	[self OnUpdate with Delta is [self GetDeltaTime], Extra is [self OnUpdate with Delta is [self GetDeltaTime], Extra is null]]
	
	//create a nested function
	@nestedMethod is
	
	@end
	//call it
	[self nestedMethod]
	
	local a = 10
	b = 10
	a = 5 + b
end

//function with parameters
@OnUpdate with Delta as delta, Extra as extra is
begin

end

@GetDeltaTime is
begin
    return 1
end

static @StaticFunction is
begin

end
```

Javascript result
-----------------
```js
RacoonScript.Extends(SubClass, SuperClass)
function SubClass (){
    /*generated code*/
    this.self = this;
    this.thisClass = SubClass;
    this.superClass = SuperClass;
    /*end*/
    //single line comment
    
    /*
     * multiline comment
     */
     
    //function with no parameter
    this.OnCreate = 

    //function with parameters
    this.OnUpdate (delta, extra){
    	
    }

    this.GetDeltaTime = function(){
        return 1;
    }
    static @StaticFunction is

    @end
}
SubClass.prototype.OnCreate = function(){
    
 	//function call
 	self.OnUpdate(1, null);
 	//function call as function call parameters
 	self.OnUpdate(self.GetDeltaTime(), self.OnUpdate(self.GetDeltaTime(), null));
	
	//create a nested function
	var NestedMethod = function(){
	
	};
	//call it
	NestedMethod()
	
	var a = 10;
	this.b = 10;
	a = 5 + this.b;
};
```