---
title: protected (C++)
ms.date: 11/04/2016
f1_keywords:
- protected_cpp
helpviewer_keywords:
- protected keyword [C++], member access
- protected keyword [C++]
ms.assetid: 863d299f-fc0d-45d5-a1a7-bd24b7778a93
ms.openlocfilehash: 79ca081726c1f26a251763e2533ade730f075e2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317265"
---
# <a name="protected-c"></a>protected (C++)

## <a name="syntax"></a>Sözdizimi

```
protected:
   [member-list]
protected base-class
```

## <a name="remarks"></a>Açıklamalar

**Korumalı** anahtar kelime, *üye listesindeki* sınıf üyelerine bir sonraki erişim belirticisine **(ortak** veya **özel)** veya sınıf tanımının sonuna kadar erişim belirtir. **Korumalı** olarak bildirilen sınıf üyeleri yalnızca aşağıdakiler tarafından kullanılabilir:

- Başlangıçta bu üyeleri bildiren sınıfın üye işlevleri.

- Başlangıçta bu üyeleri bildirilen sınıf arkadaşları.

- Başlangıçta bu üyeleri bildiren sınıftan genel veya korumalı erişimle türetilmiş sınıflar.

- Korumalı üyelere özel erişimi de olan, doğrudan özel olarak türetilmiş sınıflar.

Bir taban sınıfın adından önce, **korumalı** anahtar kelime, taban sınıfın ortak ve korumalı üyelerinin türetilmiş sınıflarının korunan üyeleri olduğunu belirtir.

Korumalı üyeler, yalnızca beyan edildikleri sınıfın üyeleri tarafından erişilebilen **özel** üyeler kadar özel değildir, ancak herhangi bir işlevde erişilebilen kamu üyeleri kadar **genel** değildirler.

**Statik** olarak da bildirilen korumalı üyeler, türemiş bir sınıfın herhangi bir arkadaşı veya üye işlevi tarafından erişilebilir. **Statik** olarak bildirilmemiş korumalı üyeler, türemiş bir sınıftaki arkadaşlar ve üye işlevler için yalnızca türemiş sınıfın işaretçisi, başvurusu veya nesnesi aracılığıyla erişilebilir.

İlgili bilgiler için, [sınıf üyelerine erişimi denetlemede](member-access-control-cpp.md) [arkadaş,](../cpp/friend-cpp.md) [ortak,](../cpp/public-cpp.md) [özel](../cpp/private-cpp.md)ve üye erişim tablosuna bakın.

## <a name="clr-specific"></a>/clr Özel

CLR türlerinde, C++ erişim belirtici anahtar kelimeler **(genel,** **özel**ve **korumalı)** derlemelerle ilgili türlerin ve yöntemlerin görünürlüğünü etkileyebilir. Daha fazla bilgi için [Üye Erişim Denetimi'ne](member-access-control-cpp.md)bakın.

> [!NOTE]
> [/LN](../build/reference/ln-create-msil-module.md) ile derlenen dosyalar bu davranışdan etkilenmez. Bu durumda, tüm yönetilen sınıflar (ortak veya özel) görünür.

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

[Sınıf Üyelerine Erişimi Denetleme](member-access-control-cpp.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)
