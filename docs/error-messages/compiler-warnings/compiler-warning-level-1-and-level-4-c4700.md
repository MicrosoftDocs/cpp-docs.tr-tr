---
title: Derleyici Uyarısı (düzey 1 ve düzey 4) C4700
ms.date: 02/21/2018
f1_keywords:
- C4700
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
ms.openlocfilehash: fa3326bd5ab495dbc4c54130bb168422eb827dce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463225"
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>Derleyici Uyarısı (düzey 1 ve düzey 4) C4700

> başlatılmamış yerel değişken '*adı*' kullanılır

Yerel değişken *adı* olmuştur *kullanılan*, diğer bir deyişle, okuma, bir değer var. önce atanmış. C ve C++ içinde varsayılan olarak yerel değişken başlatılmamış. Başlatılmamış değişkenler herhangi bir değer içerebilir ve kullanımları tanımsız davranışa yol. Uyarı C4700 neredeyse her zaman programınızda öngörülemeyen sonuçlara veya kilitlenmelere neden olabilir bir hata gösterir.

Bu sorunu gidermek için bildirildikleri olduğunda yerel değişkenlerini başlatmak veya kullanmadan önce bir değer atayabilirsiniz. Bir işlev başvurusu parametre olarak geçirilen veya ne zaman adresini işaretçi parametre olarak geçirilen bir değişkeni başlatmak için kullanılabilir.

## <a name="example"></a>Örnek

Bu örnek, başlatılır ve sonuçlanabilir çöp değer türünü gösterir önce değişkenleri t ve u v kullanıldığında C4700 oluşturur. Değişkenleri x, y ve z kullanılmadan önce başlatıldığından uyarı neden değil:

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

S için çıktıyı tahmin edilemez ve bu kod çalıştırma, t, u ve v olduğunda başlatılmamış verilmiştir:

```Output
Value in s: 37816963
Value in w: 42
```
