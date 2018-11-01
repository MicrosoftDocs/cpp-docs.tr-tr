---
title: Derleyici Hatası C2381
ms.date: 11/04/2016
f1_keywords:
- C2381
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
ms.openlocfilehash: b29f7dac6c6d71e12eb0f003cdfc151dd2c349a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663205"
---
# <a name="compiler-error-c2381"></a>Derleyici Hatası C2381

'function': yeniden tanımlama; __declspec(noreturn) farklıdır

Bir işlev bildirildi ve kullanılan tanımı ardından tanımlanan [noreturn](../../cpp/noreturn.md) `__declspec` değiştiricisi. Kullanımını `noreturn` oluşturan bir işlevi yeniden tanımlama; bildirim ve tanım kullanımı üzerinde anlaşmaya varması gerekiyor `noreturn`.

Aşağıdaki örnek, C2381 oluşturur:

```
// C2381.cpp
// compile with: /c
void f1();
void __declspec(noreturn) f1() {}   // C2381
void __declspec(noreturn) f2() {}   // OK
```