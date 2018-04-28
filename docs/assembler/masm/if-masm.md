---
title: IF (MASM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- if
dev_langs:
- C++
helpviewer_keywords:
- IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 76bf63b917a65a5a41fd261cfc861a77b0f0d16f
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
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
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)