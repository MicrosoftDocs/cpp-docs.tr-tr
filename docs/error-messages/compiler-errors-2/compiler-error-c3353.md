---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3353'
title: Derleyici hatası C3353
ms.date: 11/04/2016
f1_keywords:
- C3353
helpviewer_keywords:
- C3353
ms.assetid: 5699c04b-d504-46ce-bf71-c200318fed71
ms.openlocfilehash: 50ff7a6b104f3e16ce17f1398da49a146c0d41a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335037"
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
