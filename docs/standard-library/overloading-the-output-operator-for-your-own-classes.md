---
title: Kendi sınıflarınız için işleci aşırı yükleme &lt; &lt;
ms.date: 11/04/2016
helpviewer_keywords:
- operator<<, overloading for your own classes
- operator <<, overloading for your own classes
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
ms.openlocfilehash: c470bb7335a5997ae26327f99b8c5f31d20b4edb
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452060"
---
# <a name="overloading-the-ltlt-operator-for-your-own-classes"></a>Kendi sınıflarınız için işleci aşırı yükleme &lt; &lt;

Çıkış akışları standart türler için ekleme`<<`() işlecini kullanır. Ayrıca kendi sınıflarınız için `<<` işlecini aşırı yükleyebilirsiniz.

## <a name="example"></a>Örnek

İşlev örneği bir `Date` yapının kullanımını gösterdi. `write` Tarih, veri üyelerinin (ay, gün C++ ve yıl) görünümden gizlendiği bir sınıf için ideal bir adaydır. Çıkış akışı, böyle bir yapıyı görüntülemek için mantıksal hedefdir. Bu kod, `cout` nesnesini kullanarak bir tarih görüntüler:

```cpp
Date dt(1, 2, 92);

cout <<dt;
```

Ekleme işlecinden sonra bir `Date` nesneyi kabul `ostream` `Date` etmek için, sol ve sağ taraftaki bir nesneyi tanımak üzere ekleme işlecini aşırı yükleme. `cout` Aşırı yüklenmiş `<<` işleç işlevi, bir `Date` nesne içindeki özel verilere erişebilmeleri için sınıfın `Date` bir arkadaşınız olarak bildirilmelidir.

```cpp
// overload_date.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

class Date
{
    int mo, da, yr;
public:
    Date(int m, int d, int y)
    {
        mo = m; da = d; yr = y;
    }
    friend ostream& operator<<(ostream& os, const Date& dt);
};

ostream& operator<<(ostream& os, const Date& dt)
{
    os << dt.mo << '/' << dt.da << '/' << dt.yr;
    return os;
}

int main()
{
    Date dt(5, 6, 92);
    cout << dt;
}
```

```Output
5/6/92
```

## <a name="remarks"></a>Açıklamalar

Aşırı yüklenmiş operatör özgün `ostream` nesneye bir başvuru döndürür; bu, eklemeleri birleştirebileceğiniz anlamına gelir:

```cpp
cout <<"The date is" <<dt <<flush;
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)
