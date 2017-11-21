---
title: YEREL (MASM) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Local
dev_langs: C++
helpviewer_keywords: LOCAL directive
ms.assetid: 76147e2d-23ca-4f1e-8817-81428becd113
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 60dac02a5bf08f7ced2fbb8adb46cc558cbfe44b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="local-masm"></a>LOCAL (MASM)
Makro içinde ilk yönergesinde **yerel** makrosu her örneği için benzersiz etiketleri tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      LOCAL localname [[, localname]]...  
LOCAL label [[ [count ] ]] [[:type]] [[, label [[ [count] ]] [[type]]]]...  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir yordamı tanımı içinde ikinci yönergesi (**PROC**), **yerel** yordam boyunca mevcut yığın tabanlı değişkenleri oluşturur. *Etiket* basit bir değişken veya bir dizi içeren olabilir *sayısı* öğeleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler başvurusu](../../assembler/masm/directives-reference.md)