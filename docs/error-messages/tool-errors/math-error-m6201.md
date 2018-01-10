---
title: "Matematik hatası M6201 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: M6201
dev_langs: C++
helpviewer_keywords: M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17de7fab7b41a5a8acc2fed2f3c8185f66aadd9c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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