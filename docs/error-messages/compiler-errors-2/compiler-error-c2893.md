---
title: Derleyici Hatası C2893
ms.date: 11/04/2016
f1_keywords:
- C2893
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
ms.openlocfilehash: f1fad1ad18af54945ef32dadaac50a6de4dbd62f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455191"
---
# <a name="compiler-error-c2893"></a>Derleyici Hatası C2893

'Şablon adı' işlev şablonu özelleştirilemedi

Derleyici, bir işlev şablonu özelleştirilemedi. Bu hatanın birçok nedeni olabilir.

Genel olarak, C2893 hatayı gidermek için işlev imzası gözden geçirin ve her türün örneğini oluşturabilir emin olmak için yoludur.

## <a name="example"></a>Örnek

C2893 gerçekleşir çünkü `f`'s şablon parametresi `T` olmasını atanan `std::map<int,int>`, ancak `std::map<int,int>` üyesi yok `data_type` (`T::data_type` ile oluşturulabilir değil `T = std::map<int,int>`.). Aşağıdaki örnek, C2893 oluşturur.

```
// C2893.cpp
// compile with: /c /EHsc
#include<map>
using namespace std;
class MyClass {};

template<class T>
inline typename T::data_type
// try the following line instead
// inline typename  T::mapped_type
f(T const& p1, MyClass const& p2);

template<class T>
void bar(T const& p1) {
    MyClass r;
    f(p1,r);   // C2893
}

int main() {
   map<int,int> m;
   bar(m);
}
```