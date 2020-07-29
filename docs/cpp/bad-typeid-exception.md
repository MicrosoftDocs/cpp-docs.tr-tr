---
title: bad_typeid özel durumu
ms.date: 10/04/2019
f1_keywords:
- bad_typeid
- bad_typeid_cpp
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
ms.openlocfilehash: 3e01f97c67803408c9ce5bf056e3e9ed4746d259
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229174"
---
# <a name="bad_typeid-exception"></a>bad_typeid özel durumu

**Bad_typeid** özel durumu, IÇIN işleneni null işaretçisiyse [TypeId işleci](../cpp/typeid-operator.md) tarafından oluşturulur **`typeid`** .

## <a name="syntax"></a>Sözdizimi

```
catch (bad_typeid)
   statement
```

## <a name="remarks"></a>Açıklamalar

**Bad_typeid** arabirimi:

```cpp
class bad_typeid : public exception
{
public:
   bad_typeid();
   bad_typeid(const char * _Message = "bad typeid");
   bad_typeid(const bad_typeid &);
   virtual ~bad_typeid();

   bad_typeid& operator=(const bad_typeid&);
   const char* what() const;
};
```

Aşağıdaki örnek, **`typeid`** **bad_typeid** bir özel durum oluşturan işleci gösterir.

```cpp
// expre_bad_typeid.cpp
// compile with: /EHsc /GR
#include <typeinfo>
#include <iostream>

class A{
public:
   // object for class needs vtable
   // for RTTI
   virtual ~A();
};

using namespace std;
int main() {
A* a = NULL;

try {
   cout << typeid(*a).name() << endl;  // Error condition
   }
catch (bad_typeid){
   cout << "Object is NULL" << endl;
   }
}
```

## <a name="output"></a>Çıktı

```Output
Object is NULL
```

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma zamanı tür bilgileri](../cpp/run-time-type-information.md)\
[Anahtar sözcükler](../cpp/keywords-cpp.md)
