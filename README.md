# QExt
## Purpose
QExt is an add-on library for Qt developers with limited dependencies. The aims of QExt in a nutshell are:
 - Ease C++11/14 use with Qt
 - Expose useful Qt functionality that is currently private
 - Limit "rolling-your-own"
 - Extend Qt in a familiar Qt-style

## Goals
 1. Modularity
 2. Minimal dependencies
 3. Seamless integration with Qt
 4. Sensible use of C++11/14
 5. Reasonable speed and memory effeciency
 6. Excellent documentation

## Features
QExt exposes and maintains functionality that is "private" in Qt. The canonical example of a private class later made public is QVarLengthArray. QExt re-implements and supports similar types of useful classes that are hidden in Qt or emulates their functionality.

QExt also makes Qt-style development easier, such as the use of the d-ptr (also known as the compiler firewall), including Private class inheritance and back links (see `QePublicBase` and `QePrivateBase` in QeCore).

C++14 is now supported by VS, gcc, and Clang, so it is used throughout the library to speed, ease, and simplify development. One of the benefits of this are macros that replace `Q_D` and `Q_Q` without needing a class name declaration (`Q_DPTR` and `Q_QPTR`). This is legal code in QExt:

    void MyPublicClass::setFoo(const Foo &f)
    {
       Q_DPTR;
       d->foo = f;
    }

Optional components of QExt include a rich library of widgets (QeWidgets), a ribbon toolkit (QeRibbon), and Windows/COM integration (QeWindows).

## Status
QExt is currently highly unstable (pre-alpha) and subject to change, including API changes and wholesale renaming/removal/replacement of classes and functions.

### QeCore
- Public and private classes: done
- D-ptr and q-ptr, `auto` semantics: done
- `QeUniquePointer`: nearly complete

### QeWidgets
- Some widgets need cleanup, polish, and documentation

### QeRibbon
- Design decisions need to be made
- Some basic classes complete
- Emulation of Windows `SplitButton` control needs rewrite
- `QeRibbonGroupLayout` needs implementation 

### QeWindows
- QeUnknown Pointer: Nearly complete
- Numerous low-level functions done
- COM smart pointers need to be used everywhere 

## License
QExt is released under the GNU General Public License Version 3.

## Contributing
We're not quite there yet. Let me put some code up first.

### Style
QExt is written in the Qt development style, which is (circularly) dependant upon the KDE style. Deviations will be noted here if/when they occur.
