---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2344'
title: Derleyici hatası C2344
ms.date: 11/04/2016
f1_keywords:
- C2344
helpviewer_keywords:
- C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
ms.openlocfilehash: 1ad4f1808f407a9f654f5bbf3a022c2dc7b0b3ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234767"
---
# <a name="compiler-error-c2344"></a>Derleyici hatası C2344

align (#): hizalama ikinin üssü olmalıdır

[Align](../../cpp/align-cpp.md) anahtar sözcüğünü kullanırken geçirdiğiniz değer ikinin üssü olmalıdır.

Örneğin, aşağıdaki kod C2344 oluşturur, çünkü 3 iki üssü değildir:

```cpp
// C2344.cpp
// compile with: /c
__declspec(align(3)) int a;   // C2344
__declspec(align(4)) int b;   // OK
```
