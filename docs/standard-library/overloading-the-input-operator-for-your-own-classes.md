---
title: Kendi sınıflarınız için işleci aşırı yükleme &gt; &gt;
ms.date: 11/04/2016
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
ms.openlocfilehash: 672dfb7ec40b2f18cbde0adc92522d3194a5e738
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450133"
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>Kendi sınıflarınız için işleci aşırı yükleme &gt; &gt;

Giriş akışları, standart türler için`>>`ayıklama () işlecini kullanır. Kendi türlerinizin benzer ayıklama işleçleri yazabilirsiniz; başarınız, tam olarak boşluk kullanılmasına bağlıdır.

Daha önce sunulan `Date` sınıf için bir ayıklama işleci örneği aşağıda verilmiştir:

```cpp
istream& operator>> (istream& is, Date& dt)
{
    is>> dt.mo>> dt.da>> dt.yr;
    return is;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Giriş Akışları](../standard-library/input-streams.md)
