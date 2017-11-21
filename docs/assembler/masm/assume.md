---
title: VARSAYIN | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ASSUME
dev_langs: C++
helpviewer_keywords: ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6046d19e628e75dee6e3f33b400c48dcbf317735
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="assume"></a>ASSUME
YAZMAÇ değerlerini denetlenirken hata sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
ASSUME segregister:name [[, segregister:name]]...  
ASSUME dataregister:type [[, dataregister:type]]...  
ASSUME register:ERROR [[, register:ERROR]]...  
ASSUME [[register:]] NOTHING [[, register:NOTHING]]...  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sonra bir `ASSUME` derleyici verilen yazmaçlar değerlerine değişiklikleri izleyen yürürlüğe, koymak. **HATA** kayıt kullanılıyorsa bir hata oluşturur. **Hiçbir şey** kaldırır kaydetmek hata denetimi. Farklı türde bir deyiminde varsayımlar birleştirebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler başvurusu](../../assembler/masm/directives-reference.md)