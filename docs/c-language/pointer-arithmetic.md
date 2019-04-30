---
title: İşaretçi Aritmetiği
ms.date: 11/04/2016
helpviewer_keywords:
- pointer arithmetic
- arithmetic pointer
ms.assetid: eb924a29-59d3-48a5-9d62-9424790730eb
ms.openlocfilehash: c1b3e31561bedece6a6180fbeb13473153a46ab6
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343134"
---
# <a name="pointer-arithmetic"></a>İşaretçi Aritmetiği

Bir işaretçi ve tamsayı içeren eklenebilir işlemler, yalnızca işaretçi işlenen bir dizi üyesini giderir ve bir uzaklık aynı dizi sınırları içindeki tamsayı değerini üretir anlamlı sonuçlar verir. Tamsayı değeri adresi uzaklık dönüştürüldüğünde, derleyici bellek konumları aynı boyutta yalnızca özgün adresini ve adresini artı uzaklık arasında kalan varsayar.

Bu varsayımı dizi üyeleri için geçerlidir. Tanımı gereği, dizi bir dizi değer aynı türde olması; öğeleri bitişik bellek konumlarda yer alır. Ancak, dizi öğelerinin dışında tüm türler için depolama tanımlayıcıları aynı türde tarafından doldurulacak garanti edilmez. Diğer bir deyişle, boşluklar bile konumları aynı tür bellek konumları arasında görünür. Bu nedenle, tüm değerleri ancak dizi öğelerine adreslerinden çıkararak veya ekleyerek, sonuçlar tanımsızdır.

Benzer şekilde, iki işaretçi değerleri çıkartılır, dönüştürme yalnızca boşluk yok'ile aynı türde değerler tarafından işlenen verilen adresleri arasında kalan varsayar.

## <a name="see-also"></a>Ayrıca bkz.

[C Ek İşleçleri](../c-language/c-additive-operators.md)
