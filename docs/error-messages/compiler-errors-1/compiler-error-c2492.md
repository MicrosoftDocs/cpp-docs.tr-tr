---
title: Derleyici hatası C2492
ms.date: 11/04/2016
f1_keywords:
- C2492
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
ms.openlocfilehash: fd52b434f86bdc93124c6005bbf7fadad3cb56b2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757065"
---
# <a name="compiler-error-c2492"></a>Derleyici hatası C2492

'*değişken*': iş parçacığı depolama süresine sahip verilerin dll arabirimi olmayabilir

Değişkeni, [iş parçacığı](../../cpp/thread.md) ÖZNITELIĞIYLE ve DLL arabirimiyle birlikte bildirilmiştir. `thread` değişkeninin adresi çalışma zamanına kadar bilinmiyor, bu nedenle bir DLL içeri veya dışarı aktarmaya bağlanamaz.

Aşağıdaki örnek C2492 oluşturur:

```cpp
// C2492.cpp
// compile with: /c
class C {
public:
   char   ch;
};

__declspec(dllexport) __declspec(thread) C c_1;   // C2492
__declspec(thread) C c_1;   // OK
```
