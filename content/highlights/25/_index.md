---
title: "JavaFX 25 Highlights"
section: "highlights"
styleclass: "content"
---
# JavaFX 25 Highlights

JavaFX version 25 has been released. We've tailored down some of the most exciting parts of the release in this document.

## Important Changes

### JavaFX 25 Requires JDK 23 or Later

JavaFX 25 is compiled with `--release 23` and thus requires JDK 23 or later in order to run. 
If you attempt to run with an older JDK, the Java launcher will exit with an error message indicating that the `javafx.base` module cannot be read.

See [JDK-8359387](https://bugs.openjdk.org/browse/JDK-8359387) for more information.

### JavaFX Requires GTK 3.20 or Later on Linux

On Linux platforms, JavaFX requires GTK3 version 3.20 or later. 
An exception will be thrown when initializing the JavaFX runtime if the GTK 3 library cannot be loaded or is older than 3.20.

See [JDK-8359396](https://bugs.openjdk.org/browse/JDK-8359396) for more information.

### JavaFX Applications No Longer Need `--sun-misc-unsafe-memory-access=allow`

It is no longer necessary to pass `--sun-misc-unsafe-memory-access=allow` to `java` on the command line when running JavaFX applications. 
The bug that formerly caused this option to be needed has been fixed.

See [JDK-8334137](https://bugs.openjdk.org/browse/JDK-8334137) for more information.

## Removed Features and Options

### A Deprecated `TransitionEvent` Constructor Has Been Removed

The `TransitionEvent(EventType, StyleableProperty, Duration)` constructor was deprecated for removal in JavaFX 24 and has now been removed. 
Application developers should use `TransitionEvent(EventType, StyleableProperty, String, Duration)` instead.

See [JDK-8353617](https://bugs.openjdk.org/browse/JDK-8353617) for more information.

Exciting features:
- New APIs:
  - Public API for Text Layout Info
  - JavaFX controls can now be placed in the title bar

- New Features:
  - RichTextArea control now supports CSS styling of highlights
  - TextArea now has support for multi-line prompt text

The community came together to fix 74 bugs in the last 6 months. Following are major bug-fixes that went into JavaFX 25:

- Fix for seek hangs with fMP4 H.265/HEVC or H.265/HEVC over HTTP/FILE
- Fix for ToolBar showing overflow menu with fractional scale
- Fix for ConcurrentModificationException creating MenuBar on background thread

Finally, these are some dependency upgrades in JavaFX 25:
- Update WebKit to 620.1
- Update libxml2 to 2.13.8
- Update libxslt to 1.1.43
- Update SQLite to 3.49.1

A more comprehensive list of all the changes in JavaFX 25 can be found on [Github](https://github.com/openjdk/jfx/blob/jfx25/doc-files/release-notes-25.md).

Kudos go to the fine people at [Gluon](https://gluonhq.com) who took care of the bulk of the work on JavaFX 25. Do check their [JavaFX Long Term Support](https://gluonhq.com/services/javafx-support/) services.
