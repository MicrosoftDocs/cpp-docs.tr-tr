---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2512'
title: Derleyici hatası C2512
ms.date: 02/09/2018
f1_keywords:
- C2512
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
ms.openlocfilehash: 40574ab7fc54ba678729429401ed14fefefe9ebd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212915"
---
# <a name="compiler-error-c2512"></a>Derleyici hatası C2512

> '*tanımlayıcı*': uygun bir varsayılan oluşturucu yok

*Varsayılan Oluşturucu*, bağımsız değişken gerektirmeyen bir Oluşturucu, belirtilen sınıf, yapı veya birleşim için kullanılamaz. Derleyici, yalnızca Kullanıcı tanımlı oluşturucular sağlanmadığında varsayılan bir oluşturucu sağlar.

Void olmayan bir parametre alan bir Oluşturucu sağlarsanız ve sınıfınızın parametre olmadan (örneğin, bir dizinin öğeleri olarak) oluşturulmasını sağlamak istiyorsanız, ayrıca bir varsayılan Oluşturucu sağlamanız gerekir. Varsayılan Oluşturucu, tüm parametrelerin varsayılan değerlerine sahip bir Oluşturucu olabilir.

## <a name="example"></a>Örnek

Hata C2512 yaygın bir nedeni, bağımsız değişken alan bir sınıf veya yapı Oluşturucu tanımladığınızda ve sonra bir bağımsız değişken olmadan sınıfınızın veya yapının bir örneğini bildirmeye çalışır. Örneğin, `struct B` aşağıdaki bir `char *` bağımsız değişken içermeyen bir bağımsız değişken gerektirmeyen bir Oluşturucu bildirir. İçinde `main` , B 'nin bir örneği bildirilmiştir, ancak bağımsız değişken sağlanmaz. Derleyici, B için varsayılan bir Oluşturucu bulamadığı için C2512 oluşturur.

```cpp
// C2512.cpp
// Compile with: cl /W4 c2512.cpp
// C2512 expected
struct B {
   B (char *) {}
   // Uncomment the following line to fix.
   // B() {}
};

int main() {
   B b;   // C2512 - This requires a default constructor
}
```

Yapı veya sınıfınız için varsayılan bir Oluşturucu `B() {}` veya gibi tüm bağımsız değişkenlerin varsayılan değerlere sahip olduğu bir Oluşturucu tanımlayarak bu sorunu çözebilirsiniz `B (char * = nullptr) {}` .
