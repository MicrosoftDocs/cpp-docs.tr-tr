---
title: Compiler Warning (level 3) C4538
ms.date: 11/04/2016
f1_keywords:
- C4538
helpviewer_keywords:
- C4538
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
ms.openlocfilehash: b60d919952b07e63d28a373414f1307d2031f00d
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188954"
---
# <a name="compiler-warning-level-3-c4538"></a>Compiler Warning (level 3) C4538

'type' : const/volatile qualifiers on this type are not supported

A qualifier keyword was applied to an array incorrectly. For more information, see [array](../../extensions/arrays-cpp-component-extensions.md).

The following sample generates C4538:

```cpp
// C4538.cpp
// compile with: /clr /W3 /LD
const array<int> ^f1();   // C4538
array<const int> ^f2();   // OK
```