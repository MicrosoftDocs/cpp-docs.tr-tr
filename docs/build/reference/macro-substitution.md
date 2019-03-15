---
title: Makro Değiştirme
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: 43dc9133c53b1c436c0df8c3db66ae8f18604222
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824046"
---
# <a name="macro-substitution"></a>Makro Değiştirme

Zaman *makroadı* çağrılır, her geçtiği *Dize1* tanımında dize ile değiştirilir *dize2*.

## <a name="syntax"></a>Sözdizimi

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>Açıklamalar

Makro değiştirme büyük/küçük harfe duyarlıdır ve sabitidir. *Dize1* ve *dize2* makroları çağrılamaz. Orijinal tanımını değiştirme değiştirmez. Dışında herhangi bir önceden tanımlanmış makro metinde değiştirebildiği [ $$@ ](filename-macros.md).

Boşluk veya sekme iki nokta üst üste koyun; herhangi iki noktadan sonra değişmez değer olarak yorumlanır. Varsa *dize2* null, tüm oluşumlarını olan *Dize1* makro tanımı dizeden silinir.

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE Makrosu Kullanma](using-an-nmake-macro.md)
