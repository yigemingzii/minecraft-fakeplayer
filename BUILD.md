<!--
  Modified by yigemingzii, July 2026
  - Added Minecraft 26.x build instructions (Paper server jar replaces BuildTools)
-->
# Build introduction

Here is a simple introduction lead you to build this project

## Build NMS Dependencies

### Minecraft 1.20.x - 1.21.x (Spigot BuildTools)

Mojang does not allow anyone to publish the remapped NMS jar to any public repository,
so you need to build it yourself

1. Download [BuildTools](https://www.spigotmc.org/wiki/buildtools/)
2. execute `java -jar BuildTools.jar --rev 1.21 --remapped` to install remapped NMS 1.21 to your local repository. _You might need to install other version depending on projects' requirements._

### Minecraft 26.x (Paper Server Jar)

Starting from Minecraft 26.1, Mojang ships the server unobfuscated, so BuildTools is no longer needed.
Paper also no longer publishes spigot remapped-mojang artifacts for 26.x.
Instead, the `fakeplayer-v26_1_2` module compiles against the Paper server jar directly.

1. Download the Paper server jar:
   - Visit [papermc.io/downloads/paper](https://papermc.io/downloads/paper) and download the 26.1.2 build, OR
   - Run the paperclip jar: `java -jar lib/paper-26.1.2-server.jar --help` (this will auto-extract to `versions/26.1.2/paper-26.1.2.jar`)

2. The extracted jar at `versions/26.1.2/paper-26.1.2.jar` is referenced via system scope in the module's `pom.xml`

3. Build the module: `mvn compile -pl fakeplayer-v26_1_2 -am`

