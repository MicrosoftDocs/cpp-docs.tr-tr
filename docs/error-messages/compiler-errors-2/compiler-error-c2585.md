---
title: Derleyici Hatası C2585 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2585
dev_langs:
- C++
helpviewer_keywords:
- C2585
ms.assetid: 05bb1a9c-28fb-4a88-a1b5-aea85ebdee1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ab812a4b6621acb28a4df636056598047f5c21e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230167"
---
# <a name="compiler-error-c2585"></a>Derleyici Hatası C2585
'type ' açık dönüştürme belirsiz  
  
 Tür dönüşümü birden fazla sonuç üretebilir.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Birden çok devralmayı göre bir sınıf veya yapı türü dönüştürme. Aynı temel sınıfı türü birden çok kez devralır, dönüştürme işlevi veya işleci kapsam çözümü kullanmanız gerekir (`::`) Dönüştürmedeki devralınan sınıfların belirtmek için.  
  
2.  Bir dönüşüm işleci ve bir oluşturucu aynı dönüştürme yapma tanımlanmadı.