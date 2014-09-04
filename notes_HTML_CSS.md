####Heriarchy

BOM(Browser Object Model) --> DOM(Document Object Model) --> html

####CSS
__Four combinators:__

	Descendent combinator marked with a space ( )
	Direct descendent combinator Marked with a grater than (>)
	Zibling combinators Marked with a plus sign (+)
	Sudo class combinator marked with colons (:)

__Specificity Level (http://specificity.keegan.st)__
	
	ID, CLASS, ELEMENT

__examples:__
	
	body{
		/*This has a specificity of 001*/
	}

	body h1 p{
		/*This has a specificity of 003*/
	}

	#tom h2 p{
		/*This has a specificity of 102*/
	}

	li:not(:first-of-type){
		/*This has a specificity of 011*/
	}