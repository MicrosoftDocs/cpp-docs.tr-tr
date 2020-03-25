---
title: protected (C++)
ms.date: 11/04/2016
f1_keywords:
- protected_cpp
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
ms.openlocfilehash: 29f57eac7201ac0647275c70c539f9b2f28eb81b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179256"
---
# <a name="protected-c"></a>protected (C++)

## <a name="syntax"></a>Sözdizimi

```
protected:
   [member-list]
protected base-class
```

## <a name="remarks"></a>Açıklamalar

**Protected** anahtar sözcüğü, *üye listesindeki* sınıf üyelerine bir sonraki erişim tanımlayıcısına (**genel** veya **özel**) veya sınıf tanımının sonuna kadar erişimi belirtir. **Korumalı** olarak belirtilen sınıf üyeleri yalnızca şunlar tarafından kullanılabilir:

- Başlangıçta bu üyeleri bildiren sınıfın üye işlevleri.

- Başlangıçta bu üyeleri bildirilen sınıf arkadaşları.

- Başlangıçta bu üyeleri bildiren sınıftan genel veya korumalı erişimle türetilmiş sınıflar.

- Korumalı üyelere özel erişimi de olan, doğrudan özel olarak türetilmiş sınıflar.

Bir temel sınıfın adından önce, **Protected** anahtar sözcüğü, temel sınıfın ortak ve korunan üyelerinin, türetilmiş sınıflarının korunan üyeleri olduğunu belirtir.

Korunan Üyeler, yalnızca bildirildiği sınıfın üyeleri tarafından erişilebilen **özel** Üyeler olarak özel değildir, ancak bu, herhangi bir işlevde erişilebilen **ortak** Üyeler olarak genel olarak değildir.

**Statik** olarak da belirtilen korumalı üyelere, türetilmiş bir sınıfın herhangi bir arkadaşınız veya member işlevi erişebilir. **Statik** olarak bildirilmeyen Korunan üyelere, türetilmiş bir sınıftaki arkadaş ve üye işlevleri yalnızca türetilmiş sınıfın işaretçisi, başvuru veya nesne aracılığıyla erişilebilir.

İlgili bilgiler için, [sınıf üyelerine erişimi denetleme](member-access-control-cpp.md)içindeki [arkadaş](../cpp/friend-cpp.md), [genel](../cpp/public-cpp.md), [özel](../cpp/private-cpp.md)ve üye erişim tablosuna bakın.

## <a name="clr-specific"></a>/clr Özel

C++ CLR türlerinde, erişim belirleyicisi anahtar sözcükleri (**genel**, **özel**ve **korumalı**) derlemelerle ilgili olarak türlerin ve yöntemlerin görünürlüğünü etkileyebilir. Daha fazla bilgi için bkz. [üye Access Control](member-access-control-cpp.md).

> [!NOTE]
>  [/Ln](../build/reference/ln-create-msil-module.md) ile derlenen dosyalar bu davranıştan etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.

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
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
