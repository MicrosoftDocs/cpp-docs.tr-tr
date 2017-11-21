---
title: IF (MASM) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: if
dev_langs: C++
helpviewer_keywords: IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b6ddb2c9d9ec6e39a0147d513fb452685d8e7213
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="if-masm"></a>IF (MASM)
Veren bütünleştirilmiş *if* varsa *İfade1* değeri true (sıfır) veya *elseifstatements* varsa *İfade1* false (0) ve *İfade2* doğrudur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
   IF expression1  
ifstatements  
[[ELSEIF expression2  
   elseifstatements]]  
[[ELSE  
   elsestatements]]  
ENDIF  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İçin aşağıdaki yönergeleri yerine [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI** , **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, ve **ELSEIFNDEF** . İsteğe bağlı olarak derler *elsestatements* önceki ifade yanlış olması durumunda. İfadeler derleme zamanında değerlendirildiğini unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler başvurusu](../../assembler/masm/directives-reference.md)