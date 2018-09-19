---
title: Maksimum dize uzunluğu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- lengths, strings
- string length, maximum
- maximum string length
- strings [C++], length
ms.assetid: 99a80e4a-6212-47b7-a6bd-bdf99bd44928
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82bf6ef1f868ee182d3bef038ba87b07e85419db
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095554"
---
# <a name="maximum-string-length"></a>Maksimum Dize Uzunluğu

**Microsoft'a özgü**

ANSI uyumluluğu birleştirme sonra bir dize sabit değerinde en fazla 509 karakterleri kabul etmek için bir derleyici gerektirir. Microsoft C'de izin verilen uzunluk dize sabitinin yaklaşık 2.048 bayttır. Ancak, dize sabit değeri çift tırnak işareti içine alınmış bölümlerinin oluşuyorsa, önişlemci bölümleri tek bir dize olarak sıralar ve birleştirilmiş her satır için fazladan bir bayt toplam bayt sayısı ekler.

Örneğin, bir dize olan 40 satır satır (2.000 karakter) başına 50 karakterden oluşur ve 7 karakter içeren bir satır ve her satır çift tırnak işaretleri arasına varsayalım. Bu kadar 2.007 bayt artı tek baytlık 2,008 bayt toplam sondaki null karakter ekler. Birleştirme üzerinde bir ek karakter her ilk 40 satırlar eklenir. Bu, 2.048 bayt toplam hale getirir. Not, ancak devamlılıklar satır olması durumunda (\\) kullanılan yerine çift tırnak işareti, önişlemcinin her satır için bir ek karakter eklemez.

Sınırlandırılmış bir kişi 2048 bayttan daha uzun olamaz, ancak bir dize sabit değeri kabaca 65535 bayt dizeleri birleştirerek oluşturulabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C Dize Değişmez Değerleri](../c-language/c-string-literals.md)