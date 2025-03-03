[//]: # (title: RubyMine Plugin Development)

<!-- Copyright 2000-2022 JetBrains s.r.o. and other contributors. Use of this source code is governed by the Apache 2.0 license that can be found in the LICENSE file. -->

## Introduction
[RubyMine](https://www.jetbrains.com/ruby/) is an IntelliJ Platform-based product.
Plugin projects for RubyMine can be developed using IntelliJ IDEA with the `gradle-intellij-plugin`.

 > Qualifying Open Source projects can [apply for free licenses](https://www.jetbrains.com/community/opensource/) of JetBrains products.
 >
 {type="tip"}

## Configuring Plugin Projects Targeting RubyMine
The configuration of RubyMine plugin projects follows the methods described in [Configuring Plugin Projects using the IntelliJ IDEA Product Attribute](dev_alternate_products.md#configuring-plugin-projects-using-the-intellij-idea-product-attribute), and [Configuring the plugin.xml File](dev_alternate_products.md#configuring-pluginxml).

The table below summarizes the `gradle-intellij-plugin` attributes to set in the <path>build.gradle</path> file for a RubyMine plugin project.
Click on an entry in the table's *Attribute* column to go to the documentation about that attribute.
To see how these attributes appear in a similar <path>build.gradle</path> file for PhpStorm, see [Configuring build.gradle using the IntelliJ IDEA Product Attribute](dev_alternate_products.md#configuring-buildgradle-using-the-intellij-idea-product-attribute).

| `gradle-intellij-plugin` Attribute | Attribute Value                                                                                                                                                                                                     |
|------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [`intellij.type`][properties]      | `IU` for IntelliJ IDEA Ultimate.                                                                                                                                                                                    |
| [`intellij.version`][properties]   | Set to the same `IU` BRANCH.BUILD as the RubyMine target version, e.g. `192.7142.36`.                                                                                                                               |
| [`intellij.plugins`][properties]   | `org.jetbrains.plugins.ruby:2019.2.20191029` for the Ruby plugin.<br/>See below for Ruby plugin version information.                                                                                                |
| [`runIde.ideDir`][dsl]             | Path to locally installed target version of RubyMine. For example, on macOS:<br/><path>/Users/$USERNAME$/Library/Application Support/JetBrains/Toolbox/apps/RubyMine/ch-0/192.7142.37/RubyMine.app/Contents</path>. |

[properties]: https://github.com/JetBrains/gradle-intellij-plugin/blob/master/README.md#intellij-platform-properties
[dsl]: https://github.com/JetBrains/gradle-intellij-plugin/blob/master/README.md#running-dsl

The required `org.jetbrains.plugins.ruby` plugin isn't compatible with IntelliJ IDEA Community edition but is compatible with IntelliJ IDEA Ultimate (`IU`) edition.
Product compatibility is determined from the Ruby plugin [version page](https://plugins.jetbrains.com/plugin/1293-ruby/versions).
The Ruby plugin isn't bundled with `IU`, so the Ruby plugin version must be explicitly declared to support the target RubyMine (and `IU`) BRANCH.BUILD version.
The correct Ruby plugin version is also determined from the Ruby plugin version page.

The dependency on the Ruby plugin APIs must be declared in the <path>plugin.xml</path> file.
As described in [Modules Specific to Functionality](plugin_compatibility.md#modules-specific-to-functionality) table, the `<depends>` elements must contain `com.intellij.modules.ruby`.
The dependency declaration is illustrated in the <path>plugin.xml</path> snippet below:

```xml
  <!-- Requires the Ruby plugin -->
  <depends>com.intellij.modules.ruby</depends>
```

## Available RubyMine APIs

 > See [RubyMine Extension Point List](rubymine_extension_point_list.md) for complete list.
 >
 {type="note"}

Use the [Exploring APIs as a Consumer](plugin_compatibility.md#exploring-apis-as-a-consumer) process to identify the library <path>ruby.jar</path>.
Test your plugin with any version of RubyMine you intend to support.

## Open Source Plugins for RubyMine
When learning new APIs, it is helpful to have some representative projects for reference:
* [Ruby-Doc-Adder](https://github.com/aristotll/RubyDocAdder)
* [Ruby Dynamic Code Insight](https://github.com/JetBrains/ruby-type-inference)
* [Railways](https://github.com/basgren/railways)
