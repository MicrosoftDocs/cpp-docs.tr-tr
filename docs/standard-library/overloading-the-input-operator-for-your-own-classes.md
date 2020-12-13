---
description: 'Hakkında daha fazla bilgi edinin: &gt; &gt; kendi sınıflarınız Için Işleci aşırı yükleme'
title: '&gt; &gt; Kendi sınıflarınız için işleci aşırı yükleme'
ms.date: 11/04/2016
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
ms.openlocfilehash: 4de7c16dd1c42f85f169da50f11a514eb245b47c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340859"
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>&gt; &gt; Kendi sınıflarınız için işleci aşırı yükleme

Giriş akışları `>>` , standart türler için ayıklama () işlecini kullanır. Kendi türlerinizin benzer ayıklama işleçleri yazabilirsiniz; başarınız, tam olarak boşluk kullanılmasına bağlıdır.

Daha önce sunulan sınıf için bir ayıklama işleci örneği aşağıda verilmiştir `Date` :

```cpp
istream& operator>> (istream& is, Date& dt)
{
    is>> dt.mo>> dt.da>> dt.yr;
    return is;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Giriş akışları](../standard-library/input-streams.md)
