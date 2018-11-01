---
title: Derleyici Hatası C2255
ms.date: 11/04/2016
f1_keywords:
- C2255
helpviewer_keywords:
- C2255
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
ms.openlocfilehash: ae2c61257af3e1aca2d26ce5f8801999f7bb77c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429399"
---
# <a name="compiler-error-c2255"></a>Derleyici Hatası C2255

'element': bir sınıf tanımının dışında kullanılamaz

Örneğin, değiştiricilere işlevi olarak bildirilen bir `friend`.

Aşağıdaki örnek, C2255 oluşturur:

```
// C2255.cpp
// compile with: /c
class A {
private:
   void func1();
   friend void func2();
};

friend void func1() {}   // C2255
void func2(){}
```