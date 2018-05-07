---
title: Matematik hatası M6201 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6201
dev_langs:
- C++
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6a15e841cfc8daf1abdafc9997698807e7356af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="math-error-m6201"></a>Matematik Hatası M6201
'function': _domaın hata  
  
 Bu işlev için geçerli giriş değerleri, etki alanı dışındaki verilen işlevi bağımsız değişken oluştu.  
  
## <a name="example"></a>Örnek  
  
```  
result = sqrt(-1.0)   // C statement  
result = SQRT(-1.0)   !  FORTRAN statement  
```  
  
 Bu hata çağırır `_matherr` işlevi işlev adı, bağımsız değişkenlerini ve hata türü. Yeniden yazana `_matherr` belirli çalışma zamanı kayan nokta Matematiği hatalarının işlenmesini özelleştirmek için işlevi.