---
title: Derleyici Hatası C2512 | Microsoft Docs
ms.custom: ''
ms.date: 02/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2512
dev_langs:
- C++
helpviewer_keywords:
- C2512
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 286be19ca407039a77d51503a34c7a27da1c3d5b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2512"></a>Derleyici Hatası C2512

> '*tanımlayıcısı*': kullanılabilir uygun varsayılan oluşturucu yok  

A *varsayılan oluşturucu*, hiç bağımsız değişken gerektiren bir oluşturucu belirtilen sınıf, yapı veya birlik için kullanılabilir değil. Yalnızca hiçbir kullanıcı tarafından tanımlanan oluşturucular sağlanıyorsa derleyici varsayılan bir oluşturucu sağlar.

Bir geçersiz kılma olmayan parametresi alan bir oluşturucu sağlayın ve (örneğin, bir dizinin öğeleri) hiçbir parametrelerle oluşturulacak sınıfınız izin vermek istiyorsanız, varsayılan bir oluşturucu sağlamanız gerekir. Varsayılan Oluşturucu tüm parametrelerin değerlerini varsayılan bir oluşturucu olabilir.

## <a name="example"></a>Örnek

Bağımsız değişken almayan bir sınıf veya yapı Oluşturucu tanımlarken bir ortak C2512 hatanın nedeni ve ardından sınıf veya yapı herhangi bir bağımsız değişken olmadan bir örneğini bildirmek deneyin. Örneğin, `struct B` aşağıda gerektiren bir oluşturucu bildiren bir `char *` bağımsız değişkeni, ancak bağımsız değişken almayan bir değil. İçinde `main`B örneği bildirildi, ancak bağımsız değişken sağlandı. B için varsayılan bir oluşturucu bulamadığından derleyici C2512 oluşturur.

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

Yapı ya da sınıfı için varsayılan bir oluşturucu tanımlayarak bu sorunu gidermek `B() {}`, ya da tüm bağımsız değişkenler sahip olduğu varsayılan değerler, aşağıdaki gibi bir oluşturucu `B (char * = nullptr) {}`.
