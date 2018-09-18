---
title: Derleyici Hatası C2797 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2797
dev_langs:
- C++
helpviewer_keywords:
- C2797
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 701ec194c968b9f1d17269573b33e78d69fbb256
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035376"
---
# <a name="compiler-error-c2797"></a>Derleyici Hatası C2797

(Eski) Liste başlatması üye başlatıcı listesi veya statik olmayan veri üyesi başlatıcısı uygulanmadı.

Bu uyarı, Visual Studio 2015'te kullanılmıyor. Visual Studio 2013 veya önceki sürümlerinde, Visual C++ derleyicisi liste başlatması veya bir üye başlatıcı listesi, hem de statik olmayan veri üyesi başlatıcısı uygulamıyor. Visual Studio 2013 güncelleştirme 3 önce bu sessiz hatalı kod oluşturma için yol açabilecek bir işlev çağrısı için dönüştürüldü. Visual Studio 2013 güncelleştirme 3'ü bu hata olarak bildirir.

Bu örnek C2797 oluşturur:

```
#include <vector>
struct S {
    S() : v1{1} {} // C2797, VS2013 RTM incorrectly calls 'vector(size_type)'

    std::vector<int> v1;
    std::vector<int> v2{1, 2}; // C2797, VS2013 RTM incorrectly calls 'vector(size_type, const int &)'
};

```

Bu örnek ayrıca C2797 oluşturur:

```
struct S1 {
    int i;
};

struct S2 {
    S2() : s1{0} {} // C2797, VS2013 RTM interprets as S2() : s1(0) {} causing C2664
    S1 s1;
    S1 s2{0}; // C2797, VS2013 RTM interprets as S1 s2 = S1(0); causing C2664
};

```

Bu sorunu gidermek için açık yapımı iç listeleri kullanabilirsiniz. Örneğin:

```
#include <vector>
typedef std::vector<int> Vector;
struct S {
    S() : v1(Vector{1}) {}

    Vector v1;
    Vector v2 = Vector{1, 2};
};

```

Liste başlatma gerekmiyorsa:

```
struct S {
    S() : s1("") {}

    std::string s1;
    std::string s2 = std::string("");
};

```

(Visual Studio 2013'teki derleyici bu örtülü olarak önce Visual Studio 2013 güncelleştirme 3 desteklemez.)