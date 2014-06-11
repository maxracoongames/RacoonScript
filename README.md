RacoonScript
============

RacoonScript Example:
---------------------
```js
package testPackage;

class TestClass1 extends RDOMComponent {
	function new(){
		super("div");
	}
	function Test(){
		property1();
	}
	function property1(value){
		get{
			return new NestedClass();
		}		
		set{
		
		}
	}
	class NestedClass {
		function new(){
		
		}
		function Test(){
		
		}
	}
}
```

Javascript Result:
---------------------
```js
```
