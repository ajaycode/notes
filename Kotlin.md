# Notes on Kotlin

#### const vs val
The modifier const must be used for compile-time consts.  Variables that cannot be changed are assigned to a variable with the keyword val.
```
companion object {
  const val PROG_NAME = "KILLER_APP"
  }
  ```

#### companion object as the equivalent of static
companion object is the equivalent of singleton. The code within the companion object is not instantiated for each instance of the object.  Loggers are examples that are required in each class, but do not need to be instantiated whenever a new instance is created.
```
 class MyController {
    companion object {
      @Suppress("JAVA_CLASS_ON_COMPANION")
      @JvmStatic
      var logger : Log = LogFactory.getLog (javaClass.enclosingClass)
      }
     //... other members and properties
    }
```

#### object as singleton
```
object MyConstants {
 const val PROG_NAME = "KILLER_APP"
 const val MIN_YEAR  = 2023
 }
 
 //
 println (MyConstants.PROG_NAME)
```
