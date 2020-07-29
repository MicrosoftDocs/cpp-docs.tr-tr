---
title: Derleyici hatası C2381
ms.date: 11/04/2016
f1_keywords:
- C2381
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
ms.openlocfilehash: a36655b0b3a28536538998656d7ce354c409d07c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225533"
---
# <a name="compiler-error-c2381"></a>Derleyici hatası C2381

' function ': yeniden tanımlama; __declspec (noreturn) farklı

Bir işlev bildirildi ve sonra tanımlandı, ancak tanım [noreturn](../../cpp/noreturn.md) **`__declspec`** değiştiricisini kullandı. Öğesinin kullanımı, `noreturn` işlevinin yeniden açıklamasını oluşturur; bildirim ve tanımın kullanımını kabul etmesi gerekir `noreturn` .

Aşağıdaki örnek C2381 oluşturur:

```cpp
// C2381.cpp
// compile with: /c
void f1();
void __declspec(noreturn) f1() {}   // C2381
void __declspec(noreturn) f2() {}   // OK
```
