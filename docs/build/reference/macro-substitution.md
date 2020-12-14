---
description: 'Daha fazla bilgi edinin: makro değiştirme'
title: Makro Değiştirme
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
ms.openlocfilehash: 5e1531afb210b4671632bca2540bfc7562653139
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199187"
---
# <a name="macro-substitution"></a>Makro Değiştirme

*Makroadı* çağrıldığında, tanım dizesinde her bir *Dize1* oluşumu *dize2* ile değiştirilmiştir.

## <a name="syntax"></a>Syntax

```
$(macroname:string1=string2)
```

## <a name="remarks"></a>Açıklamalar

Makro değiştirme büyük/küçük harfe duyarlıdır ve değişmez değerdir; *Dize1* ve *dize2* makroları çağıramazsınız. Değiştirme özgün tanımı değiştirmez. Dışında herhangi bir önceden tanımlı makroya metin ekleyebilirsiniz [$$@](filename-macros.md) .

İki noktadan önce boşluk veya sekme yok; iki nokta üst üste, değişmez değer olarak yorumlanır. *Dize2* null ise, *Dize1* 'nin tüm oluşumları makronun tanım dizesinden silinir.

## <a name="see-also"></a>Ayrıca bkz.

[NMAKE makrosu kullanma](using-an-nmake-macro.md)
