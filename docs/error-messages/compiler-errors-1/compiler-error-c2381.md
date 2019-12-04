---
title: Derleyici hatası C2381
ms.date: 11/04/2016
f1_keywords:
- C2381
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
ms.openlocfilehash: 834b9939a99c694c702bb268b928575b4beb8856
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745401"
---
# <a name="compiler-error-c2381"></a>Derleyici hatası C2381

' function ': yeniden tanımlama; __declspec (noreturn) farklı

Bir işlev bildirildi ve sonra tanımlandı, ancak tanım [noreturn](../../cpp/noreturn.md) `__declspec` değiştiricisini kullandı. `noreturn` kullanımı işlevin yeniden açıklamasını oluşturur; bildirim ve tanımın `noreturn`kullanımını kabul etmesi gerekir.

Aşağıdaki örnek C2381 oluşturur:

```cpp
// C2381.cpp
// compile with: /c
void f1();
void __declspec(noreturn) f1() {}   // C2381
void __declspec(noreturn) f2() {}   // OK
```
