---
title: Compiler Warning (level 3) C4646
ms.date: 11/04/2016
f1_keywords:
- C4646
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
ms.openlocfilehash: 2f156bfbe92fbfb3437a7f0b9ac77a91976c2b1c
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189389"
---
# <a name="compiler-warning-level-3-c4646"></a>Compiler Warning (level 3) C4646

function declared with __declspec(noreturn) has non-void return type

A function marked with the [noreturn](../../cpp/noreturn.md) `__declspec` modifier should have a [void](../../cpp/void-cpp.md) return type.

The following sample generates C4646:

```cpp
// C4646.cpp
// compile with: /W3 /WX
int __declspec(noreturn) TestFunction()
{   // C4646  make return type void
}
```