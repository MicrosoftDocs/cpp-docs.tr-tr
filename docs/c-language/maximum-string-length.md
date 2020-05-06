---
title: Maksimum Dize Uzunluğu
ms.date: 11/04/2016
helpviewer_keywords:
- lengths, strings
- string length, maximum
- maximum string length
- strings [C++], length
ms.assetid: 99a80e4a-6212-47b7-a6bd-bdf99bd44928
ms.openlocfilehash: 650088249e4c6abd515c29b873a9f09dc1d2a60a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232884"
---
# <a name="maximum-string-length"></a>Maksimum Dize Uzunluğu

**Microsoft'a Özgü**

ANSI uyumluluğu, bir derleyicinin birleştirme sonrasında bir dize sabit değerinde en fazla 509 karakter kabul etmesini gerektirir. Microsoft C 'de izin verilen bir dize sabit değerinin en fazla uzunluğu yaklaşık 2.048 bayttır. Ancak, dize sabiti çift tırnak işareti içine alınmış bölümlerden oluşuyorsa, ön işlemci parçaları tek bir dizeye ekler ve birleştirilmiş her satır için toplam bayt sayısına ek bir bayt ekler.

Örneğin, bir dize, her satır için 50 karakter (2.000 karakter) ve bir satır 7 karakter içeren 40 satırdan oluşur ve her satır çift tırnak işareti içine alınmalıdır. Bu, toplam 2.008 bayt için en fazla 2.007 bayt ve Sonlandırıcı null karakteri için bir bayt ekler. Birleştirme sırasında, ilk 40 satırın her biri için ek bir karakter eklenir. Bu, toplam 2.048 baytlık bir işlem yapar. Ancak, çift tırnak işareti yerine satır devamlılıkları\\() kullanılırsa, Önişlemci her satır için ek bir karakter eklemez.

Tek tırnaklı bir dize 2048 bayttan daha uzun olamaz, bu da kabaca 65535 baytlık bir dize sabit değeri birleştirerek dizeler oluşturulabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Dize Değişmez Değerleri](../c-language/c-string-literals.md)
