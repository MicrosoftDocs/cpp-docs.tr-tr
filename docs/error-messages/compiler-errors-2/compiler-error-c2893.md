---
title: Derleyici hatası C2893
ms.date: 11/04/2016
f1_keywords:
- C2893
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
ms.openlocfilehash: ca603eb94d5d528a7fed15e0320e1f5d88bf0629
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760882"
---
# <a name="compiler-error-c2893"></a>Derleyici hatası C2893

' Şablon adı ' işlev şablonu özelleştirilemedi

Derleyici bir işlev şablonu özelleştirilemedi. Bu hatanın pek çok nedeni olabilir.

Genel olarak, bir C2893 hatasını çözme yöntemi işlevin imzasını gözden geçirmenin yanı sıra her türü örneklendirilediğinizden emin olmanızı sağlar.

## <a name="example"></a>Örnek

C2893 `f`şablon parametresi `T` `std::map<int,int>`olarak anlaşılamadığından, ancak `std::map<int,int>` üye `data_type` yok (`T::data_type` `T = std::map<int,int>`ile başlatılamaz.). Aşağıdaki örnek C2893 oluşturur.

```cpp
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
