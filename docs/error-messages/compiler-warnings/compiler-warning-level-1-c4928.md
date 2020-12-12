---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4928'
title: Derleyici Uyarısı (düzey 1) C4928
ms.date: 11/04/2016
f1_keywords:
- C4928
helpviewer_keywords:
- C4928
ms.assetid: 77235d7f-9360-45cb-8348-d148c605c4a3
ms.openlocfilehash: 15cf688a01ef62b6c76b8be5a61d43d436cfe790
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203620"
---
# <a name="compiler-warning-level-1-c4928"></a>Derleyici Uyarısı (düzey 1) C4928

hatalı kopya başlatma; birden çok kullanıcı tanımlı dönüştürme örtük olarak uygulandı

Birden çok kullanıcı tanımlı dönüştürme yordamı bulundu. Derleyici, tüm bu yordamlar için kodu yürütür.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Aşağıdaki örnek C4928 oluşturur:

```cpp
// C4928.cpp
// compile with: /W1
#pragma warning(default: 4928)

struct I
{
};

struct I1 : I
{
};

struct I2 : I
{
};

template <class T>
struct Ptr
{
   operator T*()
   {
      return 0;
   }

   Ptr()
   {
   }

   Ptr(I*)
   {
   }
};

int main()
{
   Ptr<I1> p1;
   Ptr<I2> p2 = p1;   // C4928
   // try one of the following two lines to resolve this error
   // Ptr<I2> p2(p1);
   // Ptr<I2> p2 = (I1*) p1;
}
```
