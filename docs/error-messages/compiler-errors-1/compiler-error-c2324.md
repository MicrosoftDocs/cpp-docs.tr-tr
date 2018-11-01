---
title: Derleyici Hatası C2324
ms.date: 11/04/2016
f1_keywords:
- C2324
helpviewer_keywords:
- C2324
ms.assetid: 215f0544-85b0-452d-825f-17a388b6a61c
ms.openlocfilehash: 694d1b2c9df4830e721af51517044e9734fcf415
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449835"
---
# <a name="compiler-error-c2324"></a>Derleyici Hatası C2324

'identifier': 'name' sağında beklenmiyor

Yanlış bir tanımlayıcıyı kullanarak bir yok Edicisi çağrılır.

Aşağıdaki örnek, C2324 oluşturur:

```
// C2324.cpp
class A {};
typedef A* pA_t;
int i;

int main() {
   pA_t * ppa = new pA_t;
   ppa->~i;   // C2324
   ppa->~pA_t();   // OK
}
```