---
title: Aşırı yükleme &lt; &lt; kendi işleci
ms.date: 11/04/2016
helpviewer_keywords:
- operator<<, overloading for your own classes
- operator <<, overloading for your own classes
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
ms.openlocfilehash: 290491f7afb22873d60abb6662b470d8e7abefc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486937"
---
# <a name="overloading-the-ltlt-operator-for-your-own-classes"></a>Aşırı yükleme &lt; &lt; kendi işleci

Çıkış akışları ekleme kullanın (`<<`) standart türler için işleci. Ayrıca aşırı `<<` kendi işleci.

## <a name="example"></a>Örnek

`write` İşlevi örnek kullanımını gösteriyordu bir `Date` yapısı. Veri üyeleri (ay, gün ve yıl) görünümünden gizlenen bir C++ sınıfı için ideal bir aday tarihtir. Böyle bir yapı görüntülemek için mantıksal hedef bir çıkış akışıdır. Bu kod kullanarak bir tarih görüntüler `cout` nesnesi:

```cpp
Date dt(1, 2, 92);

cout <<dt;
```

Almak için `cout` kabul etmek için bir `Date` tanımak için ekleme İşleç aşırı yüklemesi, nesne ekleme işleçten sonra bir `ostream` soldaki nesnesi ve bir `Date` sağ. Aşırı yüklenen `<<` işleç işlevini ardından bildirilmiş bir sınıfın arkadaş `Date` içinde özel verilere erişebilmek için bir `Date` nesne.

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

Aşırı yüklenmiş işleç özgün bir başvuru döndürür `ostream` nesne eklemeler birleştirebilirsiniz anlamına gelir:

```cpp
cout <<"The date is" <<dt <<flush;
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
