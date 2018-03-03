---
title: "Derleyici Uyarısı (düzey 4) C4235 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4235
dev_langs:
- C++
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b0fea028932a48b9c7ee1a677a3e6dc8078edc35
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4235"></a>Derleyici Uyarısı (düzey 4) C4235
kullanılan standart olmayan uzantısı: Bu mimarisine desteklenmeyen 'anahtar sözcüğü' anahtar sözcüğü  
  
 Derleyici kullandığınız anahtar sözcüğü desteklemez.  
  
 Bu uyarı için bir hata otomatik olarak yükseltilir. Bu davranışı değiştirmek istiyorsanız, kullanmak [#pragma Uyarısı](../../preprocessor/warning.md). Örneğin, bir düzey 2 uyarı C4235 yapmak için aşağıdaki kod satırını kullanın.  
  
```  
#pragma warning(2:4235)  
```  
  
 Kaynak kodu dosyasının içinde.