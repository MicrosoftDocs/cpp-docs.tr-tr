---
title: Aşırı yükleme &lt; &lt; kendi sınıflarınız için işleci | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- operator<<, overloading for your own classes
- operator <<, overloading for your own classes
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5f5129be6ebf7cac336373f00c7f9e989c23489
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852539"
---
# <a name="overloading-the-ltlt-operator-for-your-own-classes"></a>Aşırı yükleme &lt; &lt; kendi sınıflarınız için işleci

Çıkış akışları ekleme kullanın (`<<`) standart türler için işleci. Ayrıca aşırı `<<` kendi sınıflarınız için işleci.

## <a name="example"></a>Örnek

`write` İşlevi örnek gösterdi kullanımını bir `Date` yapısı. Veri üyeleri (ay, gün ve yıl) bir görünümden gizli bir C++ sınıf için ideal bir aday tarihidir. Çıkış akışına böyle bir yapı görüntüleme için mantıksal hedefi değil. Bu kod kullanarak bir tarihi görüntüler `cout` nesnesi:

```cpp
Date dt(1, 2, 92);

cout <<dt;
```

Alınacak `cout` kabul etmek için bir `Date` nesne ekleme işleci sonra tanımak için ekleme işleci aşırı bir `ostream` nesneyi soldaki ve `Date` sağdaki. Aşırı yüklenmiş `<<` işleci işlevi bir sınıf arkadaş sonra bildirilmelidir `Date` içindeki özel verilere erişebilmesi için bir `Date` nesnesi.

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

Aşırı yüklenmiş işleci özgün bir başvuru döndürür `ostream` eklemeleri birleştirebilirsiniz anlamına gelir nesnesi:

```cpp
cout <<"The date is" <<dt <<flush;
```

## <a name="see-also"></a>Ayrıca bkz.

[Çıkış Akışları](../standard-library/output-streams.md)<br/>
