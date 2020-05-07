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

Bir işaretçi ve bir tamsayı içeren eklenebilir işlemler, yalnızca işaretçi işleneni bir dizi üyesini adresleyen ve tamsayı değeri aynı dizinin sınırları içinde bir konum üretirse anlamlı sonuçlar verir. Tamsayı değeri bir adres denkleine dönüştürüldüğünde, derleyici, özgün adres ve adres ile arasındaki fark ile aynı boyuttaki yalnızca bellek konumlarının bulunduğunu varsayar.

Bu varsayım dizi üyeleri için geçerlidir. Tanım olarak, bir dizi aynı türdeki bir değer dizisidir; öğeleri bitişik bellek konumlarında bulunur. Ancak, dizi öğeleri hariç her türlü tür için depolama, aynı tanımlayıcı türüyle doldurulacak garanti edilmez. Diğer bir deyişle, aynı türdeki konumlar dahil olmak üzere bellek konumları arasında boşluklar görünebilir. Bu nedenle, herhangi bir değerin adreslerine ekleme veya bunlardan çıkarma sonuçları, ancak dizi öğeleri tanımsızdır.

Benzer şekilde, iki işaretçi değeri çıkarıldığında, dönüştürme yalnızca aynı türdeki değerlerin boşluk olmadan, işlenen tarafından verilen adresler arasında olduğunu varsayar.

## <a name="see-also"></a>Ayrıca bkz.

[C eklenebilir Işleçler](../c-language/c-additive-operators.md)
