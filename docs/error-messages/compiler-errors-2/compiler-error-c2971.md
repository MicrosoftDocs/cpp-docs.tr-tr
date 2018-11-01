---
title: Derleyici Hatası C2971
ms.date: 11/04/2016
f1_keywords:
- C2971
helpviewer_keywords:
- C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
ms.openlocfilehash: 09f3578bff5806fc32a3b5599dcfa8caa3696974
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437304"
---
# <a name="compiler-error-c2971"></a>Derleyici Hatası C2971

'class': şablon parametresi 'param': 'değişken': yerel bir değişken bir tür olmayan bağımsız değişken olarak kullanılamaz

Bir şablon bağımsız değişkeni bir ad veya yerel değişkenin adresi kullanamazsınız.

Aşağıdaki örnek, C2971 oluşturur:

```
// C2971.cpp
template <int *pi>
class Y {};

int global_var = 0;

int main() {
   int local_var = 0;
   Y<&local_var> aY;   // C2971
   // try the following line instead
   // Y<&global_var> aY;
}
```