---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2128'
title: Derleyici hatası C2128
ms.date: 11/04/2016
f1_keywords:
- c2128
helpviewer_keywords:
- C2128
ms.assetid: 08cbf734-75b3-49f2-9026-9b319947612d
ms.openlocfilehash: fd72ffd45206a885d56b3d2f1821240279f06e21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323174"
---
# <a name="compiler-error-c2128"></a>Derleyici hatası C2128

' function ': alloc_text/same_seg yalnızca C bağlaması olan işlevler için geçerlidir

`#pragma alloc_text` yalnızca C bağlantısına sahip olacak şekilde belirtilen işlevlerle kullanılabilir.

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
