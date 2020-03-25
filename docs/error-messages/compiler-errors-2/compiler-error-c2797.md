---
title: Derleyici Hatası C2797
ms.date: 11/04/2016
f1_keywords:
- C2797
helpviewer_keywords:
- C2797
ms.assetid: 9fb26d35-eb5c-46fc-9ff5-756fba5bdaff
ms.openlocfilehash: 9973ddcccc69e85bdf79e0623fa4bcc1d6689032
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202096"
---
# <a name="compiler-error-c2797"></a>Derleyici Hatası C2797

Dışı Üye başlatıcısı listesinin veya statik olmayan veri üyesi başlatıcısının içindeki liste başlatması uygulanmadı.

Bu uyarı, Visual Studio 2015 ' de kullanılmıyor. Visual Studio 2013 ve önceki sürümlerde, Microsoft C++ derleyicisi, bir üye Başlatıcı listesinde veya statik olmayan bir veri üyesi başlatıcısında liste başlatma uygulamaz. Güncelleştirme 3 ' ü Visual Studio 2013 önce, bu, hatalı kod oluşturmaya yol açabilecek şekilde sessizce bir işlev çağrısına dönüştürüldü. Visual Studio 2013 güncelleştirme 3, bunu hata olarak raporlar.

Bu örnek C2797 oluşturur:

```
#include <vector>
struct S {
    S() : v1{1} {} // C2797, VS2013 RTM incorrectly calls 'vector(size_type)'

    std::vector<int> v1;
    std::vector<int> v2{1, 2}; // C2797, VS2013 RTM incorrectly calls 'vector(size_type, const int &)'
};
```

Bu örnek ayrıca C2797 üretir:

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

Bu sorunu düzeltemedi, iç listelerin açık olarak oluşturulmasını kullanabilirsiniz. Örneğin:

```
#include <vector>
typedef std::vector<int> Vector;
struct S {
    S() : v1(Vector{1}) {}

    Vector v1;
    Vector v2 = Vector{1, 2};
};
```

Liste başlatma gerektirmeyin:

```
struct S {
    S() : s1("") {}

    std::string s1;
    std::string s2 = std::string("");
};
```

(Visual Studio 2013 derleyici, bunu Visual Studio 2013 güncelleştirme 3 ' ten önce örtülü olarak yapar.)
