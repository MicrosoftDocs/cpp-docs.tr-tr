---
description: 'Daha fazla bilgi edinin: Protected (C++)'
title: protected (C++)
ms.date: 11/04/2016
f1_keywords:
- protected_cpp
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
ms.openlocfilehash: 17b74db6ae257e757253c12fdfeb4fa9bac2a3db
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299117"
---
# <a name="protected-c"></a>protected (C++)

## <a name="syntax"></a>Syntax

```
protected:
   [member-list]
protected base-class
```

## <a name="remarks"></a>Açıklamalar

**`protected`** Anahtar sözcüğü, *üye listesindeki* sınıf üyelerine bir sonraki erişim tanımlayıcısına ( **`public`** veya **`private`** ) veya sınıf tanımının sonuna kadar erişimi belirtir. Olarak belirtilen sınıf üyeleri **`protected`** yalnızca şunlar tarafından kullanılabilir:

- Başlangıçta bu üyeleri bildiren sınıfın üye işlevleri.

- Başlangıçta bu üyeleri bildirilen sınıf arkadaşları.

- Başlangıçta bu üyeleri bildiren sınıftan genel veya korumalı erişimle türetilmiş sınıflar.

- Korumalı üyelere özel erişimi de olan, doğrudan özel olarak türetilmiş sınıflar.

Bir temel sınıfın adından önce, **`protected`** anahtar sözcüğü, temel sınıfın ortak ve korunan üyelerinin, türetilmiş sınıflarının korunan üyeleri olduğunu belirtir.

Korunan Üyeler **`private`** , yalnızca bildirildiği sınıfın üyeleri tarafından erişilebilen, ancak **`public`** herhangi bir işlevde erişilebilen üye olarak ortak olmayan üyeler olarak özel değildir.

Aynı zamanda olarak da belirtilen korumalı üyelere **`static`** , türetilmiş bir sınıfın herhangi bir arkadaşınız veya üye işleviyle erişilebilir. Olarak bildirilmemiş Korunan üyelere, türetilmiş bir **`static`** sınıftaki arkadaş ve üye işlevleri yalnızca türetilmiş sınıfın işaretçisi, başvuru veya nesne aracılığıyla erişilebilir.

İlgili bilgiler için, [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)içindeki [arkadaş](../cpp/friend-cpp.md), [genel](../cpp/public-cpp.md), [özel](../cpp/private-cpp.md)ve üye erişim tablosuna bakın.

## <a name="clr-specific"></a>/clr Özel

CLR türlerinde, C++ erişim belirtici anahtar sözcükleri ( **`public`** , **`private`** ve **`protected`** ) derlemelerle ilgili olarak türlerin ve yöntemlerin görünürlüğünü etkileyebilir. Daha fazla bilgi için bkz. [üye Access Control](member-access-control-cpp.md).

> [!NOTE]
> [/Ln](../build/reference/ln-create-msil-module.md) ile derlenen dosyalar bu davranıştan etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.

## <a name="end-clr-specific"></a>END /clr Özel

## <a name="example"></a>Örnek

```cpp
// keyword_protected.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
class X {
public:
   void setProtMemb( int i ) { m_protMemb = i; }
   void Display() { cout << m_protMemb << endl; }
protected:
   int  m_protMemb;
   void Protfunc() { cout << "\nAccess allowed\n"; }
} x;

class Y : public X {
public:
   void useProtfunc() { Protfunc(); }
} y;

int main() {
   // x.m_protMemb;         error, m_protMemb is protected
   x.setProtMemb( 0 );   // OK, uses public access function
   x.Display();
   y.setProtMemb( 5 );   // OK, uses public access function
   y.Display();
   // x.Protfunc();         error, Protfunc() is protected
   y.useProtfunc();      // OK, uses public access function
                        // in derived class
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
