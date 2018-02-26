EA Agent Loader
============

#### Project Deprecated
With the introduction of JDK9, dynamically self attaching Java Agents is considered bad practice. As such we are deprecating this project and will no longer continue to maintain it.
The project remains here for reference and for JDK8 users.

Brief
============
EA Agent Loader is a collection of utilities for [java agent](https://docs.oracle.com/javase/8/docs/api/java/lang/instrument/package-summary.html) developers.
It allows programmers to write and test their java agents using dynamic agent loading (without using the -javaagent jvm parameter).

Developer & License
======
This project was developed by [Electronic Arts](http://www.ea.com) and is licensed under the [BSD 3-Clause License](LICENSE).

Example
=======
```java
public class HelloAgentWorld
{
    public static class HelloAgent
    {
        public static void agentmain(String agentArgs, Instrumentation inst)
        {
            System.out.println(agentArgs);
            System.out.println("Hi from the agent!");
            System.out.println("I've got instrumentation!: " + inst);
        }
    }

    public static void main(String[] args)
    {
        AgentLoader.loadAgentClass(HelloAgent.class.getName(), "Hello!");
    }
}
```
