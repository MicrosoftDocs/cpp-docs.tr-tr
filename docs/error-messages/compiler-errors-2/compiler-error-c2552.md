---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2552'
title: Derleyici hatası C2552
ms.date: 11/04/2016
f1_keywords:
- C2552
helpviewer_keywords:
- C2552
ms.assetid: 0e0ab759-788a-4faf-9337-80d4b9e2e8c9
ms.openlocfilehash: bd028af17ac5535eb1f72acf053dda193d4cc636
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134530"
---
# <a name="compiler-error-c2552"></a>Derleyici hatası C2552

'tanımlayıcı' : toplama olmayan değerler başlatıcı listesiyle başlatılamaz

Toplam değer tanımlayıcısı hatalı olarak başlatıldı.

[Toplamalar](../../c-language/initializing-aggregate-types.md) şöyle tanımlanır:

- Diziler

- Şunlara sahip olmayan sınıflar, yapılar ve birleşimler:

  - Oluşturucular

  - Özel veya korumalı üyeler

  - Temel sınıflar

  - Sanal işlevler

Ayrıca Visual C++, kurucuların yer aldığı bir toplam değerde veri türlerine izin vermez.

Aşağıdakiler, bir tür üzerinde toplama başlatma denendiğinde C2552'nin olası tetikleme nedenlerini belirtir:

- Türün bir veya daha fazla kullanıcı tanımlı oluşturucusu var.

- Türün, bir veya daha fazla statik olmayan, özel veri üyeleri var.

- Türün bir veya daha fazla sanal işlevi var.

- Türün temel bir sınıfı var.

- Tür, bir başvuru sınıfı veya CLR arabirimi.

- Türün, öğelerinde yıkıcılar bulunan, sabit olmayan bir boyut dizisi (sıfır dizi) var.

Aşağıdaki örnek C2552'i oluşturur:

```cpp
// C2552.cpp
// compile with: /clr
#include <string>
using namespace std;

struct Pair_Incorrect {
private:
   string m_name;
   double m_val;
};

struct Pair_Correct1 {
public:
   Pair_Correct1(string name, double val)
      : m_name(name), m_val(val) {}

private:
   string m_name;
   double m_val;
};

struct Pair_Correct2 {
public:
   string m_name;
   double m_val;
};

int main() {
   // To fix, add a constructor to this class and use it for
   // initializing the data members, see Pair_Correct1 (below)
   // or
   // Do not have any private or protected non-static data members,
   // see Pair_Correct2 (below).  Pair_Correct2 is not recommended in
   // case your object model requires some non-static data members to
   // be private or protected

   string name("John");
   Pair_Incorrect pair1 = { name, 0.0 };   // C2552

   // initialize a CLR immutable value type that has a constructor
   System::DateTime dt = {2001, 4, 12, 22, 16, 49, 844};   // C2552

   Pair_Correct1 pair2( name, 0.0 );
   Pair_Correct1 pair3 = Pair_Correct1( name, 0.0 );
   Pair_Correct2 pair4 = { name, 0.0 };
   System::DateTime dt2(2001, 4, 12, 22, 16, 49, 844);
}
```
