---
title: "C boyutlu tamsayı türleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: sized integer types
ms.assetid: 0d6199b4-d0ab-4e8c-a769-785f5afb92eb
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 101c8facb8871d814d1a1ea05c2856d3105a8bfc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="c-sized-integer-types"></a>C Boyutlu Tamsayı Türleri
**Microsoft özel**  
  
 Microsoft C, boyutlandırılmış tamsayı türleri için destek sağlar. __İnt kullanarak 8 - 16-, 32 veya 64 bit tamsayı değişkenleri bildirebilirsiniz *n*  tür tanımlayıcısı, burada  *n*  tamsayı değişken bit cinsinden boyutu. Değeri  *n*  8, 16, 32 veya 64 olabilir. Aşağıdaki örnekte, boyutlandırılmış tamsayıların dört türünün her biri için bir değişken bildirilmektedir:  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Boyutlandırılmış tamsayıların ilk üç türü, aynı boyuta sahip ANSI türleri için eş anlamlıdır ve birden fazla platformda aynı şekilde davranan taşınabilir kod yazmak için yararlıdır. Tür char ile __int8 veri türü eşanlamlıdır Not \__int16 kısa, türüyle eşanlamlı ve \__int32 türü tamsayı ile eşanlamlı \__İnt64 türünde hiçbir eşdeğer ANSI karşılık gelen.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel türleri depolama](../c-language/storage-of-basic-types.md)