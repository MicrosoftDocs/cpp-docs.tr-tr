---
title: Çıkarma (-)
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], subtraction
- subtraction operator, syntax
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
ms.openlocfilehash: 5c9510cf3708ef049b5dac213fa3de894fcd4a07
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56147613"
---
# <a name="subtraction--"></a>Çıkarma (-)

Çıkarma işleci (**-**) ikinci işlenen ilk çıkarır. Her iki işlenen de tamsayı veya kayan türler olabilir veya tek bir işlenen bir işaretçi ve diğer bir tamsayı olabilir.

İki işaretçileri çıkartılır, fark imzalı bir tamsayı değer türünde bir değer boyutu tarafından fark bölerek dönüştürülür, işaretçiler adresi. İntegral değerinin boyutu türü tarafından tanımlanan **ptrdiff_t** STDDEF içinde standart içerme dosyası. H Sonuç, bellek konumları arasında iki adres türü sayısını temsil eder. Sonuç yalnızca içinde açıklandığı gibi aynı iki öğe için anlamlı olması garanti [işaretçi aritmetiği](../c-language/pointer-arithmetic.md).

Bir işaretçi değeri bir tamsayı değeri çıkarılır, tamsayı değeri çıkarma işleci dönüştürür (*miyim*) boyutunu ele alan bir işaretçi değeri tarafından çarpmadan tarafından. Dönüştürme işleminden sonra temsil eder bir tamsayı değeri *miyim* her konum işaretçi türü tarafından belirtilen uzunluğa sahip olduğu, bellek konumları. Dönüştürülmüş tamsayı değeri çıkarılan işaretçi değer, bellek adresi sonucudur *miyim* özgün adresini önce konumları. Yeni İşaretçi, orijinal işaretçi değeri tarafından ele alınan değerini işaret eder.

## <a name="see-also"></a>Ayrıca bkz.

[C Ek İşleçleri](../c-language/c-additive-operators.md)
