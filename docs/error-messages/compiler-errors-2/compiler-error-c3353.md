---
title: Derleyici hatası C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: 332e0b253aed53f2adadf448b6a9c0681abc825e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74747461"
---
# <a name="compiler-error-c3353"></a>Derleyici hatası C3353

' Delegate ': bir temsilci yalnızca bir genel işlevden veya yönetilen ya da WinRT türünün üye işlevinden oluşturulabilir

[Delegate](../../extensions/delegate-cpp-component-extensions.md) anahtar sözcüğüyle belirtilen temsilciler yalnızca genel kapsamda bildirilemez.

Aşağıdaki örnek C3353 oluşturur:

```cpp
// C3353.cpp
// compile with: /clr
delegate int f;   // C3353
```
