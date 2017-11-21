---
title: ". EĞER | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .IF
dev_langs: C++
helpviewer_keywords: .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2416b73fa42f9cac629644ea624a9545f3988dc3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="if"></a>.IF
Testleri kod oluşturur `condition1` (örneğin, AX > 7) ve yürütür *deyimleri* bu koşulun doğru olması durumunda.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
   .IF condition1   
statements  
[[.ELSEIF condition2   
   statements]]  
[[.ELSE  
   statements]]  
.ENDIF  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa bir [. ELSE](../../assembler/masm/dot-else.md) özgün koşul yanlış ise, aşağıdaki şekilde, kendi deyimleri çalıştırılır. Çalışma zamanında koşul değerlendirildiğini unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler başvurusu](../../assembler/masm/directives-reference.md)