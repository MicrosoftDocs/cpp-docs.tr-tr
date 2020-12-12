---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2157'
title: Derleyici hatası C2157
ms.date: 11/04/2016
f1_keywords:
- C2157
helpviewer_keywords:
- C2157
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
ms.openlocfilehash: 4d8619d3d27bd9a1cb0c5323d9fdbf462b043ecf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181334"
---
# <a name="compiler-error-c2157"></a>Derleyici hatası C2157

' function ': pragma listesinde kullanılmadan önce bildirilmelidir

İşlev adı, bir [alloc_text](../../preprocessor/alloc-text.md) pragma için işlev listesinde başvurulmadan önce bildirilmemiş.

Aşağıdaki örnek C2157 oluşturur:

```cpp
// C2157.cpp
// compile with: /c
#pragma alloc_text( "func", func)   // C2157

// OK
extern "C" void func();
#pragma alloc_text( "func", func)
```
