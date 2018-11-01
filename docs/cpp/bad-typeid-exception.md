---
title: bad_typeid Özel Durumu
ms.date: 11/04/2016
f1_keywords:
- bad_typeid
- bad_typeid_cpp
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
ms.openlocfilehash: 5d53d2e25b56aa78edaebcd4be0e468993ebb8f8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514042"
---
# <a name="badtypeid-exception"></a>bad_typeid Özel Durumu

**Bad_typeid** tarafından özel durum [typeid işleci](../cpp/typeid-operator.md) zaman için işlenen **TypeID** bir NULL işaretçidir.

## <a name="syntax"></a>Sözdizimi

```
catch (bad_typeid)
   statement
```

## <a name="remarks"></a>Açıklamalar

Arabirimin **bad_typeid** olan:

```cpp
class bad_typeid : public exception
{
public:
   bad_typeid(const char * _Message = "bad typeid");
   bad_typeid(const bad_typeid &);
   virtual ~bad_typeid();
};
```

Aşağıdaki örnekte gösterildiği **TypeID** atma işleci bir **bad_typeid** özel durum.

```cpp
// expre_bad_typeid.cpp
// compile with: /EHsc /GR
#include <typeinfo.h>
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

## <a name="output"></a>Çıkış

```Output
Object is NULL
```

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma Zamanı Tür Bilgileri](../cpp/run-time-type-information.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)