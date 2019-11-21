---
title: Derleme Zamanı Kapsüllemesi için Pimpl (Modern C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: f1eb06ad3a52be486f085babf699677951b1ee71
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245183"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>Derleme Zamanı Kapsüllemesi için Pimpl (Modern C++)

The *pimpl idiom* is a modern C++ technique to hide implementation, to minimize coupling, and to separate interfaces. Pimpl is short for "pointer to implementation." You may already be familiar with the concept but know it by other names like Cheshire Cat or Compiler Firewall idiom.

## <a name="why-use-pimpl"></a>Why use pimpl?

Here's how the pimpl idiom can improve the software development lifecycle:

- Minimization of compilation dependencies.

- Separation of interface and implementation.

- Portability.

## <a name="pimpl-header"></a>Pimpl header

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

The pimpl idiom avoids rebuild cascades and brittle object layouts. It's well suited for (transitively) popular types.

## <a name="pimpl-implementation"></a>Pimpl implementation

Define the `impl` class in the .cpp file.

```cpp
// my_class.cpp
class my_class::impl {  // defined privately here
  // ... all private data and functions: all of these
  //     can now change without recompiling callers ...
};
my_class::my_class(): pimpl( new impl )
{
  // ... set impl values ...
}
```

## <a name="best-practices"></a>Önerilen uygulamalar

Consider whether to add support for non-throwing swap specialization.

## <a name="see-also"></a>Ayrıca bkz.

[Welcome back to C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
