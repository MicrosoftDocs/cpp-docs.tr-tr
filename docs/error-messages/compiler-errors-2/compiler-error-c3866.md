---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3866'
title: Derleyici hatası C3866
ms.date: 11/04/2016
f1_keywords:
- C3866
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
ms.openlocfilehash: fceb8ed41a3cbfc287f4c1115cd0502ce8506925
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222872"
---
# <a name="compiler-error-c3866"></a>Derleyici hatası C3866

işlev çağrısında bağımsız değişken listesi eksik

Statik olmayan bir üye işlevinin içinde, yıkıcı veya Sonlandırıcı çağrısında bağımsız değişken listesi yoktu.

Aşağıdaki örnek C3866 oluşturur:

```cpp
// C3866.cpp
// compile with: /c
class C {
   ~C();
   void f() {
      this->~C;   // C3866
      this->~C();   // OK
   }
};
```
