---
description: 'Daha fazla bilgi edinin: çıkarma (-)'
title: Çıkarma (-)
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], subtraction
- subtraction operator, syntax
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
ms.openlocfilehash: 8e0daf4e1bfdbb844df99e3f79dc2baf5a30e6e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114565"
---
# <a name="subtraction--"></a>Çıkarma (-)

Çıkarma işleci ( **-** ) birinciden ikinci işleneni çıkartır. Her iki işlenen de İntegral veya kayan türler olabilir ya da bir işlenen bir işaretçi ve diğeri tamsayı olabilir.

İki işaretçi çıkarıldığında, fark, işaret adresinin bir değer boyutuna göre farkı ayırarak imzalı bir integral değerine dönüştürülür. İntegral değerin boyutu, standart içerme dosyası STDDEF. H içinde **ptrdiff_t** tür tarafından tanımlanır. Sonuç, iki adres arasındaki bu türdeki bellek konumlarının sayısını temsil eder. Sonuç, [Işaretçi aritmetik](../c-language/pointer-arithmetic.md)bölümünde anlatıldığı gibi, yalnızca aynı dizinin iki öğesi için anlamlı olması garanti edilir.

Bir tamsayı değeri bir işaretçi değerinden çıkarıldığında, çıkarma işleci değeri, işaretçinin adresleyen değerin boyutuyla çarparak tamsayı değerini (*i*) dönüştürür. Dönüştürmeden sonra, tamsayı değeri *i* bellek konumlarını temsil eder; burada her konum işaretçi türü tarafından belirtilen uzunluğa sahiptir. Dönüştürülen tamsayı değeri işaretçi değerinden çıkarıldığında, sonuç, özgün adresten önceki *Konumlarım* olan bellek adresidir. Yeni işaretçi, orijinal işaretçi değeri tarafından belirtilen türde bir değere işaret eder.

## <a name="see-also"></a>Ayrıca bkz.

[C eklenebilir Işleçler](../c-language/c-additive-operators.md)
