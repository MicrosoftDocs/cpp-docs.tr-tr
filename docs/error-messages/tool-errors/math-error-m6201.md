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
ms.openlocfilehash: e8288770d74497e576a299d683b846214a187a1c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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