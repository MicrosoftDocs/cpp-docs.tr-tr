---
description: 'Hakkında daha fazla bilgi edinin: &lt; &lt; kendi sınıflarınız Için Işleci aşırı yükleme'
title: '&lt; &lt; Kendi sınıflarınız için işleci aşırı yükleme'
ms.date: 11/04/2016
helpviewer_keywords:
- operator<<, overloading for your own classes
- operator <<, overloading for your own classes
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
ms.openlocfilehash: 206d6ccb50c7cb3706c66adeb6c1429a04775fc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340846"
---
# <a name="overloading-the-ltlt-operator-for-your-own-classes"></a>&lt; &lt; Kendi sınıflarınız için işleci aşırı yükleme

Çıkış akışları `<<` standart türler için ekleme () işlecini kullanır. Ayrıca `<<` kendi sınıflarınız için işlecini aşırı yükleyebilirsiniz.

## <a name="example"></a>Örnek

`write`İşlev örneği bir yapının kullanımını gösterdi `Date` . Tarih, veri üyelerinin (ay, gün ve yıl) görünümden gizlendiği C++ sınıfı için ideal bir adaydır. Çıkış akışı, böyle bir yapıyı görüntülemek için mantıksal hedefdir. Bu kod, nesnesini kullanarak bir tarih görüntüler `cout` :

```cpp
Date dt(1, 2, 92);

cout <<dt;
```

`cout` `Date` Ekleme işlecinden sonra bir nesneyi kabul etmek için, `ostream` sol ve sağ taraftaki bir nesneyi tanımak üzere ekleme işlecini aşırı yükleme `Date` . Aşırı yüklenmiş `<<` işleç işlevi, `Date` bir nesne içindeki özel verilere erişebilmeleri için sınıfın bir arkadaşınız olarak bildirilmelidir `Date` .

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

Aşırı yüklenmiş operatör özgün nesneye bir başvuru döndürür; `ostream` Bu, eklemeleri birleştirebileceğiniz anlamına gelir:

```cpp
cout <<"The date is" <<dt <<flush;
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış akışları](../standard-library/output-streams.md)
