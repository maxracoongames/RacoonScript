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
    classVar = 5
    
    @OnCreate with Name as name
    	//function call
    	[self.OnUpdate with Delta is 1, Extra is null]
    	
    	//function call as function call parameters
    	[self.OnUpdate with Delta is [self.GetDeltaTime], Extra is [self.OnUpdate with Delta is [self.GetDeltaTime], Extra is null]]
    	
    	//create a nested function
    	@nestedMethod
    	
    	end
    	//call it
    	[nestedMethod]
    	
    	var localVar = 10
    	var b = 10 
    	self.classVar = 5 + b
    	
    end

    //function with parameters
    @OnUpdate with Delta as delta, Extra as extra
        [super.OnUpdate with Delta is delta, Extra is extra]
    end

    @GetDeltaTime
        return 1
    end
    
    static @StaticFunction 
    
    end
```

Javascript Result:
---------------------
```js
RacoonScript.Extends(SubClass, SuperClass);
function SubClass(name){
    this.OnCreate(name);
    
    //line:XX classVar = 5 
    this.classVar = 5;
}
//line:XX @OnCreate with Name as name
SubClass.prototype.OnCreate = function(name){
    var self = this;
    //line:XX [self.OnUpdate with Delta is 1, Extra is null]
	self.OnUpdate (1, null);
	//line:XX [self.OnUpdate with Delta is [self.GetDeltaTime], Extra is [self.OnUpdate with Delta is [self.GetDeltaTime], Extra is null]]
	self.OnUpdate (self.GetDeltaTime(),self.OnUpdate (self.GetDeltaTime(), null));
	//line:XX @nestedMethod
	nestedMethod = function(){
	
	};
	//line:XX [nestedMethod]
	nestedMethod();
	//line:XX var localVar = 10
	var localVar = 10;
	//line:XX var b = 10
	var b = 10;
	//line:XX self.classVar = 5 + b;
	self.classVar = 5 + b;
};


SubClass.prototype.OnUpdate = function(delta, extra){
    var self = this;
    SuperClass.prototype.OnUpdate.call(self, delta, extra);
};

SubClass.prototype.GetDeltaTime = function(){
    var self = this;
    return 1;
};

SubClass.StaticFunction = function(){

};
```
