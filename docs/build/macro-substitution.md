---
title: "Makro değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, macro substitution
- macros, NMAKE
- substitution macros in NMAKE
ms.assetid: 47465cfe-fd92-49db-aebe-7c2d7ecceb73
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8e63e071629c2647ccd8f89095fbc7c2285f1a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [NMAKE makrosu kullanma](../build/using-an-nmake-macro.md)