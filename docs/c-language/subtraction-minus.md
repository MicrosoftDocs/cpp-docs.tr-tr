---
title: Çıkarma (-)
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C], subtraction
- subtraction operator, syntax
ms.assetid: 9cacba7d-20b3-4372-8a63-ba5d8ee64177
ms.openlocfilehash: 5c9510cf3708ef049b5dac213fa3de894fcd4a07
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157766"
---
# <a name="subtraction--"></a>Çıkarma (-)

Çıkarma işleci (**-**) birinciden ikinci işleneni çıkartır. Her iki işlenen de İntegral veya kayan türler olabilir ya da bir işlenen bir işaretçi ve diğeri tamsayı olabilir.

İki işaretçi çıkarıldığında, fark, işaret adresinin bir değer boyutuna göre farkı ayırarak imzalı bir integral değerine dönüştürülür. İntegral değerin boyutu, standart içerme dosyası STDDEF içindeki **ptrdiff_t** türü tarafından tanımlanır. Olsun. Sonuç, iki adres arasındaki bu türdeki bellek konumlarının sayısını temsil eder. Sonuç, [Işaretçi aritmetik](../c-language/pointer-arithmetic.md)bölümünde anlatıldığı gibi, yalnızca aynı dizinin iki öğesi için anlamlı olması garanti edilir.

Bir tamsayı değeri bir işaretçi değerinden çıkarıldığında, çıkarma işleci değeri, işaretçinin adresleyen değerin boyutuyla çarparak tamsayı değerini (*i*) dönüştürür. Dönüştürmeden sonra, tamsayı değeri *i* bellek konumlarını temsil eder; burada her konum işaretçi türü tarafından belirtilen uzunluğa sahiptir. Dönüştürülen tamsayı değeri işaretçi değerinden çıkarıldığında, sonuç, özgün adresten önceki *Konumlarım* olan bellek adresidir. Yeni işaretçi, orijinal işaretçi değeri tarafından belirtilen türde bir değere işaret eder.

## <a name="see-also"></a>Ayrıca bkz.

[C eklenebilir Işleçler](../c-language/c-additive-operators.md)
