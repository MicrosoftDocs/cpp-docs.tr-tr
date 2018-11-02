---
title: Derleyici Uyarısı (düzey 4) C4510
ms.date: 11/04/2016
f1_keywords:
- C4510
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
ms.openlocfilehash: 80183e9f7ef17cbc37592f36eb8db1df2be94827
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539067"
---
# <a name="compiler-warning-level-4-c4510"></a>Derleyici Uyarısı (düzey 4) C4510

'class': varsayılan oluşturucu üretilemedi

Belirtilen sınıfın varsayılan bir oluşturucu derleyici oluşturulamıyor ve kullanıcı tanımlı oluşturucusu yok oluşturuldu. Bu tür nesneler oluşturmak mümkün olmayacaktır.

Derleyicinin bir varsayılan oluşturucu oluşturmasını önlemek birkaç durum mevcuttur dahil olmak üzere:

- Const veri üyesi.

- Bir başvuru veri üyesi.

Bu üyeler başlatır sınıfı için bir kullanıcı tanımlı varsayılan oluşturucu oluşturmanız gerekir.

Aşağıdaki örnek, C4510 oluşturur:

```
// C4510.cpp
// compile with: /W4
struct A {
   const int i;
   int &j;
   A& operator=( const A& ); // C4510 expected
   // uncomment the following line to resolve this C4510
   // A(int ii, int &jj) : i(ii), j(jj) {}
};   // C4510

int main() {
}
```