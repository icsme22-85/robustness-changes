# Groups
## 1. Smells exist and are worsened
"I am pretty sure that all smells existed at the point of this change. However, the robustness improvement contributes to the worsening of two smells (LongMethod and BrainMethod)."

"The change improves the robustness, however the smells already existed and were not affected by the change."

"The exception changes indeed contribute to increasing the Intensive Coupling in the method, since more external method needed to be called"

"The change in the catch block is not related to the smells. However, the chance can be introduing the Dispersed Coupling smell."

"Added a try/catch block that tests whether a type can be converted. Seems to be that anti-pattern where exceptions are being used as control flow. Related to the long method smell, as it is making the method longer."	

"The change in the catch block is only related to styling of the logging. However, the methor itself calls a new classe called ClassHelper, which makes the method have a Dispersed Coupling"

"The exception changes indeed contribute to add a feature envy respect to CALLS_TO_org.apache.dubbo.rpc.cluster.support.AbstractClusterInvoker<T>. I dont't consider the long method as a smells. However, there is a disperd coupling in this method."

"The change moves the code from the catch to finally, which can be problematic, not handling the error. In addition, the calls in the catch blocks makes the code have the Feature Envy"


## 2. Refactoring
"The exception changes indeed contribute for making the method long and being coupled to different classes. Given the aparent complexity of the feature, the try with resources part could be improved or even extracted to a sub method."

"Refactoring brought already existing code from other classes to this one which was almost empty. Introduced the smell. Exception handling is being used mostly for logging."


## 3. Indirect Relation
The feature envy and message chain smells seem to be related to the operation being performed, which is parsing. It is common that this kind of operation may result in exceptions. Therefore, there is an indirect relation between the smells and the exceptional change.


## 4. Try worsens the smell
This change to a try clause did in fact worsen all of the smells present in the method (FeatureEnvy, LongMethod,  DispersedCoupling). In this try clause, there are several nested conditions. The change made the line not execute when a specific condition was met, but since the conditions were nested, this required the developer to duplicate this same line multiple times, adding more calls to an external method and making the class longer.

# Smells Collected

#### Brain Method
  Long and complex method that centralizes the intelligence of a class
#### Dispersed Coupling
  A method that accesses many elements, and the accessed code elements are dispersed among many classes
#### Feature Envy
  A method that is more interested in a class other than the one it actually is in
#### Intensive Coupling
  A method that has tight coupling with other methods, and these coupled methods are defined in the context of few classes
#### Long Method
  A method that is unduly long in terms of lines of code
#### Message Chain
  A long chain of method invocations is performed to implement a class functionality
#### Long Parameter List
  A method having a long list of parameters, some of which avoidable

