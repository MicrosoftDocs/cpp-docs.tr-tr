---
title: İşaretçi Türlerine ve Türlerinden Dönüşümler
ms.date: 11/04/2016
helpviewer_keywords:
- pointers, converting
- conversions, pointer
- type casts, involving pointers
- void pointers
ms.assetid: 3facc56f-06d3-4570-b1a2-7d4927b83086
ms.openlocfilehash: 6358216e72f054becf33d18aadb6a3a51bab8363
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218903"
---
# <a name="conversions-to-and-from-pointer-types"></a>İşaretçi Türlerine ve Türlerinden Dönüşümler

Bir değer türünün işaretçisi, farklı türden bir işaretçiye dönüştürülebilir. Ancak sonuç, depolanan farklı türlerin hizalama gereksinimleri ve boyutları nedeniyle tanımlanmamış olabilir. Bir nesnenin işaretçisi, türü daha az katı veya eşit derecede katı olan depolama hizalaması gerektiren bir nesnenin işaretçisine dönüştürülebilir ve değiştirilmeden geri alınabilir.

Bir işaretçisi **`void`** , herhangi bir türe veya bir işaretçiye, hiçbir tür kısıtlaması veya kaybı olmadan dönüştürülebilir. Sonuç yeniden orijinal türüne dönüştürülürse, orijinal işaretçi kurtarılır.

Bir işaretçi aynı türden, ancak farklı veya ek niteleyicileri olan başka bir işaretçiye dönüştürülürse, yeni işaretçi yeni niteleyici tarafından uygulanan kısıtlamalar dışında eskisiyle aynı olur.

İşaretçi değeri, integral değerine de dönüştürülebilir. Dönüştürme yolu, aşağıdaki kurallara göre işaretçinin boyutuna ve integral türünün boyutuna bağlıdır:

- İşaretçinin boyutu integral türünün boyutundan büyük veya buna eşitse, işaretçi dönüştürme işleminde işaretsiz bir değer gibi görev alır, ancak bu değer gibi kayan bir değere dönüştürülemez.

- İşaretçi integral türünden küçükse, işaretçi önce integral türüyle aynı boyuttan bir işaretçiye, ardından integral türüne dönüştürülür.

Bunun tersi olarak, aşağıdaki kurallara göre bir integral türü işaretçi türüne dönüştürülebilir:

- İntegral türü işaretçi türüyle aynı boyuttaysa, dönüştürme işlemi integral değerinin bir işaretçi (işaretsiz tamsayı) olarak değerlendirilmesine neden olur.

- İntegral türünün boyutu işaretçi türünün boyutundan farklıysa, integral türü önce, [Işaretli Integral türlerinden](../c-language/conversions-from-signed-integral-types.md) ve [Işaretsiz integral türlerden dönüşümden](../c-language/conversions-from-unsigned-integral-types.md)gelen tablolarda verilen dönüştürme yolları kullanılarak işaretçinin boyutuna dönüştürülür. Daha sonra bir işaretçi değeri olarak kabul edilir.

Değer 0 olan veya tür ifade türüne sahip bir integral sabit ifadesi **`void`** <strong>\*</strong> bir tür atama, atamaya göre veya herhangi bir tür işaretçisine karşılaştırmaya göre dönüştürülebilir. Bu, aynı türden başka bir null işaretçisine eşit olan bir null işaretçisi oluşturur, ancak bu null işaretçisi bir işlevin veya nesnenin herhangi bir işaretçisine eşit değildir. 0 sabiti dışındaki tamsayılar işaretçi türüne dönüştürülebilir, ancak sonuç taşınabilir değildir.

## <a name="see-also"></a>Ayrıca bkz.

[Atama dönüştürmeleri](../c-language/assignment-conversions.md)
