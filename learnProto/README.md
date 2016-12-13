#Protocobuf Java Intellij setup

Add more details to [googles java protobuf tutorial](https://developers.google.com/protocol-buffers/docs/javatutorial)

##1. Define protocol formate
Check **addressbook.proto**

##2. Compiling Your Protocol Buffers
```
protoc -I=$SRC_DIR --java_out=$DST_DIR $SRC_DIR/addressbook.proto
```
This generates **com/example/tutorial/AddressBookProtos.java** in your specified destination directory.

##3. Create empty Marven project

```
mvn archetype:generate -DgroupId=com.example.tutorial \
-DartifactId=learnProto -DarchetypeArtifactId=maven-archetype-quickstart -Dinteractive\
Mode=false
```
This will create an empty project, import with intellij, Add protobuf dependency(code below) into **pom.xml**
```xml
<dependency>
      <groupId>com.google.protobuf</groupId>
      <artifactId>protobuf-java</artifactId>
      <version>3.1.0</version>
      <scope>compile</scope>
</dependency>
 ```


##4. Add code generated in step 2 to project

Move the folder _com_ created in step 2 to _src/main/java_


##5. Add Writer and Reader using the API generated in step 2

Check **AddPerson.java** and **ListPeople.java**

##6. TODO: Add **addressbook.proto** to project

create a folder named proto under _src/main/java_, mv **addressbook.proto** into it.

install [intellij protobuf plugin](https://plugins.jetbrains.com/plugin/8277)

//TODO: Check http://vlkan.com/blog/post/2015/11/27/maven-protobuf/