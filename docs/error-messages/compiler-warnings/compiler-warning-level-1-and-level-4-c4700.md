---
title: "Derleyici Uyarısı (düzey 1 ve düzey 4) C4700 | Microsoft Docs"
ms.custom: 
ms.date: 02/21/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4700
dev_langs:
- C++
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00b871d6199338cc3040d6bddedb85f8732dfccd
ms.sourcegitcommit: 4e416049665819ac62f5300ddf86e94adede4ba0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>Derleyici Uyarısı (düzey 1 ve düzey 4) C4700

> başlatılmamış yerel değişken '*adı*' kullanılan

Yerel değişken *adı* bırakıldı *kullanılan*, diğer bir deyişle, okuma, bir değer var. önce atanmış. C ve C++'de varsayılan olarak yerel değişkenler başlatılmamış. Herhangi bir değer başlatılmamış değişkenleri içerebilir ve bunların kullanılması tanımsız davranışa yol açar. Uyarı C4700 neredeyse her zaman öngörülemeyen sonuçlara veya kilitlenme programınıza neden olabilir. bir hata gösterir.

Bu sorunu gidermek için bunlar bildirirken yerel değişkenler başlatmak veya kullanıldıkları önce bir değer atayabilirsiniz. Bir işlev başvurusu parametre olarak geçirilen veya ne zaman adresini işaretçi parametre olarak geçirilen bir değişkeni başlatmak için kullanılabilir.

## <a name="example"></a>Örnek

Önce başlatılır ve sonuçlanabilir çöp değer türünü gösterir değişkenleri t, u ve v kullanıldığında bu örnek C4700 oluşturur. Değişkenleri x, y ve z kullanılmadan önce başlatıldığından uyarı neden değil:

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

Bu kodu çalıştırma, t, u ve v olduğunda başlatılmamış ve s çıktısı öngörülemeyen şöyledir:

```Output
Value in s: 37816963
Value in w: 42
```
