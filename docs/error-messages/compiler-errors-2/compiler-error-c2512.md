---
title: Derleyici Hatası C2512
ms.date: 02/09/2018
f1_keywords:
- C2512
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
ms.openlocfilehash: 16a1da0e882cd178c9e01737480d74eb23c7c38c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164832"
---
# <a name="compiler-error-c2512"></a>Derleyici Hatası C2512

> '*tanımlayıcı*': kullanılabilir uygun varsayılan oluşturucu yok

A *varsayılan oluşturucu*, hiçbir bağımsız değişken gerektirmediğini bir oluşturucu, belirtilen sınıf, yapı veya birleşim için kullanılabilir değildir. Yalnızca hiçbir kullanıcı tarafından tanımlanan oluşturucuları sağlanırsa, derleyici varsayılan bir oluşturucu sağlar.

Void olmayan bir parametre alan bir oluşturucu sağlayın ve (örneğin, öğeleri dizi olarak) hiçbir parametre olmadan oluşturulacak sınıfınıza izin vermek istediğiniz, varsayılan bir oluşturucu de belirtmeniz gerekir. Varsayılan Oluşturucu, bir oluşturucu tüm parametreler için varsayılan değerlere sahip olabilir.

## <a name="example"></a>Örnek

Bağımsız değişken alan bir class veya struct Oluşturucu tanımlarken hatası C2512 yaygın bir nedeni olduğundan ve bir örneği, sınıfın veya yapının tüm bağımsız değişkenler olmadan bildirme girişimi. Örneğin, `struct B` aşağıda gerektiren bir yapıcı bir `char *` bağımsız değişkeni, ancak hiçbir bağımsız değişken bir değil. İçinde `main`B örneğini bildirildi, ancak hiçbir bağımsız değişken sağlandı. B için varsayılan bir oluşturucu bulamadığından derleyici C2512 oluşturur.

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

Yapı ya da sınıfı için varsayılan oluşturucu tanımlayarak bu sorunu düzeltebilirsiniz `B() {}`, ya da tüm bağımsız değişkenler sahip olduğu varsayılan değerler, aşağıdaki gibi bir oluşturucu `B (char * = nullptr) {}`.
