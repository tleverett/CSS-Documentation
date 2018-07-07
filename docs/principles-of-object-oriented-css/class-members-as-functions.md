<sub>/ [CSS Documentation](..) / [Principles of Object-Oriented CSS](.) / Class Members as Functions</sub>

# Class Members as Functions

> It's turtles all the way down

The jump for methods and procedures to be considered functions should be reasonably self-explanatory. They take input, and produce output.

For fields, properties and the like it can be a little less clear, so for clarity lets look at some simple examples using C#.

<!--
Maybe update examples to use JS instead?
-->

To start we declare a simple class (OOP) with a field:

```c#
class ExampleClass
{
  public ExampleType ExampleField;
}
```

This is not significantly different from a simple class (OOP) with a property:

```c#
class ExampleClass
{
  public ExampleType ExampleProperty { get; set; }
}
```

The `ExampleProperty` can be rewritten using explicit getters and setters:

```c#
class ExampleClass
{
  private ExampleType _exampleField
  public ExampleType ExampleProperty
  {
    get
    {
      return _exampleField;
    }
    set
    {
      _exampleField = value;
    }
  }
}
```

and these explicit getters and setters can be rewritten to remove the syntactic sugar of accessors and mutators:

```c#
class ExampleClass
{
  private ExampleType _exampleField;
  public ExampleType getExampleProperty()
  {
    return _exampleField;
  }

  public void setExampleProperty(ExampleType value)
  {
    _exampleField = value;
  }
}
```

Note that the private fields are purely implementation details. These functions could as easily delegate to an external data-store:

```c#
class ExampleClass
{
  public ExampleType getExampleProperty()
  {
    return externalDataStore.getExampleProperty();
  }

  public void setExampleProperty(ExampleType value)
  {
    externalDataStore.setExampleProperty(value)
  }
}
```

and all of these classes (OOP) are conceptually identical.