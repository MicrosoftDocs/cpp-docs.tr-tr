---
description: 'Daha fazla bilgi: en fazla dize uzunluğu'
title: Maksimum Dize Uzunluğu
ms.date: 11/04/2016
helpviewer_keywords:
- lengths, strings
- string length, maximum
- maximum string length
- strings [C++], length
ms.assetid: 99a80e4a-6212-47b7-a6bd-bdf99bd44928
ms.openlocfilehash: 1da7618a044be2427bd0b0f7f4931287ee4b8014
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243438"
---
# <a name="maximum-string-length"></a>Maksimum Dize Uzunluğu

**Microsoft'a Özgü**

ANSI uyumluluğu, bir derleyicinin birleştirme sonrasında bir dize sabit değerinde en fazla 509 karakter kabul etmesini gerektirir. Microsoft C 'de izin verilen bir dize sabit değerinin en fazla uzunluğu yaklaşık 2.048 bayttır. Ancak, dize sabiti çift tırnak işareti içine alınmış bölümlerden oluşuyorsa, ön işlemci parçaları tek bir dizeye ekler ve birleştirilmiş her satır için toplam bayt sayısına ek bir bayt ekler.

Örneğin, bir dize, her satır için 50 karakter (2.000 karakter) ve bir satır 7 karakter içeren 40 satırdan oluşur ve her satır çift tırnak işareti içine alınmalıdır. Bu, toplam 2.008 bayt için en fazla 2.007 bayt ve Sonlandırıcı null karakteri için bir bayt ekler. Birleştirme sırasında, ilk 40 satırın her biri için ek bir karakter eklenir. Bu, toplam 2.048 baytlık bir işlem yapar. Ancak, çift tırnak işareti yerine satır devamlılıkları ( \\ ) kullanılırsa, Önişlemci her satır için ek bir karakter eklemez.

Tek tırnaklı bir dize 2048 bayttan daha uzun olamaz, bu da kabaca 65535 baytlık bir dize sabit değeri birleştirerek dizeler oluşturulabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C dize değişmez değerleri](../c-language/c-string-literals.md)
