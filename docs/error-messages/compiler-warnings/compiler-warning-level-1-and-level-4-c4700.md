---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1 ve düzey 4) C4700'
title: Derleyici Uyarısı (düzey 1 ve düzey 4) C4700
ms.date: 02/21/2018
f1_keywords:
- C4700
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
ms.openlocfilehash: 7ba19bdd6d8e25e095f796adc8cdb60b5cc8d325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241605"
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>Derleyici Uyarısı (düzey 1 ve düzey 4) C4700

> başlatılmamış yerel değişken '*Name*' kullanıldı

Yerel değişken *adı* *kullanıldı*, diğer bir deyişle, bir değer atanmadan önce, öğesinden okundu. C ve C++ ' da yerel değişkenler varsayılan olarak başlatılmaz. Başlatılmamış değişkenler herhangi bir değer içerebilir ve kullanımları tanımsız davranışa neden olur. Uyarı C4700 neredeyse her zaman, programınızda öngörülemeyen sonuçlara veya kilitlenmelere neden olabilecek bir hatayı gösterir.

Bu sorunu onarmak için, yerel değişkenleri bildirildiği sırada başlatabilir veya kullanılmadan önce bunlara bir değer atayabilirsiniz. Bir işlev, başvuru parametresi olarak geçirilen bir değişkeni başlatmak için veya adresi bir işaretçi parametresi olarak geçirildiğinde kullanılabilir.

## <a name="example"></a>Örnek

Bu örnek, t, u ve v değişkenleri başlatılmadan önce kullanıldığında ve sonuç olarak oluşabilecek çöp değer türünü gösteren C4700 oluşturur. X, y ve z değişkenleri, kullanılmadan önce başlatıldıklarından, uyarıya neden olmaz:

```cpp
// c4700.cpp
// compile by using: cl /EHsc /W4 c4700.cpp
#include <iostream>

// function takes an int reference to initialize
void initialize(int& i)
{
    i = 21;
}

int main()
{
    int s, t, u, v;   // Danger, uninitialized variables

    s = t + u + v;    // C4700: t, u, v used before initialization
    std::cout << "Value in s: " << s << std::endl;

    int w, x;         // Danger, uninitialized variables
    initialize(x);    // fix: call function to init x before use
    int y{10};        // fix: initialize y, z when declared
    int z{11};        // This C++11 syntax is recommended over int z = 11;

    w = x + y + z;    // Okay, all values initialized before use
    std::cout << "Value in w: " << w << std::endl;
}
```

Bu kod çalıştırıldığında, t, u ve v başlatılmadığında, s için çıkış öngörülemeyen olur:

```Output
Value in s: 37816963
Value in w: 42
```
