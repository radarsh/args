args
====

A reusable solution for Command Line Arguments Parsing in Java

## Usage

```java
// Initiate the arguments engine.
ArgsEngine engine = new ArgsEngine();

// Configure the switches/options. Use true for valued options.
engine.add("-q", "--quiet");
engine.add("-o", "--redirect-output", true);
engine.add("-h", "--help");

// Perform the parsing. The 'args' is the String[] received by main method.
engine.parse(args);

// Start fetching states of switches.
boolean quiet = engine.getBoolean("-q");

if(engine.getBoolean("-o")) {
    // For valued options, use getString.
    String redir = engine.getString("-o");
}

// Use getNonOptions to filter out all options.
String[] nonOptions = engine.getNonOptions();
```