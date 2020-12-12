---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2893'
title: Derleyici hatası C2893
ms.date: 11/04/2016
f1_keywords:
- C2893
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
ms.openlocfilehash: 42e31327096a539feeb691c698b52f57ecb615a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278265"
---
# <a name="compiler-error-c2893"></a>Derleyici hatası C2893

' Şablon adı ' işlev şablonu özelleştirilemedi

Derleyici bir işlev şablonu özelleştirilemedi. Bu hatanın pek çok nedeni olabilir.

Genel olarak, bir C2893 hatasını çözme yöntemi işlevin imzasını gözden geçirmenin yanı sıra her türü örneklendirilediğinizden emin olmanızı sağlar.

## <a name="example"></a>Örnek

C2893 `f` , şablon parametresi olarak `T` çıkarılmış `std::map<int,int>` , ancak `std::map<int,int>` üyesi olmayan `data_type` ( `T::data_type` ile örneği oluşturulamıyor `T = std::map<int,int>` .) nedeniyle oluşur. Aşağıdaki örnek C2893 oluşturur.

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
