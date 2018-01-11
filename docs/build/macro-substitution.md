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
ms.workload: cplusplus
ms.openlocfilehash: 7c2ea7a2509e58cfd4da163cc76c018d06c244fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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