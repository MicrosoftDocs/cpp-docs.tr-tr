---
title: . EĞER | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .IF
dev_langs:
- C++
helpviewer_keywords:
- .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ab0e2fc510b4be8c5a9a8c0c3d0fb1c4347f0b9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
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
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)