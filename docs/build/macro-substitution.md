---
title: Makro değiştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4028ee710cf38b6a4ef929de9a7e4ffad95f3e41
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="macro-substitution"></a>Makro Değiştirme
Zaman *makroadı* çağrılır, her oluşumu *Dize1* , tanımında dize ile değiştirilir *dize2*.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
$(macroname:string1=string2)  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Makro değiştirme büyük küçük harfe duyarlıdır ve değişmez değer; *Dize1* ve *dize2* makroları çağrılamıyor. Değiştirme orijinal tanımını değiştirmez. Önceden tanımlanmış tüm makrosu dışında metinde yerine [ $$@ ](../build/filename-macros.md).  
  
 Hiçbir boşluk ya da sekme iki nokta üst üste koyun; herhangi iki nokta üst üste sonra sabit değer olarak yorumlanır. Varsa *dize2* null, tüm oluşumlarını olan *Dize1* makro tanımı dizeden silinir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [NMAKE Makrosu Kullanma](../build/using-an-nmake-macro.md)