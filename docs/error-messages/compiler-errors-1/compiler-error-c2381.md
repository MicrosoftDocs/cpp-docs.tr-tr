---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2381'
title: Derleyici hatası C2381
ms.date: 11/04/2016
f1_keywords:
- C2381
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
ms.openlocfilehash: ccaed8e5fc637ffb7e5cd2a33a00ddb5cf7c102b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282199"
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
