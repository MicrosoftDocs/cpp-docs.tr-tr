---
title: Derleyici hatası C2128
ms.date: 11/04/2016
f1_keywords:
- c2128
helpviewer_keywords:
- C2128
ms.assetid: 08cbf734-75b3-49f2-9026-9b319947612d
ms.openlocfilehash: 461492946271a141cbdb563b34769e69e9cf75e1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755180"
---
# <a name="compiler-error-c2128"></a>Derleyici hatası C2128

' function ': alloc_text/same_seg yalnızca C bağlaması olan işlevler için geçerlidir

`pragma` `alloc_text`, yalnızca C bağlantısına sahip olacak şekilde belirtilen işlevlerle kullanılabilir.

Aşağıdaki örnek C2128 oluşturur:

```cpp
// C2128.cpp
// compile with: /c

// Delete the following line to resolve.
void func();
// #pragma alloc_text("my segment", func)   // C2128

extern "C" {
void func();
}

#pragma alloc_text("my segment", func)
void func() {}
```
