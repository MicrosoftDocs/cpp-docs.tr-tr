---
description: 'Daha fazla bilgi edinin: Işaretçi aritmetiği'
title: İşaretçi Aritmetiği
ms.date: 11/04/2016
helpviewer_keywords:
- pointer arithmetic
- arithmetic pointer
ms.assetid: eb924a29-59d3-48a5-9d62-9424790730eb
ms.openlocfilehash: 37ee9fd696f874d1faa84b5d656317cf67f75a6c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243126"
---
# <a name="pointer-arithmetic"></a>İşaretçi Aritmetiği

Bir işaretçi ve bir tamsayı içeren eklenebilir işlemler, yalnızca işaretçi işleneni bir dizi üyesini adresleyen ve tamsayı değeri aynı dizinin sınırları içinde bir konum üretirse anlamlı sonuçlar verir. Tamsayı değeri bir adres denkleine dönüştürüldüğünde, derleyici, özgün adres ve adres ile arasındaki fark ile aynı boyuttaki yalnızca bellek konumlarının bulunduğunu varsayar.

Bu varsayım dizi üyeleri için geçerlidir. Tanım olarak, bir dizi aynı türdeki bir değer dizisidir; öğeleri bitişik bellek konumlarında bulunur. Ancak, dizi öğeleri hariç her türlü tür için depolama, aynı tanımlayıcı türüyle doldurulacak garanti edilmez. Diğer bir deyişle, aynı türdeki konumlar dahil olmak üzere bellek konumları arasında boşluklar görünebilir. Bu nedenle, herhangi bir değerin adreslerine ekleme veya bunlardan çıkarma sonuçları, ancak dizi öğeleri tanımsızdır.

Benzer şekilde, iki işaretçi değeri çıkarıldığında, dönüştürme yalnızca aynı türdeki değerlerin boşluk olmadan, işlenen tarafından verilen adresler arasında olduğunu varsayar.

## <a name="see-also"></a>Ayrıca bkz.

[C eklenebilir Işleçler](../c-language/c-additive-operators.md)
