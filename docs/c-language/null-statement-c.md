---
title: Null Statement (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- semicolon, C null statement
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 72e120fa412481a8313809bd5cdaf748de498bde
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="null-statement-c"></a>Boş Deyim (C)
Bir "boş deyimi", yalnızca noktalı virgül içeren bir deyimdir; bir deyimin olabileceği yerlerde görünebilir. Boş bir deyimi yürütüldüğünde, hiçbir şey olmaz. Boş bir deyimi doğru şekilde kodlamanın yolu aşağıda gösterilmiştir:  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
;  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Gibi ifadelerini **yapmak**, **için**, **varsa**, ve `while` yürütülebilir bir deyimi deyimi gövdesi olarak yer gerektirir. Boş deyim, substantive deyim gövdesini gerekmeyen durumlarda sözdizimi koşullarını karşılar.  
  
 Diğer C deyimlerinde olduğu gibi, boş bir deyimden önce etiket ekleyebilirsiniz. Deyim olmayan bir öğeyi (örneğin, bileşik bir deyimin kapanış ayracı) etiketlemek için, boş bir deyimi etiketleyebilir ve aynı etkiyi görmek için onu hemen öğeden önce ekleyebilirsiniz.  
  
 Bu örnekte boş deyimi gösterilmektedir:  
  
```  
for ( i = 0; i < 10; line[i++] = 0 )  
     ;  
```  
  
 Bu örnekte, döngü bir ifade **için** deyimi `line[i++] = 0` ilk 10 öğelerini başlatır `line` 0. Deyim gövdesi boş bir deyimdir çünkü başka bir deyim gerekli değildir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Deyimler](../c-language/statements-c.md)