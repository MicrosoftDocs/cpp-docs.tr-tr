---
title: Aşırı yükleme &gt; &gt; kendi işleci
ms.date: 11/04/2016
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
ms.openlocfilehash: 86b8af963345c8eb9b3f44cfb16332bc09420bf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370729"
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>Aşırı yükleme &gt; &gt; kendi işleci

Giriş akışları ayıklama kullanın (`>>`) işleci standart türleri için. Kendi türlerinizi için benzer ayıklama işleçlerini yazabilirsiniz; başarınız, boşluk tam olarak kullanarak bağlıdır.

İşte bir örnek için bir çıkarma işleci `Date` sınıfı sunulan daha önce:

```cpp
istream& operator>> (istream& is, Date& dt)
{
    is>> dt.mo>> dt.da>> dt.yr;
    return is;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)<br/>
