# CppConcepts
C++ Language and Concepts
	heap & stack
		heap = global/static & slow
		stack = local & high speed, RAM, LiFo, variable in function
	object lifetime, scope exit, order of initialization and stack unwinding
	pass by reference vs. pass by value
	the semantics of move (like std::move)
		l value = has something on the storage (an address)
		r value = does have nothing on the storage
		e.g. var = 4
			var is the l value
			4 is the r value
		std::move() -> cast to r value -> does not! move anything
	const correctness
		const X* p   p is a pointer to an X which is const
		X* const p   p is constant and points to an Object X
	Resource Acquisition Is Initialization (RAII)
		wrap a class around a resource -> avoid resource leaks
	the rule of three/five/zero https://en.cppreference.com/w/cpp/language/rule_of_three
	the Static Initialization Order Fiasco https://en.cppreference.com/w/cpp/language/siof
	inheritance diamond problem
		class Person{}
		class Student: virtual public Person{} //virtual!
		class Dozent: virtual public Person{} //virtual!
		class TA: public Dozent, public Student
		{
			TA(): Student(), Dozent(), Person() {} //Person()!
		}
	inheritance how to access the base class function inside of an override function
	composition over inheritance
	abstract classes (aka interfaces)
	namespaces, anonymous namespaces
	simple templates
	argument-dependent lookup (ADL)
		King Lookup
	use libraries wherever possible; prefer the standard library to other libraries
	STL
		containers: std::vector, std::list, std::map, ...
			size is known: std::array > built-in array
			add & remove at front & back: std::deque
			add & remove in the middle: std::list
			random access to objects: don't take std::list
			system has cache: std::vector > std::list
			string: std::string
			key/value-pair: std::unordered_map std::map
			onekey -> multiple entries: std::unordered_multimap std::multimap
		algorithms: std::find_if, std::any_of, ...
		std::future, std::promise
			async vs. deferred
		smart pointers: std::unique_ptr, std::shared_ptr, std::weak_ptr
		mutex: std::mutex std::shared_mutex std::shared_lock std::lock_guard std::unique_lock...
		std::call_once
		...
	the iterators library
	function objects, and lambdas vs. std::bind
		-> use lambdas
	google test, google mock
	JSON for Modern C++
git
	rebase vs. git merge
		(see also: https://learngitbranching.js.org/) (bearbeitet) 
